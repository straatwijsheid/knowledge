# Straatwijsheid knowledge

Hand-curated knowledge for [Straatwijsheid](https://straatwijsheid.nl): what Dutch streets are named after, as judged by people and reviewed against sources.
The code that uses it lives in [straatwijsheid/straatwijsheid](https://github.com/straatwijsheid/straatwijsheid) (`python src/pipeline.py bootstrap` clones this repository into `knowledge/`).

Licence: CC-BY 4.0, see `LICENSE` and `ATTRIBUTION.md`.

## Know your neighbourhood? Help us name the streets

Each gemeente has a review sheet, `gemeenten/<province>/<gemeente>/REVIEW.md`: streets we read as a kind of person (or place, or thing) but cannot name yet,
grouped by buurt. Add what you know in the *Your answer* column and open a pull request. Say where the knowledge comes from (a local history book, a street
sign, an OpenStreetMap or Wikidata link); a plausible guess is welcome too, marked as such. The sheets are Dutch first with English beside it.

Step by step, what counts as a source and what happens to your answer: **[REVIEWING.md](REVIEWING.md)** (Nederlands / English).

## Contributing

- **Review-sheet answer:** see above; the easiest way to help, no tooling needed.
- **A correction:** add an entry to `gemeenten/<province>/<gemeente>/corrections.json` (format below), always with a `reason` and, where you can, a source.
- **A wrong rule proposal:** add the street to `global/rule_exclusions.json` under the rule's name, with the reason. Do not edit `overrides/<rule>.json` by hand: the code regenerates those files.
- **A new gemeente:** an entry in `global/gemeenten_index.json` (CBS code, name, province) and its folder under `gemeenten/`, produced by `pipeline.py add` in the code repository.
- Overrides are regenerated with `python src/rules/run.py --apply RULE` in the code repository; commit the regenerated files with the change that caused them.
- Commit messages: a short imperative subject saying what changed. Knowledge is licensed CC-BY 4.0; give a source for what you add and do not paste text from websites or books.

The full guide (setup, tests, adding a rule) is [CONTRIBUTING.md](https://github.com/straatwijsheid/straatwijsheid/blob/main/CONTRIBUTING.md) in the code repository.

## Layout

```
schema_version                          one integer: the layout version; core refuses a checkout whose version it does not read
global/                                  curated lists that apply everywhere
  vocabulary.json, species*.txt, famous_people.txt, common_*.txt, person_labels.json, directional_places.json, place_match_corrections.json
  rule_exclusions.json                   rule proposals that were reviewed and rejected, with the reason
  rules_status.json                      rules switched off until their proposals are reviewed
  osm_entity_kinds.json, osm_suggestions.json   reviewed kinds for OSM etymology items; tags we want added in OpenStreetMap
  theme_labels.json, gemeenten.json (acquisition exceptions), gemeenten_index.json (the registry: CBS gemeentecode GM#### -> name and province)
gemeenten/<province>/<gemeente>/
  REVIEW.md                              the review sheet (generated; answers go here); REVIEWING.md at the top: how to fill one in
  corrections.json                       reviewed street-level decisions, each with a reason; the last and strongest layer
  review_notes.json                      notes shown in the review sheet
  overrides/<layer>.json                 the street-level classification layers, one file per rule (legacy_hand = the frozen first-wave hand classifications)
```

A street is identified by `(gemeente code, street)`: the CBS gemeentecode (GM####, see `global/gemeenten_index.json`), never the name, because two gemeenten can share a name (Bergen in Noord-Holland and in Limburg). The `gemeente` field inside entries is the display name; the shard directory (province, then name) is what ties an entry to its gemeente. The same street name can mean different people in different places, so the buurt decides, never the name alone.

## Corrections

`corrections.json` holds `{"corrections": [ {gemeente, street, category, subcategory, entity_label, entity_description, confidence, reason, from_osm?}, ... ]}`.
`category` is `person`, `place` or `thing`. `from_osm: true` takes the namesake from the street's OpenStreetMap etymology tag and keeps the kind given here.
Always give a `reason`.
