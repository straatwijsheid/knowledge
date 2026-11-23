# Een controleblad invullen / Filling in a review sheet

*Nederlands eerst, English below.*

## Nederlands

**Waarom?** Een computer kan veel straatnamen herkennen, maar niet wie "Banstraat" echt is. Dat weet iemand uit de buurt, of staat in een plaatselijk geschiedenisboek. Elke gemeente heeft een controleblad (`gemeenten/<provincie>/<gemeente>/REVIEW.md`) met de straten waar uw kennis het meeste oplevert.

**Zo vult u het in**

1. Open het blad van uw gemeente op GitHub en kies het potlood (Edit). GitHub maakt zelf een kopie voor u.
2. Typ in de laatste kolom, *Uw antwoord*, wat u weet. Eén regel per straat, geen `|`-teken. Voorbeelden:
   - `Jan Ban, organist in de Catharinakerk, 1850-1920` (wie)
   - `fout: dit is een plant` (de lezing klopt niet)
   - `waarschijnlijk Jan Ban, organist` (een gok mag, maar zeg dat het een gok is)
3. Sla over wat u niet weet. Laat de andere kolommen en regels ongemoeid.
4. Kies *Commit changes* en maak een pull request. Zet in de beschrijving waar uw kennis vandaan komt.

**Wat telt als bron?**

| Uw antwoord rust op | Wat wij ervan maken |
|---|---|
| Een Wikidata-item, OpenStreetMap-tag (`name:etymology:wikidata`) of een webpagina/document die de naamgeving zegt: geef de link | kan op *niveau 1* (extern onderbouwd) komen, nadat een beheerder de bron heeft gelezen |
| Een boek, straatnaambordje of gemeentelijk besluit: noem titel, pagina of datum | *niveau 2* (uit kennis, niet gecontroleerd), of niveau 1 als de bron controleerbaar is |
| Uw eigen lokale kennis, zonder bron | *niveau 2*, nooit hoger |
| Een gok | wordt als gok genoteerd, niet toegepast zolang er geen tweede aanwijzing is |

Plak geen tekst uit websites of boeken; geef de bron en vat samen in eigen woorden. Uw bijdrage valt onder [CC-BY 4.0](LICENSE).

**Wat gebeurt er daarna?** Een beheerder leest uw pull request, zet de antwoorden om in correcties (`corrections.json`, met uw reden en bron), genereert de overrides en de kaart opnieuw, en voegt samen. De straat verschijnt dan met uw naamgever op de kaart. Antwoorden die we niet kunnen toepassen (te vaag, tegenstrijdig) blijven staan met een vraag terug in de pull request. Het blad wordt later opnieuw gegenereerd; uw antwoorden blijven daarbij bewaard.

## English

**Why?** A computer can recognise many street names, but not who "Banstraat" really is. Someone from the neighbourhood knows, or a local history book does. Each gemeente has a review sheet (`gemeenten/<province>/<gemeente>/REVIEW.md`) listing the streets where your knowledge helps most.

**How to fill it in**

1. Open your gemeente's sheet on GitHub and choose the pencil (Edit). GitHub makes a copy for you.
2. In the last column, *Your answer*, type what you know. One line per street, no `|` character. Examples:
   - `Jan Ban, organist at the Catharinakerk, 1850-1920` (who)
   - `wrong: this is a plant` (our reading is wrong)
   - `probably Jan Ban, organist` (a guess is welcome, but say it is one)
3. Skip any you do not know. Leave the other columns and rows alone.
4. Choose *Commit changes* and open a pull request. Say in the description where your knowledge comes from.

**What counts as a source?**

| Your answer rests on | What we make of it |
|---|---|
| A Wikidata item, an OpenStreetMap tag (`name:etymology:wikidata`) or a web page/document that states the naming: give the link | can reach *tier 1* (externally backed) once a maintainer has read the source |
| A book, a street sign or a municipal decision: give title, page or date | *tier 2* (from knowledge, unverified), or tier 1 if the source can be checked |
| Your own local knowledge, with no source | *tier 2*, never higher |
| A guess | recorded as a guess, not applied until there is a second indication |

Do not paste text from websites or books: cite and summarise in your own words. Your contribution is licensed [CC-BY 4.0](LICENSE).

**What happens next?** A maintainer reads your pull request, turns the answers into corrections (`corrections.json`, with your reason and source), regenerates the overrides and the map, and merges. The street then shows your namesake on the map. Answers we cannot apply (too vague, contradictory) get a question back in the pull request. The sheet is regenerated later; your answers are kept when that happens.

What the tiers mean: [method](https://github.com/straatwijsheid/straatwijsheid/blob/main/docs/method.md). Setup and the other ways to contribute: [CONTRIBUTING](https://github.com/straatwijsheid/straatwijsheid/blob/main/CONTRIBUTING.md).
