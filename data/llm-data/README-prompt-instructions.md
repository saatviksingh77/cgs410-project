### PROMPTS TO BE FED TO THE DIFFERENT LLMS FOR THE DIFFERENT LANGUAGES BASED ON THE TYPE OF SUD DATA AVAILABLE

<b>

- RUN THE PROMPT MULTIPLE TIMES (variable) TO COLLECT A DATA OF ```500 RAW SENTENCES``` FROM THE CHOSEN LLM

- THE RAW SENTENCES ARE THEN TO BE PUT IN A ```.txt``` FILE WITH ```EACH LINE HAVING ONE SENTENCE ONLY```

- ChatGPT free, Claude free, Gemini Thinking mode

</b>

<br>

> For all languages, run a small sample back through the LLM and ask "Are these sentences grammatically correct and natural in [said language]?” as a quick quality check before committing to parsing 500 of them.

```
Here are 10 sentences in [language]. For each one, tell me:
1. Is it grammatically correct?
2. Does it sound like formal written text (not spoken)?
3. Is it between [X] and [Y] words long?
Flag any sentence that fails any criterion.
```

> – Sometimes an instruction like below has to be added to ensure uniqueness of responses <br>
> ```strictly generate unique new sentences each time and do not repeat or rephrase from previous responses``` <br>
> – Increasing single prompt sentence count also ensures better uniqueness within responses. <br>
> – Issue observed mainly in free versions, or less mainstream languages.

<br><br>

-------ENGLISH------- <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/en.txt```
```
Generate exactly 50 sentences in English that resemble informal but grammatically complete web writing, the kind found in online news comments, blog posts, and factual Q&A forums. Topics should span everyday factual knowledge: science, geography, current events, technology, sports, and history. 

Vary the syntactic structure deliberately across the 50 sentences:
- At least 10 sentences should contain a subordinate clause 
  (e.g. "Although the river floods annually, the town has never relocated.")
- At least 10 should contain a relative clause 
  (e.g. "The enzyme that breaks down lactose is produced in the small intestine.")
- At least 10 should be compound sentences joined by coordinating conjunctions
- The remaining sentences can be simple declarative

Each sentence must be between 12 and 20 words long. Do not use passive voice exclusively — mix active and passive constructions. Do not use bullet points, numbered lists, headings, or dialogue. Output only the sentences, one per line, with absolutely no additional commentary, labels, or blank lines between sentences.
```
<br>

-------HINDI------- <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/hi.txt```
```
हिंदी समाचार पत्र की शैली में ठीक 50 वाक्य लिखें। विषय इनमें से 
हों: राजनीति, भूगोल, विज्ञान, इतिहास, खेल, या अर्थव्यवस्था। 
भाषा औपचारिक और मानक हिंदी होनी चाहिए, जैसे हिंदुस्तान टाइम्स 
या दैनिक जागरण में प्रकाशित होती है।

वाक्य संरचना में विविधता रखें:
- कम से कम 10 वाक्यों में कारण-कार्य संबंध हो 
  (जैसे "क्योंकि", "इसलिए", "फलतः")
- कम से कक 10 वाक्यों में सापेक्ष उपवाक्य हो 
  (जैसे "जो", "जिसने", "जहाँ")
- कम से कम 10 वाक्यों में संयुक्त क्रिया हो 
  (जैसे "कर दिया", "हो गया", "ले लिया")
- वाक्य SOV क्रम में हों — क्रिया वाक्य के अंत में आए

प्रत्येक वाक्य 18 से 28 शब्दों का होना चाहिए। वाक्य पूर्ण और 
स्वतंत्र हों। केवल वाक्य लिखें, एक पंक्ति में एक वाक्य, बिना 
क्रमांक, शीर्षक या अतिरिक्त टिप्पणी के।
```
<br>

––––––GERMAN––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/de.txt```
```
Schreibe genau 50 Sätze auf Deutsch, die dem Stil von Wikipedia-Artikeln 
und deutschen Nachrichtentexten entsprechen. Themen sollen aus den 
Bereichen Geographie, Wissenschaft, Geschichte, Technologie, Politik 
und Kultur stammen.

Achte auf folgende syntaktische Eigenschaften, die für natürliches 
Deutsch typisch sind:
- Mindestens 15 Sätze sollen einen eingebetteten Nebensatz enthalten, 
  bei dem das Verb am Ende steht (z.B. Relativsätze mit "der/die/das", 
  oder Kausalsätze mit "weil", "obwohl", "damit")
- Mindestens 10 Sätze sollen komplexe Nominalphrasen mit 
  attributiven Adjektiven enthalten 
  (z.B. "die neu gegründete Forschungseinrichtung")
