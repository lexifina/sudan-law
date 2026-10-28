# How this repository was made (Sudan)

This file is written by the build on 2026-10-28, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Ministry of Justice, Laws of Sudan ebook (9th Revised Edition) | <https://www.moj.gov.sd/sudanlaws/> | 2026-10-28 | Rights: وزارة العدل - جمهورية السودان (no open licence stated) |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `criminal-act-1991` | القانون الجنائي لسنة 1991 | 1 | 2015-03-30 to 2015-03-30 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-28.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 0 laws in the record.
- 1 tags.

## Dates

Each commit is dated at noon (Africa/Khartoum) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: the only version is dated by the revised edition's own stated date (laws in force to 30 March 2015). https://www.moj.gov.sd/sudanlaws/epub/EPUB/xhtml/sibyrw.html

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `822cb7a5c182161c215af80909fde316dd6e0732279c7df3a5b434f30c046e2c` (186146 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- One version per act, from the 9th Revised Edition, dated 2015-03-30 (the edition's own stated cut-off), credited to the publisher as oldest version available.
- Each source paragraph is one line; the marginal note (section heading) is taken out of the run-in text and put in the heading line.
- Footnote markers are dropped from the text; the amending laws they name are listed in the version note, not credited, because the edition gives no dates per change.
- The 2019 Constitutional Charter and its 2020 and 2025 amendments are left out: the official gazette PDFs (moj.gov.sd files 144, 226, 425) are scans with no usable text layer, and OCR is not used. The WIPO Lex English text is an International IDEA translation, not official.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code; no model wrote or edited legal text.
