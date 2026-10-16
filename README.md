# Künstlerfinanzen — open data on the Künstlersozialkasse (KSK)

Two small, sourced datasets for freelancers insured with the German Künstlersozialkasse,
published by [Künstlerfinanzen](https://kuenstlerfinanzen.de/) under **CC BY 4.0**.
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23420846.svg)](https://doi.org/10.5281/zenodo.23420846) Every row
carries its primary source and the date it was last checked. The live copies are served at
<https://kuenstlerfinanzen.de/entwickler.html>; this repository is the citable snapshot.

*Deutsch:* Zwei kleine, belegte Datensätze für KSK-Versicherte — die Beitragssätze der
Künstlersozialversicherung und die festen Fristen und Meldeschlüsse des Jahres (KSK, VG Wort,
VG Bild-Kunst, Einkommensteuer-Vorauszahlungen). Jede Zeile nennt ihre Quelle und ihr Prüfdatum.
Lizenz CC BY 4.0. Keine Rechts- oder Steuerberatung.

## Datasets

| File | What | Rows | Source per row |
|---|---|---|---|
| `data/ksk-beitragssaetze.json` / `.csv` | Contribution rates of the Künstlersozialversicherung per year — full statutory rates and the share the insured person bears (pension, health, care, care surcharge for the childless) | 1 year (2026) | kuenstlersozialkasse.de "Beitrag" |
| `data/ksk-fristen.json` / `.csv` | Fixed dates of the year for KSK members: the 1 December income report (§12 KSVG), the audit reply (§13 KSVG), first contribution due 5 February, VG Wort (31 Jan / 31 Mar METIS), VG Bild-Kunst (31 Mar), income-tax prepayments (§37 EStG), and the September mailing of the Meldebogen | 11 | gesetze-im-internet.de, kuenstlersozialkasse.de, vgwort.de, bildkunst.de, verwaltung.bund.de |
| `data/ksk-fristen.ics` | The same fixed dates as a yearly-recurring iCalendar feed | 11 events | — |

### Columns

**ksk-beitragssaetze** — `jahr`; `rente_prozent`, `kranken_prozent`, `pflege_prozent`,
`pflege_kinderlos_prozent` (full statutory rates in %); `rente_versicherte_prozent`,
`kranken_versicherte_prozent`, `pflege_versicherte_prozent`, `pflege_kinderlos_versicherte_prozent`
(the insured person's share in %, as the KSK states it — the KSK bears the rest); `status`
(`VERKUENDET` = enacted); `stand` (date checked, ISO); `quelle`; `quelle_url`. The individual
health insurer's Zusatzbeitrag (half borne by the member) is **not** included.

**ksk-fristen** — `termin` (MM-DD of the fixed date; for month-only rows the first of the month);
`monat`; `nur_monat` (`ja` if only the month is fixed — in JSON `nurMonat: true`); `titel`;
`wer` (who sets the date); `grundlage` (statute or publication); `quelle` (URL); `stand`
(date checked, ISO). CSV files use `;` as separator, UTF-8 with BOM.

## Provenance and limits

- Values are transcribed from the primary sources named per row; the check dates say when.
  The maintainers re-check each September (the KSK's reporting season) and in January (new rates).
- Only enacted figures are included — no forecasts.
- This is data, not advice. Whether a date or rate applies to a particular person is a question
  for the Künstlersozialkasse, the tax office or a professional adviser.
- Deliberately **not** included: the §3 KSVG minimum-income threshold and anything that would
  classify an activity under §2 KSVG. See the publisher's editorial note:
  <https://kuenstlerfinanzen.de/redaktion.html>.

## How to cite

Künstlerfinanzen (2026). *KSK-Beitragssätze und KSK-Fristen — offene Daten zur
Künstlersozialkasse.* <https://github.com/tony158/kuenstlerfinanzen-open-data>. DOI: [10.5281/zenodo.23420846](https://doi.org/10.5281/zenodo.23420846)
(concept DOI for all versions: 10.5281/zenodo.23420845). CC BY 4.0. See `CITATION.cff`.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) —
use it freely, name "Künstlerfinanzen, kuenstlerfinanzen.de" as the source.