- Mindestens 10 Sätze sollen im Passiv formuliert sein
- Vermeide durchgehend einfache SVO-Struktur — nutze Verb-Zweit-
  Stellung mit vorangestellten Adverbialien oder Objekten

Jeder Satz soll zwischen 15 und 25 Wörter lang sein. Keine 
Aufzählungen, Überschriften, Nummerierungen oder Dialoge. Gib nur 
die Sätze aus, einen pro Zeile, ohne jeglichen zusätzlichen Text.
```
<br>

––––––ARABIC––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/ar.txt```
```
اكتب بالعربية الفصحى المعيارية (MSA) تحديداً 50 جملة بأسلوب 
إخباري رسمي، مماثل لما ينشر في وكالة رويترز أو الجزيرة باللغة 
العربية. تناول موضوعات من: الجغرافيا، التاريخ، السياسة، الاقتصاد، 
العلوم، والشؤون الدولية.

التزم بالخصائص التركيبية التالية:
- لا تقل عن 12 جملة عن ترتيب الفعل-الفاعل-المفعول (VSO) حيث 
  يبدأ الفعل الجملة
- لا تقل عن 10 جمل تحتوي على تراكيب إضافية (مثل "رئيس الوزراء 
  البريطاني" أو "مجلس الأمن الدولي")
- لا تقل عن 8 جمل تحتوي على جملة اسمية مع خبر
- لا تقل عن 8 جمل تحتوي على جملة موصولية بـ "الذي" أو "التي" 
  أو "الذين"
- استخدم التشكيل (الحركات) على الكلمات الرئيسية عند الإمكان

يجب أن تتراوح كل جملة بين 18 و26 كلمة. اكتب الجمل فقط، جملة 
واحدة في كل سطر، بدون أرقام أو عناوين أو تعليقات. لا تستخدم 
العامية أو أي لهجة محلية.
```
<br>

––––––JAPANESE––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/ja.txt```
```
日本語のウィキペディア記事のスタイルで、正確に50文を作成してください。
地理・科学・歴史・文化・技術・経済などの百科事典的なトピックを
扱ってください。

以下の文法的特徴を意識して、構造に多様性を持たせてください：
- 少なくとも15文は関係節を含むこと（例：「〜た＋名詞」の形）
- 少なくとも10文は理由や条件を表す接続助詞を含むこと
  （「ため」「ので」「から」「ば」「と」など）
- 少なくとも10文は名詞化構造を含むこと
  （「〜こと」「〜の」で終わる節）
- 少なくとも8文は複文構造（二つ以上の節を含む）であること
- すべての文でSOV語順を維持し、述語は文末に置くこと
- 助詞（が、を、に、で、は、から、まで等）を自然に使用すること

各文は40〜65文字程度（スペースなし）の長さにしてください。
体言止めは避け、すべての文を述語で終わらせてください。
番号・見出し・余分なコメントは不要です。1行に1文だけ出力して
ください。
```
<br>

––––––FRENCH––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/fr.txt```
```
Génère exactement 50 phrases en français dans le style d'articles 
Wikipédia et de journaux de référence comme Le Monde. Les sujets 
doivent couvrir : la géographie, les sciences, l'histoire, la 
politique, la culture, et la technologie.

Introduis de la variété syntaxique en respectant les contraintes 
suivantes :
- Au moins 15 phrases doivent contenir une proposition relative 
  (introduite par "qui", "que", "dont", "lequel", etc.)
- Au moins 10 phrases doivent contenir une proposition subordonnée 
  circonstancielle (causale avec "parce que"/"car", temporelle avec 
  "lorsque"/"quand", ou concessive avec "bien que"/"même si")
- Au moins 10 phrases doivent contenir un groupe nominal complexe 
  avec au moins deux modificateurs (adjectifs ou compléments du nom)
- Au moins 8 phrases doivent être à la voix passive
- Mélange les temps : présent de vérité générale, passé composé, 
  imparfait, et passé simple pour les faits historiques

Chaque phrase doit contenir entre 16 et 24 mots. N'utilise pas de 
listes, titres, numéros ou dialogues. Fournis uniquement les phrases, 
une par ligne, sans aucun texte supplémentaire.
```
<br>

––––––TURKISH––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/tr.txt```
```
Türkçe haber metni üslubunda, Hürriyet veya Milliyet gazetelerindeki 
haberlere benzer şekilde tam olarak 50 cümle yaz. Konu alanları şunları 
kapsamalı: siyaset, coğrafya, bilim, ekonomi, tarih ve teknoloji.

Aşağıdaki dilbilgisel özellikleri mutlaka yansıt:
- En az 15 cümlede sıfat-fiil (participle) kullanımı olsun 
  (örn. "-an/-en", "-dik/-dığı", "-acak/-eceği" ekleriyle)
