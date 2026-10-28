# How this repository was made (Sudan)

This file is written by the build on 2026-10-28, the day the source data was retrieved. Everything below is enough to rebuild this repository hash for hash.

## Sources

| Source | Address | Retrieved | Requests | Licence |
| --- | --- | --- | ---: | --- |
| Ministry of Justice, Laws of Sudan ebook (9th Revised Edition) | <https://www.moj.gov.sd/sudanlaws/> | 2026-10-28 |  | Rights: وزارة العدل - جمهورية السودان (no open licence stated) |

Every response is cached by the sha256 of its URL, and the table above lists every source with its retrieval date. Lexifina keeps its fetch scripts privately; `tools/parse.py` reads only the cache and writes `corpus.json`, so the same cache always gives the same corpus.

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

## Commands, in order

```sh
# fill the cache from the sources listed above (network; Lexifina's fetch scripts are kept privately)
python -X utf8 tools/parse.py                  # cache -> corpus.json (no network)
python -X utf8 tools/build.py <folder> --repo <empty folder> --docs-date 2026-10-28
python -X utf8 tools/check_repo.py <repo> --corpus <folder>/corpus.json --write
python -X utf8 tools/build.py <folder> --repo <another empty folder> --docs-date 2026-10-28 --compare <repo>
```

In the main Lexifina repository these files live as follows:
- `fetch.py`, `parse.py` and `repo/`: in `scripts/sudan-law/`.
- `build.py`, `check_repo.py` (`check.py` there) and `on.py`: in `scripts/gitlaw_common/`, with the corpus format in `SCHEMA.md`.

## Exact inputs

- `corpus.json` sha256 `38364a1bec255508bba88b530dc3611dd9bfa36afaa57263bd1997276a93d6c1` (184996 bytes)
- Script blob hashes (`git hash-object`):

| Script | Blob |
| --- | --- |
| build.py | `2bfc4ac9df193a7be844556d7f69cdb9d93ec3f2` |
| check.py | `cd346c7ff9996d450240e3bab52bcae03b2bc865` |
| on.py | `644a6c0857fbcc72562032b58d57aa113fee0641` |
| fetch.py | `53bcd7a4c46f275c8e3c45eeb5d8163b50e265b2` |
| parse.py | `209a6c7e8157c71e494dd8d5e725cb2e945101f7` |

- Tools:
  - Python 3.14.0
  - git version 2.52.0.windows.1
  - curl 8.21.0 (Windows) libcurl/8.21.0 Schannel zlib/1.3.2 WinIDN WinLDAP

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

Not yet run for this build.

These results are from the check run on the build before this one, from the same corpus.

## Decisions made by hand

- One version per act, from the 9th Revised Edition, dated 2015-03-30 (the edition's own stated cut-off), credited to the publisher as oldest version available.
- Each source paragraph is one line; the marginal note (section heading) is taken out of the run-in text and put in the heading line.
- Footnote markers are dropped from the text; the amending laws they name are listed in the version note, not credited, because the edition gives no dates per change.
- The 2019 Constitutional Charter and its 2020 and 2025 amendments are left out: the official gazette PDFs (moj.gov.sd files 144, 226, 425) are scans with no usable text layer, and OCR is not used. The WIPO Lex English text is an International IDEA translation, not official.

## What AI did and did not do

The fetch, parse and check scripts were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above, through code that anyone can rerun.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote fetch.py and parse.py; no model wrote or edited legal text.
