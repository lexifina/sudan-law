# Sudan: law history in git

[العربية](README.md) · **English**

<picture>
<source media="(prefers-color-scheme: dark)" srcset="data/effort-dark.svg">
<img alt="Sudanese law in this repository: what it holds, changes by the year they took effect, completeness against the official sources, and the correctness of what is held" src="data/effort-light.svg" width="880">
</picture>

The law of Sudan as a git history: one file per section, one commit per version on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every line; `git log` lists every change to a section; picking a date gives the text in force that day.

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is Sudan's national law, which global-law reads at `sudan/national/acts/`.

**What is in it now:** the Interim National Constitution 2005 and 300 acts of the Ministry of Justice's 9th Revised Edition of the Laws of Sudan (laws in force on 30 March 2015), from the Bills of Exchange Act 1917 to acts of 2015: among them the Criminal Act 1991, the Criminal Procedure Act 1991, the Personal Status Act for Muslims 1991, the Civil Procedure Act 1983, the Evidence Act 1994 and the Labour Act 1997. See [STRUCTURE.md](STRUCTURE.md) for the layout and what is held back.

Acts are in `قوانين/<year>/<title>/`, one file per section: `قوانين/1991/القانون-الجنائي/مادة-174.md` is section 174 of the Criminal Act, theft (السرقة); part and chapter headings are in `باب-*.md`, schedules in `جدول-*.md`, and each act's title, dates and source in `ديباجة.md`. The constitution is in `دساتير/`.

The text is in Arabic, as the Ministry of Justice's edition prints it, with each section's marginal note as its heading. An English translation is not part of this record.

## Questions as git commands

| Question | Command |
| --- | --- |
| Every change to section 174 of the Criminal Act | `git log -p --word-diff -- قوانين/1991/القانون-الجنائي/مادة-174.md` |
| Which law wrote each line of section 174? | `git blame قوانين/1991/القانون-الجنائي/مادة-174.md` |
| Every version of the Criminal Act, with the day each took effect | `git log --format="%h %(trailers:key=In-force,valueonly,separator=) %an" -- قوانين/1991/القانون-الجنائي ':!*/README.md'` |
| Section 174 as in force on 30 March 2015 | `python tools/on.py 2015-03-30 قوانين/1991/القانون-الجنائي مادة-174` |

**Outside git**, we also host this record publicly, for free:

- **[Ask Claude about Sudanese law](https://global-law.lexifina.com/v1/try_claude?country=sudan)**: opens Claude with a first question ready.
- **[Ask ChatGPT](https://global-law.lexifina.com/v1/try_chatgpt?country=sudan)**: the same question in ChatGPT.
- **[Search Sudanese law on our site](https://lexifina.com/law?country=sudan&q=%D8%A7%D9%84%D8%B3%D8%B1%D9%82%D8%A9)**: a search for "السرقة" (theft), with each provision's text and its versions, no account needed.
- **[Developer REST API](https://global-law.lexifina.com/v1/search_law?query=%D8%A7%D9%84%D8%B3%D8%B1%D9%82%D8%A9&jurisdiction=sudan)**: the same search as JSON, with no key. See the [documentation here](https://lexifina.com/api/global-law).

Both assistants read the record through the free Global law connector (MCP, `https://global-law.lexifina.com/mcp`); the first time, the chat gives you the link that adds it. Ask in Arabic or in English.

**Host it yourself easily.** All it takes is git and Python, and the tools run on your machine:

```sh
git clone --depth 1 https://github.com/lexifina/global-law && cd global-law
python3 tools/countries.py add sudan/national/acts
python3 tools/law.py show 2026-01-01 sudan/national/acts/قوانين/1991/القانون-الجنائي/مادة-174.md
```

Opened in Claude Code, Cursor, VS Code or Codex, the clone also starts a local MCP server with the same tools ([MCP.md](https://github.com/lexifina/global-law/blob/main/MCP.md)).

## Dates

Each commit is dated at noon, Africa/Khartoum, on the day the version took effect, and carries it in its `In-force:` trailer:

- an act whose footnotes in the edition name no amending law is the text as enacted, dated by the commencement date printed under its title (the edition's "تاريخ السريان"): 108 acts;
- an act whose footnotes name later amending laws is the text as in force on 30 March 2015, the edition's cut-off, and is dated that day (191 acts, the Criminal Act among them); the amending laws are listed in the commit's `Amended-by:` trailer, as the edition gives no day for each change;
- versions before 1970 are stamped 1 January 1970, with the real day first in the subject and in `In-force:`;
- the Interim National Constitution is dated 9 July 2005, the day it was signed (Art. 223(2), 226(4)).

Versions are credited to the publisher, `Ministry of Justice of Sudan (وزارة العدل)`, not to a law; the constitution to the Constitute Project. Parse corrections are separate `Kind: correction` commits, dated like the version they correct. The committer is Lexifina.

## How it is checked

- `tools/check_repo.py` reads every version back from git on the day it took effect and on the day before, compares it file by file with the corpus it was built from, and checks every commit's trailers; [`REPRODUCE.md`](REPRODUCE.md) does not yet record a run for this build.
- The Criminal Act was read again from the Ministry's live edition on 30 October 2026: every file matched.
- The wording is as printed: footnote markers are dropped, spacing is normalised and marginal notes become headings; nothing else is changed (see `LICENSE`).
- The same corpus always gives the same commit hashes (`tools/build.py`); `main` has no merge commits and no commit dated in the future.
- [vulnerabilities/](vulnerabilities/README.en.md): possible drafting mistakes in this law, found by global-law's detectors and checked by hand. Not run yet.

## What it does not show

- **Changes after 30 March 2015.** Many acts have been amended since (the Criminal Act in 2020, among others); no later change is applied, so a section may differ from the text in force today. Acts made after the edition are not here yet.
- **Amended acts as enacted**: for an amended act only the edition's 2015 text is here.
- **32 acts of the edition**, held because their parse did not check out against the act's own table of sections or had no usable date line, among them the Civil Transactions Act 1984, the Companies Act 1925 and the Land Settlement and Registration Act 1925 (list in STRUCTURE.md). Regulations, case law and bills are not here.
- **The 2019 Constitutional Charter**, its 2020 and 2025 amendments, the 1998 Constitution and the 2015 amendments of the 2005 Constitution: the official copies are Gazette scans with no text layer, and no text is read by OCR.

## Sources

| Source | Kind | Past versions | Notes |
| --- | --- | --- | --- |
| [Ministry of Justice of Sudan, قوانين السودان](https://www.moj.gov.sd/sudanlaws/) | Official 9th Revised Edition of the Laws of Sudan | no: unamended acts as enacted, amended acts as in force on 30 March 2015 | Retrieved 26 November 2026; footnotes name amending laws without dates |
| [Constitute Project](https://www.constituteproject.org/constitution/Sudan_2005?lang=ar) | Secondary copy: Interim National Constitution 2005, Arabic | no | Retrieved 26 November 2026 |

## Licence

See [`LICENSE`](LICENSE). Laws are not protected by copyright in Sudan: the Copyright and Neighbouring Rights Protection and Literal and Artistic Works Act, 2013, section 6(b), excludes official documents, which section 2 defines to include laws. Lexifina's own contributions (the arrangement of the history, the commit messages and the tools) are CC0 1.0.

No AI model wrote, translated or corrected legal text, and none runs when the history is built; the scripts were written by an AI model (see [`REPRODUCE.md`](REPRODUCE.md)).

## Visualisations

- [visualisations/](visualisations/README.en.md): charts drawn from this repository. Not drawn yet.

## More

From [lexifina/global-law](https://github.com/lexifina/global-law):

- [FEATURES.md](https://github.com/lexifina/global-law/blob/main/FEATURES.md): every feature, and what every corpus must support (`git blame`, `law.py`, the MCP tools)
- [FAQ.md](https://github.com/lexifina/global-law/blob/main/FAQ.md): questions and answers · [CONTRIBUTING.md](https://github.com/lexifina/global-law/blob/main/CONTRIBUTING.md): proposing changes · [MCP.md](https://github.com/lexifina/global-law/blob/main/MCP.md): the MCP server · [REPRODUCE.md](https://github.com/lexifina/global-law/blob/main/REPRODUCE.md): how it was built · [CHANGELOG.md](https://github.com/lexifina/global-law/blob/main/CHANGELOG.md)
- [FRESHNESS.md](https://github.com/lexifina/global-law/blob/main/FRESHNESS.md): how current each corpus is · [Monitoring](https://github.com/lexifina/global-law/tree/main/monitoring): whether updates are running · [WATCHING.md](https://github.com/lexifina/global-law/blob/main/WATCHING.md): how each official source is watched for changes
- [performance/](https://github.com/lexifina/global-law/tree/main/performance): how fast the tools are, measured
- [visualisations/](https://github.com/lexifina/global-law/tree/main/visualisations): charts and bridges across the world's law
- [Vulnerabilities](https://github.com/lexifina/global-law/tree/main/vulnerabilities): mistakes in legislation as published
