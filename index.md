
# JokeR
<p align="center">
  <img src="./img/joker.png" width="120" height="142">
</p>

 Home | [CLEF program](program) | [Publications](publications) | [Partners](partners) | [Contest](contest) | [Contact Us](contact) | [Tools](tools) | [CLEF 2022](https://www.joker-project.com/clef-2022/EN/project)
<br>

<br>
  <h1 align="center">CLEF 2023 JOKER Track:</h1>
  <h2 align="center">Automatic Wordplay Analysis</h2> 

### Topic and goals
Humour remains one of the most difficult aspects of intercultural communication. Understanding humour often involves understanding implicit cultural references and/or double meanings, especially in the case of wordplay, which raises not only the question of its (un)translatability, but also how to detect and classify instances of this complex phenomenon. The goal of the JOKER track is to bring together linguists, translators, and computer scientists to create reusable test collections for benchmarking and to explore new evaluation metrics in order to foster work on automatic methods for wordplay interpretation, generation, and translation. Building on lessons learned from the 2022 edition detailed in section 6 of this proposal, we drop Task 2 (wordplay translation in named entities) and simplify Task 1 in order to provide three shared tasks which are more focused in matching the translation process: pun detection, interpretation, then translation. Differently from the state-of-the-art, we will also provide data in French for pun detection and interpretation. We will continue an unshared task with the aim of attracting runs with new use cases, e.g. pun generation or humour evaluation using our corpus. Additionally, we hope to be able to expand our corpus to several other languages.

### Relevance to CLEF and the significance for the field
JOKER lies at the intersection of multiple fields, including natural language processing, machine translation (MT), and human-computer interaction, as well as linguistics, philosophy, and psychology. In the 2022 edition, we focused on machine translation and we constructed a unique English–French parallel corpus of wordplay with 5K parallel one-liner puns and 1.5K parallel instances of wordplay in named entities. We also saw runs based on our corpus for an unshared task for pun generation in order to improve interlocutor engagement in dialog systems. Recent developments in machine learning and artificial intelligence have greatly improved the quality of MT, but puns are often held to be untranslatable, particularly by statistical or neural MT [1], [2], which cannot robustly deal with texts that deliberately disregard or subvert linguistic conventions [3].
<br>
A few monolingual humour corpora do exist, including the datasets created for shared tasks of the International Workshop on Semantic Evaluation (SemEval): #HashtagWars: Learning a Sense of Humor [4], Detection and Interpretation of English Puns [3], Assessing Humor in Edited News Headlines [5], and Hackathon: Detecting and Rating Humor and Offense [6].  Mihalcea et al. [7] collected 16,000 humorous sentences and an equal number of negative samples from news titles, proverbs, the British National Corpus, and the Open Mind Common-Sense dataset. Another dataset contains 2,400 puns and non-puns from news sources, Yahoo!Answers, and proverbs [8], [9]. Most datasets are in English, with some notable exceptions in Italian [10], Russian [11], [12], and Spanish [13]. To the best of our knowledge, the corpus we constructed within the frame of the JOKER Task 3 [14], [15] is the first one for wordplay detection in French.


### Usage scenarios and domains of application
Wordplay is a recurrent feature of literature, advertising, movies, and social conversations.  It is therefore vitally important that natural language processing applications operating on these discourse types be capable of recognising and appropriately dealing with instances of wordplay [14]. As we mentioned before, preserving wordplay in translation might be crucial to understanding the humorous aspect of a sense. Thus, machine translation of wordplay is especially crucial in subtitling. As we demonstrated previously [15], machine translation (including popular engines like DeepL<a href="#note1" id="note1ref"><sup>1</sup></a>) is successful in only 13% of cases. Although it is impossible to resolve such a complex problem at once, we identified three main steps that could bring us closer to the automation of wordplay analysis—namely, wordplay detection, interpretation, and translation. Wordplay detection and interpretation are also important in dialogue systems in order to allow a virtual agent to react properly on the cue of the interlocutor. 
<br>


### Tasks, evaluation setup, and metrics
In this edition, we propose three shared tasks:
* Pun detection in English and French. We will use the corpora which were a side result of JOKER-2022 [15] and the augmented data of SemEval-2017 [16] as well as standard evaluation metrics for binary classification (precision, recall, accuracy)
* Pun location and interpretation in English and French. We will use the extended corpus of JOKER-2022 Task 1. We will evaluate location based on the accuracy and the interpretation based on paronyms and synonyms.
* Pun translation from English to French. We will use the extended version of the corpus of JOKER-2022 Task 3 and we will continue to evaluate the generated translation manually. 
As in 2022, we will run translation contests (eventually into other languages than French—e.g., Spanish, Maltese, and Portuguese) to have more parallel data and we will hire interns in translation to annotate them. We will also extend our corpus with wordplay from literature (e.g. Gödel, Escher, Bach: an Eternal Golden Braid by Douglas Hofstadter) and from video games. We will use untranslated data for the test data in order to enrich our corpus for the future editions. 
We will also welcome unshared runs (pun generation, humour perception, etc.). Further details will be discussed during the break-out session at CLEF-2022. Note that, while our previous JOKER track proved to be very challenging (only 13% of evaluated translations being successful), the larger data set and new evaluation metrics could alleviate this in this round.

### Statistics and lessons learnt
Forty-nine teams registered in 2022. Forty-two users downloaded the data from the server and seven submitted a total of 19 official runs for shared tasks (nine for Task 1: classification and interpretation, four for Task 2: wordplay translation in named entities, and six for Task 3: pun translation). One run was submitted after the deadline for Task 1. Two runs were submitted for the unshared task as well as new classifications proposed by participants. We decided to stop the classification task as the classification we used was not expressive enough due to the corpus construction decisions. We will keep only location and interpretation for the reasons that (1) Task 1 interested a lot of participants, (2) location and interpretation tasks are challenging problems (a few participants were somehow successful), and (3) they are important for downstream processing tasks such as translation. (We found, for example, that even professional translators found it useful to have location and interpretation annotation to evaluate the translations.) We will drop JOKER-2022’s Task 2 as, on the one hand, we did not see variations in the approaches, and on the other hand, the low success rate might be due to a lack of context that is too expensive for us to source. Task 3 allowed us to construct a new homogeneous corpus for pun detection, reducing the limitations of the corpora in the state of the art [15]. This corpus was reused by the French Association for Artificial Intelligence to organise a jam on wordplay generation in French. Thus, in 2023, we will stick to an obvious pipeline useful for pun translation—namely, pun detection, then interpretation, then translation itself. 

### Details of the expected target audience
The  target audience are students and researchers in IR and NLP, but the track is also open for researchers in other domains, including translation. (Several translators and language teachers contacted the lab organisers to have access to the corpus.) The corpus attracted the attention of the [SEA-EU Alliance](https://sea-eu.org/) (from which renewed funding was obtained for 2022–2023) and was used in a class on AI (from which two teams submitted runs). The JOKER organisers were contacted to give another intensive course open for students from the University of Cádiz (Spain), the Université de Bretagne Occidentale in Brest (France), the University of Kiel (Germany), the University of Gdańsk (Poland), the University of Split (Croatia), the University of Malta (Malta), the University of Naples-Parthenope (Italy), the University of Algarve (Portugal), and Nord University (Norway). We will also propose JOKER tasks as projects within the class on AI in the Engineering School in Brest (France). Track organisers from different countries will encourage local communities (in France, Mexico, Poland, Spain, Japan, etc.) to participate in the shared tasks. 
We will disseminate calls and other information about the tasks via the communication service in UBO, the JOKER Google group, various mailing lists (SIGIR, info-ic, madics, clef, ntcir, bulle-i3, bull-ia, ln, nlp-seminar, romip, TRANSLATIO@jiscmail.ac.uk, organisers’ university mailing lists), social networks, organisers’ personal pages, the JOKER project network, and the network of Maison des sciences de l'homme en Bretagne (funding in 2022–2023), as appropriate. We will also advertise the track at CLEF 2022 and ECIR 2023 and other conferences, workshops and local events, including AFIA (French Association for Artificial Intelligence) events. 

### Expected length of the lab session at the conference: half-day
* 45 min invited talk + 15 min for questions
* 1h round table
* 2h30 for presentations (~10 presentations of 15 min)

### References
[1]	H. Ardi, M. A. Hafizh, I. Rezqi, and R. Tuzzikriah, “Can Machine Translations Translate Humorous Texts?”, Humanus, 2022, doi: 10.24036/humanus.v21i1.115698.<br>
[2]	F. Regattin, "Traduction automatique et jeux de mots : l’incursion (ludique) d’un inculte". Brest, Université de Bretagne occidentale, mars 2021. [URL](https://motsmachines.github.io/2021/en/submissions/Mots-Machines-2021_paper_5.pdf)<br>
[3]	T. Miller, "The Punster’s Amanuensis: The Proper Place of Humans and Machines in the Translation of Wordplay", in Proceedings of the Second Workshop on Human-Informed Translation and Interpreting Technology (HiT-IT 2019), sept. 2019, p. 57‑64. doi: 10.26615/issn.2683-0078.2019_007.<br>
[4]	P. Potash, A. Romanov, and A. Rumshisky, " SemEval-2017 Task 6: #HashtagWars: Learning a Sense of Humor ", in Proceedings of the 11th International Workshop on Semantic Evaluation, août 2017, p. 49‑57. doi: 10.18653/v1/S17-2004.<br>
[5]	N. Hossain, J. Krumm, M. Gamon, and H. Kautz, " SemEval-2020 Task 7: Assessing Humor in Edited News Headlines ", in Proceedings of the Fourteenth Workshop on Semantic Evaluation, déc. 2020, p. 746‑758. [En ligne]. Disponible sur: [https://aclanthology.org/2020.semeval-1.98](https://aclanthology.org/2020.semeval-1.98)<br>
[6]	J. A. Meaney, S. Wilson, L. Chiruzzo, A. Lopez, and W. Magdy, " SemEval-2021 Task 7: HaHackathon, Detecting and Rating Humor and Offense ", in Proceedings of the 15th International Workshop on Semantic Evaluation, août 2021, p. 105‑119. doi: 10.18653/v1/2021.semeval-1.9.<br>
[7]	R. Mihalcea and C. Strapparava, " Making Computers Laugh: Investigations in Automatic Humor Recognition ", in Proceedings of Human Language Technology Conference and Conference on Empirical Methods in Natural Language Processing, Vancouver, British Columbia, Canada, oct. 2005, p. 531‑538. [En ligne]. Disponible sur: [https://www.aclweb.org/anthology/H05-1067](https://www.aclweb.org/anthology/H05-1067) <br>
[8]	A. Cattle and X. Ma, " Recognizing Humour using Word Associations and Humour Anchor Extraction ", in Proceedings of the 27th International Conference on Computational Linguistics, Santa Fe, New Mexico, USA, août 2018, p. 1849‑1858. [En ligne]. Disponible sur: [https://www.aclweb.org/anthology/C18-1157](https://www.aclweb.org/anthology/C18-1157)<br>
[9]	D. Yang, A. Lavie, C. Dyer, and E. Hovy, " Humor Recognition and Humor Anchor Extraction ", in Proceedings of the 2015 Conference on Empirical Methods in Natural Language Processing, Lisbon, Portugal, sept. 2015, p. 2367‑2376. doi: 10.18653/v1/D15-1284.<br>
[10]	A. Reyes, D. Buscaldi, and P. Rosso, " An Analysis of the Impact of Ambiguity on Automatic Humour Recognition ", in Text, Speech and Dialogue, Berlin, Heidelberg, 2009, p. 162‑169. doi: 10.1007/978-3-642-04208-9_25.<br>
[11]	V. Blinov, V. Bolotova-Baranova, and P. Braslavski, "Large Dataset and Language Model Fun-Tuning for Humor Recognition", in Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics, Florence, Italy, 2019, p. 4027‑4032. doi: 10.18653/v1/P19-1394.<br>
[12]	A. Ermilov, N. Murashkina, V. Goryacheva, and P. Braslavski, "Stierlitz Meets SVM: Humor Detection in Russian", in Artificial Intelligence and Natural Language, Cham, 2018, p. 178‑184. doi: 10.1007/978-3-030-01204-5_17.<br>
[13]	S. Castro, L. Chiruzzo, A. Rosá, D. Garat, and G. Moncecchi, "A Crowd-Annotated Spanish Corpus for Humor Analysis", in Proceedings of the Sixth International Workshop on Natural Language Processing for Social Media, Melbourne, Australia, juill. 2018, p. 7‑11. doi: 10.18653/v1/W18-3502.<br>
[14]	L. Ermakova et. al., "CLEF Workshop JOKER: Automatic Wordplay and Humour Translation", in Advances in Information Retrieval, vol. 13186, M. Hagen, S. Verberne, C. Macdonald, C. Seifert, K. Balog, K. Nørvåg, et V. Setty, Éd. Cham: Springer International Publishing, 2022, p. 355‑363. doi: 10.1007/978-3-030-99739-7_45.<br>
[15]	L. Ermakova et al., "Overview of the CLEF 2022 JOKER Task 3: Pun Translation from English into French", in Proceedings of the Working Notes of CLEF 2022: Conference and Labs of the Evaluation Forum, 2022.<br>
[16]	T. Miller, C. Hempelmann, and I. Gurevych, "SemEval-2017 Task 7: Detection and Interpretation of English Puns", in Proceedings of the 11th International Workshop on Semantic Evaluation           (SemEval-2017), Vancouver, Canada, 2017, p. 58‑68. doi: 10.18653/v1/S17-2005.<br><br><br>
<a id="note1" href="#note1ref"><sup>1</sup></a>: *DeepL translator. Accessed on 17th July 2022. [URL](https://www.deepl.com/translator)*

## How to Cite
If you extend or use this work, please cite the [paper](https://link.springer.com/chapter/10.1007/978-3-030-99739-7_45) where it was introduced:
```
Ermakova, L., Miller, T., Puchalski, O., Regattin, F., Mathurin, É., Araújo, S., 
Bosser, A.-G., Borg, C., Bokiniec, M., Corre, G. L., Jeanjean, B., Hannachi, R., 
Mallia, Ġ., Matas, G., & Saki, M. (2022). 
CLEF Workshop JOKER: Automatic Wordplay and Humour Translation. 
In M. Hagen, S. Verberne, C. Macdonald, C. Seifert, K. Balog, K. Nørvåg, & V. Setty (Eds.), 
Advances in Information Retrieval (Vol. 13186, pp. 355–363). Springer International Publishing. 
https://doi.org/10.1007/978-3-030-99739-7_45
```
[Paper](https://doi.org/10.1007/978-3-030-99739-7_45)

[Dowload .BIB](./BibTex/joker_ecir_2022.bib)


<p>
<em>This project has received a government grant managed by the National Research Agency under the program "Investissements d'avenir" with the Reference ANR-19-GURE-0001</em>
</p>
<p>
<em>JokeR is supported by The Human Science Institute in Brittany (MSHB)</em>
</p>
<div align="center">
  <a href="https://www.mshb.fr"><img src="img/mshb.jpg" height="120"></a>
  <a href="https://sea-eu.org/?lang=fr"><img src="img/sea-eu.png" height="120"></a>
  <a href="https://www.gouvernement.fr/le-programme-d-investissements-d-avenir"><img src="img/investissement-avenir.jpeg" height="120"></a>
</div>
<br />
<div align="center">
  <a href="https://clef2022.clef-initiative.eu/index.php"><img src="img/clef2023.png" height="90"></a> 
</div>

