# هيكل المستودع · Structure

Folder and file names are in Arabic, the language of the law and of the people who search it.

| Path | Holds |
| --- | --- |
| `دساتير/<السنة>-<الاسم>/` | constitutions: `دساتير/2005-الدستور-القومي-الانتقالي/` (Interim National Constitution 2005) |
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

## Held (32 acts of the edition)

Held because the parse did not reach the last section of the act's own table of sections (ترتيب المواد), found
duplicate or out-of-order sections, or the chapter has no usable date line under its title. They need a hand check.

| Act | Why held |
| --- | --- |
| قانون ناحتي الأختام لسنة 1903 | no date line under the title |
| قانون الكمبيالات لسنة 1917 | no table of sections; parsed to section 43, body mentions 99 |
| قانون الشركات لسنة 1925 | text after heading part-04-chapter-05: القـيود الخـاصة بالتخصيص .94ـ (1) لا يجوز تخصيص شيء من رأس م; text after heading part-04-chapter-06: سلطة دفع عمولات 98ـ  |
| قانون تسوية الأراضي وتسجيلها لسنة 1925 | duplicate key art-019-bis; duplicate key art-019-bis; text after heading part-00-chapter-05: 98ـ ألغيت . |
| قانون حماية المزارعين في دلتا القاش ودلتا طوكر لسنة 1928 | no date line under the title |
| قانون تنظيم العمل بالإشعاعات المؤينة لسنة 1971 | date line 1973-05-25 disagrees with the year in the title |
| قانون الحجر الصحي لسنة 1974 | text after heading part-00-chapter-04: الإقرار الصحي 52ـ (1) يجوز للسلطة الصحية أن تطلب من أي سفينة; last article 46, expected 58 |
| قانون أكاديمية السودان للعلوم الإدارية لسنة 1978 | text after heading part-00-chapter-04: تعيين الأساتذة. 18ـ يعين المجلس أساتذة الأكاديمية بناء على ت; text after heading part-00-chapter-05: الموارد المالية للأك |
| قانون صندوق مال اللاجئين لسنة 1982 | no table of sections; parsed to section 12, body mentions 6713 |
| قانون المحاماة لسنة 1983 | text after heading part-00-chapter-04: سجل المحامين . 11ـ (1) يستمر العمل بسجلي المحامين المنشأين ق; text after heading part-00-chapter-05: طلب التمرين على المح |
| قانون المعاملات المدنية لسنة 1984 | no table of sections; parsed to section 704, body mentions 819 |
| قانون رسم دمغة اتحاد عام أصحاب العمل السوداني لسنة 1984 | text after heading part-00-chapter-02: فئات الرسم . 1 3ـ (1) دون المساس بأحكام قانون رسم الدمغة لسن; text after heading part-00-chapter-03: مسئولية الاتحاد عن 9 |
| قانون الرقابة على العربات الحكومية لسنة 1988 | last article 14, expected 16 |
| قانون مكافحة الثراء الحرام والمشبوه لسنة 1989 | last article 16, expected 19 |
| قانون منظمة الدعوة الإسلامية لسنة 1990 | no date line under the title |
| قانون التأمين الاجتماعي لسنة 1990 | text after heading part-00-chapter-06: المستحقون وشروط 76ـ إذا توفى المؤمن عليه، أو صاحب المعاش فيك; text after heading part-00-chapter-07: سلطة الوزير في 83ـ ي |
| قانون المركز القومي للمناهج والبحث التربوي لسنة 1996 | last article 22, expected 38 |
| قانون جامعة غرب كردفان لسنة 1997 | last article 37, expected 38 |
| قانون معاشات القضاة لسنة 1999 | no date line under the title |
| قانون مجلس تنظيم بيوت الخبرة للخدمات الاستشارية لسنة 1999 | text after heading part-00-chapter-04: شروط الخدمة. (11) 8- (1) يمـنح رئيس المجلس وأعضـاؤه، مكافآت ; text after heading part-00-chapter-05: إنشاء بيوت الخبرة .1 |
| قانون الصندوق القومي للتأمين الصحي لسنة 2001 | text after heading part-00-chapter-03: الإدارات التنفيذية بالولايات. (1010) 17- (1) تنشأ في كل ولاي; text after heading part-00-chapter-04: موارد الصندوق المالي |
| قانون المجلس القومي لرعاية الطفولة لسنة 2008 | text after heading part-00-chapter-04: موارد المجلس . 12- تتكون موارد المجلس المالية من الآتي :; text after heading part-00-chapter-05: سلطة إصدار اللوائح. 17-  |
| قانون المعادن النفيسة والأحجار الكريمة لسنة ‏2008 | last article 24, expected 26 |
| قانون مكافحة الإغراق لسنة 2009 | last article 27, expected 28 |
| قانون مكافحة التصحر لسنة 2009 | text after heading part-00-chapter-06: أحكام عامة(3); last article 20, expected 25 |
| قانون استفتاء منطقة أبيي لسنة 2009 | text after heading part-00-chapter-05: البرنامج الإعلامي للاستفتاء. 43- (1) تقوم المفوضية بإعلان تا; text after heading part-00-chapter-06: الرشوة . 46- (1) لأغ |
| قانون النقل البحري لسنة 2010 | text after heading part-00-chapter-20: تعويضات التصادم . 130- (1) إذا وقع تصـادم بين السفينة البحري; text after heading part-00-chapter-21: سريان أحكام هذا الفص |
| قانون مجلس المهن الموسيقية والتمثيلية لسنة 2010 | last article 31, expected 32 |
| قانون مجلس المهن الطبية والصحية لسنة 2010 | text after heading part-00-chapter-06: الموارد المالية للمجلس. 25- تتكون الموارد المالية للمجلس من ; text after heading part-00-chapter-07: الشكاوى . 30- (1) يج |
| قانون جامعة ود مدني الأهلية لسنة 2012 | text after heading part-00-chapter-04: الموارد المالية للجامعة .36- (1) تتكون موارد الجامعة المالية; text after heading part-00-chapter-05: تعيين العاملين . 38- |
| قانون مكافحة الاتجار بالبشر لسنة 2014 | text after heading part-00-chapter-04: الموارد المالية للجنة . 19 تكون للجنة الموارد المالية الآتية; text after heading part-00-chapter-05: الرضا . 24- لا يعتد  |
| قانون تنمية الثروة المعدنية والتعدين لسنة 2015 | text after heading part-00-chapter-05: إنشاء اللجنة وتشكيلها والإشراف عليها .21- (1) تنشأ لجنة تسمى; text after heading part-00-chapter-06: إعداد السجلات وتقييد |

## Not here yet

- Acts made after 30 March 2015 and later amendments (e.g. the Criminal Act amendments of 2020): no official text-layer source found yet.
- The 2019 Constitutional Charter and its 2020/2025 amendments, the 1998 Constitution, the 2015 amendments of the 2005 Constitution: Gazette scans only (no OCR).
- Regulations, case law.
