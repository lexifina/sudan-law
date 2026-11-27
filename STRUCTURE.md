# هيكل المستودع · Structure

Folder and file names are in Arabic, the language of the law and of the people who search it.

| Path | Holds |
| --- | --- |
| `دساتير/<السنة>-<الاسم>/` | constitutions: `دساتير/2005-الدستور-القومي-الانتقالي/` (Interim National Constitution 2005), `دساتير/2019-الوثيقة-الدستورية-للفترة-الانتقالية/` (Transitional Constitutional Charter 2019, English translation; `فصل-NN.md` chapter headings) |
| `قوانين/<السنة>/<عنوان-القانون>/` | acts, by the year of their commencement date, e.g. `قوانين/1991/القانون-الجنائي/` |
| `…/ديباجة.md` | the act's title, commencement date (تاريخ السريان), the date of the version (النفاذ), state of the text (as enacted / as amended to 30 March 2015), amending laws named by the edition, volume and source |
| `…/مادة-NNN.md` | one section (مادة) per file, its marginal note as the heading; `مادة-NNN-أ.md`, `مادة-NNN-مكرر.md` for inserted sections |
| `…/باب-NN.md`, `…/باب-NN-فصل-NN.md` | part and chapter headings |
| `…/جدول-NN.md` | schedules |
| `مقدمة.md` | a constitution's preamble |

No folder holds more than 1,000 entries (the largest year folder holds a few dozen acts).

## Dating

- Act whose footnotes in the Ministry of Justice 9th Revised Edition name no amending law: the text as enacted, dated by the commencement date printed under its title (`Kind: law`).
- Act whose footnotes name later amending laws: the text as in force on 30 March 2015, the edition's cut-off (`Kind: consolidation`, `Amended-by:` trailer).
- Before 1970: stamped 1970-01-01 12:00, the real day first in the subject and in `In-force:`.
- Parse corrections: `Kind: correction`, dated like the version they correct. History is never rewritten.

## Held (18 acts of the edition)

Held because the parse did not reach the last section of the act's own table of sections (ترتيب المواد), found
duplicate or out-of-order sections, or the chapter has no usable date line under its title. They need a hand check.
On 2026-11-27, 13 acts were released by a relaxed parse (a footnote mark left as a plain number between the marginal
note and the section number) and the Civil Transactions Act 1984 by `cta.py` (its chapter prints Part 16 twice).

| Act | Why held |
| --- | --- |
| قانون ناحتي الأختام لسنة 1903 | no date line under the title |
| قانون الكمبيالات لسنة 1917 | no table of sections; parsed to section 43, body mentions 99 |
| قانون الشركات لسنة 1925 | text after heading part-04-chapter-05: القـيود الخـاصة بالتخصيص .94ـ (1) لا يجوز تخصيص شيء من رأس م; text after heading part-04-chapter-06: سلطة دفع عمولات 98ـ  |
| قانون تسوية الأراضي وتسجيلها لسنة 1925 | duplicate key art-019-bis; duplicate key art-019-bis; text after heading part-00-chapter-05: 98ـ ألغيت . |
| قانون حماية المزارعين في دلتا القاش ودلتا طوكر لسنة 1928 | no date line under the title |
| قانون الحجر الصحي لسنة 1974 | text after heading part-00-chapter-04: الإقرار الصحي 52ـ (1) يجوز للسلطة الصحية أن تطلب من أي سفينة; last article 46, expected 58 |
| قانون صندوق مال اللاجئين لسنة 1982 | no table of sections; parsed to section 12, body mentions 6713 |
| قانون منظمة الدعوة الإسلامية لسنة 1990 | no date line under the title |
| قانون التأمين الاجتماعي لسنة 1990 | text after heading part-00-chapter-06: المستحقون وشروط 76ـ إذا توفى المؤمن عليه، أو صاحب المعاش فيك; text after heading part-00-chapter-07: سلطة الوزير في 83ـ ي |
| قانون المركز القومي للمناهج والبحث التربوي لسنة 1996 | last article 22, expected 38 |
| قانون جامعة غرب كردفان لسنة 1997 | last article 37, expected 38 |
| قانون معاشات القضاة لسنة 1999 | date line not found in HTML |
| قانون مكافحة الإغراق لسنة 2009 | last article 27, expected 28 |
| قانون مكافحة التصحر لسنة 2009 | text after heading part-00-chapter-06: أحكام عامة(3); last article 20, expected 25 |
| قانون استفتاء منطقة أبيي لسنة 2009 | text after heading part-00-chapter-05: البرنامج الإعلامي للاستفتاء. 43- (1) تقوم المفوضية بإعلان تا; text after heading part-00-chapter-06: الرشوة . 46- (1) لأغ |
| قانون النقل البحري لسنة 2010 | text after heading part-00-chapter-20: تعويضات التصادم . 130- (1) إذا وقع تصـادم بين السفينة البحري; text after heading part-00-chapter-21: سريان أحكام هذا الفص |
| قانون مكافحة الاتجار بالبشر لسنة 2014 | text after heading part-00-chapter-04: الموارد المالية للجنة . 19 تكون للجنة الموارد المالية الآتية; text after heading part-00-chapter-05: الرضا . 24- لا يعتد  |
| قانون تنمية الثروة المعدنية والتعدين لسنة 2015 | text after heading part-00-chapter-05: إنشاء اللجنة وتشكيلها والإشراف عليها .21- (1) تنشأ لجنة تسمى; text after heading part-00-chapter-06: إعداد السجلات وتقييد |

## Not here yet

- Acts made after 30 March 2015 and later amendments (e.g. the Criminal Act amendments of 2020): no official text-layer source found yet; WIPO Lex's Arabic Criminal Act PDF (SD004) is a cover page only.
- The Arabic text of the 2019 Constitutional Charter and its 2020/2025 amendments, the 1998 Constitution, the 2015 amendments of the 2005 Constitution: Gazette scans only (no OCR). The Charter is here in English translation (2019 and 2020 versions).
- Secondary copies checked on 2026-11-26 and not usable: FAOLEX (all post-2015 Sudanese laws are scans; the 2025 genetic-resources regulations have a scrambled text layer), WIPO Lex (the 2019 Charter in English translation only), the Constitute Project (2019 Charter in English translation only; used since 2026-11-27 for the Charter), a 3-page partial Arabic Charter PDF from an NGO.
- Regulations (the Ministry of Justice download centre has about 20 regulations with a text layer, but the layer is scrambled by the PDFs' font encoding), case law.