- En az 10 cümlede zarf-fiil (converb) bağlantısı olsun 
  (örn. "-arak/-erek", "-ince/-unca", "-dığında" ile)
- En az 10 cümlede ilgeç grubu olsun (sonra, önce, göre, için, 
  ile, kadar, rağmen gibi edatlar)
- En az 8 cümlede yüklem başa getirilmiş edilgen yapı olsun 
  ("-ılır/-ilir", "-ldı/-ldi" ekleriyle)
- Tüm cümlelerde SOV söz dizimini koru — yüklem her zaman en sonda

Her cümle 10 ile 18 kelime uzunluğunda olmalı. Madde işaretleri, 
numaralandırma veya başlık kullanma. Yalnızca cümleleri yaz, 
her satıra bir cümle gelecek şekilde, hiçbir ek açıklama olmadan.
```
<br>

––––––MANDARIN CHINESE––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/zh.txt```
```
请以中文维基百科文章的风格，写出恰好50个句子。主题应涵盖：地理、
科学、历史、文化、经济和技术等百科知识领域。

请确保句子在句法结构上具有以下多样性：
- 至少15个句子包含关系从句（使用"的"字结构修饰名词，
  例如"他发现的规律"）
- 至少10个句子包含连动结构（两个或多个动词短语串联，
  例如"他走进房间拿起文件开始阅读"）
- 至少10个句子包含状语从句（使用"因为/所以"、"虽然/但是"、
  "如果/就"、"当……时"等关联词）
- 至少8个句子使用把字句或被字句
- 适当使用体标记（了、着、过）来表达动作状态

每个句子应在30至50个汉字之间（不含标点）。使用简体中文。
不要使用列表、标题、编号或对话。只输出句子，每行一句，
不要有任何额外说明或空行。
```
<br>

––––––RUSSIAN––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/ru.txt```
```
Напиши ровно 50 предложений на русском языке в стиле качественной 
российской журналистики — уровня «Коммерсантъ» или «Российской газеты». 
Темы: политика, наука, история, экономика, международные отношения, 
культура и технологии.

Соблюдай следующие синтаксические требования:
- Не менее 15 предложений должны содержать придаточные предложения 
  с союзами «который/которая/которые», «что», «когда», «если», 
  «хотя», «поскольку», «чтобы»
- Не менее 10 предложений должны содержать причастный оборот 
  (действительный или страдательный)
- Не менее 10 предложений должны содержать деепричастный оборот
- Не менее 8 предложений должны быть построены в пассивном залоге 
  (с использованием кратких причастий или возвратных глаголов)
- Используй свободный порядок слов — не ограничивайся только SVO; 
  чередуй OVS, VSO и другие порядки там, где это стилистически уместно

Каждое предложение должно содержать от 15 до 23 слов. Не используй 
списки, заголовки, нумерацию и диалоги. Выводи только предложения, 
по одному на строке, без каких-либо пояснений.
```
<br>

––––––FINNISH––––––– <br>
– Store in ```data/llm-data/llm-raw/LLMNAME/fi.txt```
```
Kirjoita täsmälleen 50 lausetta suomeksi, jotka edustavat erilaisia 
tekstilajeja: uutisteksti, tietosanakirjatyyli ja asiateksti. 
Aiheita voivat olla: maantiede, historia, tiede, politiikka, 
kulttuuri, talous ja teknologia.

Noudata seuraavia kieliopillisia vaatimuksia, jotka tekevät 
lauseista luonnollista suomea:
- Vähintään 15 lausetta sisältää sivulauseen käyttäen konjunktioita 
  "joka", "että", "kun", "jos", "vaikka", "koska" tai "jotta"
- Vähintään 10 lausetta sisältää partisiippirakenteen 
  (esim. "tehty päätös", "meneillään oleva hanke")
- Vähintään 10 lausetta sisältää genetiiviattribuutin 
  monimutkaisen nominaalilausekkeen osana 
  (esim. "Euroopan unionin jäsenvaltioiden hallitukset")
- Vähintään 8 lausetta on passiivissa 
  (esim. "päätettiin", "on havaittu", "tehtiin")
- Käytä monipuolisesti eri sijamuotoja: erityisesti partitiivia, 
  genetiiviä, allatiivia ja elatiivia luontevissa yhteyksissä
- Älä käytä puhekieltä tai slängiä

Jokainen lause tulee olla 12–20 sanan mittainen. Älä käytä 
luettelomerkkejä, numeroita tai otsikoita. Tulosta ainoastaan 
lauseet, yksi per rivi, ilman mitään ylimääräistä tekstiä.
```
<br>
