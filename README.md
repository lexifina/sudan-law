# Sudan: law history in git

The law of Sudan (SD) as a git history: one file per provision, one commit per law on the day it took effect, and the law that made the change as the commit author. It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `sd/`.

**First build, deliberately small.** Language: Arabic (the official language), so the text is right-to-left.

| Folder | Text | Versions | History |
| --- | --- | ---: | --- |
| `criminal-act-1991/` | القانون الجنائي لسنة 1991 (Criminal Act 1991) | 1 | Oldest version available: the text in the Ministry of Justice's 9th Revised Edition of the Laws of Sudan, which states it holds the laws in force to 30 March 2015 |

**What is not here.** The edition gives no dates for later changes, so the history has one version. Changes to the Criminal Act after 30 March 2015 are not in it. The Civil Transactions Act 1984 is in the same edition but was left out because its parse was not complete. The 2019 Constitutional Charter and its amendments are left out: the gazette PDFs are scans with no text layer, and nothing was read by OCR.

**Source:** [Ministry of Justice of Sudan, قوانين السودان, 9th Revised Edition](https://www.moj.gov.sd/sudanlaws/), official, retrieved 28 October 2026 and compared again with the live page on 30 October 2026 (identical). See `LICENSE` and `REPRODUCE.md`.

Dates are the day the change took effect. This repository is not legal advice; for anything that matters, read the original.
