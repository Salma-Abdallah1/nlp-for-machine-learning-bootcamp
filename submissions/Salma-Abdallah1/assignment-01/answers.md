ASSIGNMENT 1

# NLP Foundations

Natural Language Processing

Student name: Salma Abdallah Mohamud

GitHub username: Salma-Abdallah1



## 1. Natural Language Processing

Natural Language Processing (NLP) is a field of Artificial Intelligence (AI) that enables computers to process, analyse, interpret and generate human language. It combines ideas from linguistics, computer science and statistics. NLP systems work with written text, spoken language or both. Common activities include splitting text into tokens, identifying grammatical structure, extracting meaning, translating languages and generating responses.

NLP is an application area within AI. Machine Learning (ML) is one important approach used to build NLP systems: a model learns patterns from examples instead of relying only on rules written by a programmer. However, NLP is not limited to machine learning; some systems also use dictionaries, linguistic rules or combinations of approaches.

| Concept | Main role |
| --- | --- |
| Artificial Intelligence (AI) | The broad field of building systems that perform tasks associated with human intelligence. |
| Machine Learning (ML) | An approach in which systems learn patterns from data and use them to make predictions or decisions. |
| Natural Language Processing (NLP) | The area of AI concerned specifically with human language. |

### Real-life example: spam detection

An email service may automatically move suspicious messages into a spam folder. NLP processing can split the email into words and other tokens and convert its text into numerical features. A supervised ML model is trained on examples labelled “spam” or “not spam”. When a new email arrives, the model uses the learned patterns to predict its category.

In this example, AI describes the overall goal of automating a useful decision; NLP processes the human-written email; and ML learns from labelled examples. The components work together, but they have different roles.

## 2. Core Text-Data Terms

The following terms describe common units and properties used when preparing text for NLP.

| Term | Meaning |
| --- | --- |
| Corpus | A collection of text documents assembled for analysis or model development. |
| Document | One item within a corpus, such as an article, review, email or social-media post. |
| Token | A unit produced by text processing, often a word, punctuation mark or subword. |
| Vocabulary | The set of distinct tokens identified in a corpus. |
| Feature | A measurable input property derived from the text and supplied to a model. |
| Label | The target category or answer that a supervised model is trained to predict. |

### Worked example: a small sentiment dataset

Imagine a corpus containing four customer reviews. Each review is one document. A simple word-level tokenizer could produce the following tokens: “adeeg”, “fiican”, “buu”, “xumaa”, “waan”, and “jeclahay”. The vocabulary is the set of unique tokens found across all four reviews.

| Document | Example review | Label |
| --- | --- | --- |
| 1 | Adeeg fiican ayaan helay. | Positive |
| 2 | Adeeggu wuu xumaa. | Negative |
| 3 | Waan jeclahay adeeggan. | Positive |
| 4 | Adeeggu ma fiicna. | Negative |

For this dataset, the corpus is all four reviews; a document is one review; tokens are the smaller text units; the vocabulary contains the unique tokens; a feature could be the frequency or TF-IDF weight of “adeeg”; and the label is Positive or Negative. The feature is information used as model input, while the label is the answer the model is expected to learn to predict.

A second Somali-language example is a collection of news articles labelled Health, Sports or Business. The complete collection is the corpus, each article is a document, and its assigned news topic is the label.

## 3. Common NLP Tasks

NLP tasks can be distinguished by what a system receives as input and what it produces as output.

| Task | Input | Output | Example |
| --- | --- | --- | --- |
| Text classification | A complete text or document | One category or label | Classifying a Somali news article as Politics or Sports. |
| Sequence labeling | A sequence of tokens | A label for each token | Marking a person’s name or a location in a sentence. |
| Search and similarity | A query and a document collection | Ranked documents or similarity scores | Finding Somali articles relevant to a search query. |
| Text generation | A prompt, context or source text | New natural-language text | Generating a Somali summary or chatbot response. |

### Text classification

Text classification assigns a complete text to one or more predefined categories. For example, a system may receive a Somali news article and predict “Ciyaaro” (Sports) or “Siyaasad” (Politics). The output is a category rather than a newly written paragraph.

### Sequence labeling

Sequence labeling assigns a label to each token in a sequence. Named-entity recognition is one example: in “Mogadishu waa magaalo”, a system can identify “Mogadishu” as a location. Part-of-speech tagging is another example, assigning grammatical labels such as noun, verb or adjective to individual words.

### Search and similarity

An information-retrieval system compares a user’s query with a collection of documents and returns the most relevant results, usually in ranked order. For example, a user could search Somali news articles using a Somali-language query.

### Text generation

Text generation produces new language based on an input prompt or context. A summarisation system may receive a long Somali article and generate a shorter version that preserves its main points. A chatbot generates a response to a user’s question.

## 4. Supervised and Unsupervised Learning

Supervised learning uses training examples that include both input data and a known target label. The model learns a relationship between the input and the correct output, then uses that relationship to predict labels for new examples. Unsupervised learning uses data without supplied target labels; the algorithm looks for patterns or structure in the data.

| Aspect | Supervised learning | Unsupervised learning |
| --- | --- | --- |
| Training data | Inputs with known labels | Inputs without target labels |
| Main goal | Predict a defined output | Discover structure or patterns |
| Example | Classifying email as spam or not spam | Grouping similar news articles into clusters |
| Somali application | Predicting a news article’s topic | Grouping Somali social-media posts by theme |

### Supervised example

Suppose a Somali news dataset contains articles manually labelled Health, Sports or Business. A classifier learns from the labelled examples. When it receives a new article that was not part of training, it predicts one of the learned categories. The labels are necessary because they provide the target answers against which the model learns.

### Unsupervised example

A researcher collects thousands of Somali social-media posts without assigning topics. A clustering algorithm, such as K-means, can group posts with similar numerical text features. One cluster may contain posts about football, another about health and another about politics. The researcher did not provide those topic labels in advance; they interpret the groups after the algorithm finds patterns.

### Why labels matter

Labels matter in supervised learning because the model needs examples of the desired answers. Without labels such as “spam” and “not spam”, it cannot learn to predict that particular distinction from supervised examples. Unsupervised learning does not require target labels because its purpose is to explore similarities, clusters or other structures rather than reproduce a known answer.

## 5. Numerical Text Representation

Most traditional machine-learning algorithms operate on numerical data. They calculate quantities such as distances, weights, probabilities and gradients. Raw words and sentences are not directly usable by many of these algorithms, so text is converted into numerical features. Different methods preserve different information, such as word presence, frequency, order or semantic relationships.

### Example: Bag-of-Words

Bag-of-Words (BoW) creates a vocabulary and represents each document as a vector. Each position corresponds to a vocabulary word; the value records whether the word appears or how many times it occurs.

Suppose the vocabulary is:

['caafimaad', 'ciyaaro', 'ganacsi', 'warka']

The sentence “Warka caafimaad” can be represented using binary word presence as follows:

| caafimaad | ciyaaro | ganacsi | warka |
| --- | --- | --- | --- |
| 1 | 0 | 0 | 1 |

The vector [1, 0, 0, 1] tells the model that “caafimaad” and “warka” appear, while “ciyaaro” and “ganacsi” do not. A classifier can use such vectors to learn associations between words and categories.

### Main limitation

Bag-of-Words ignores word order and much of the grammatical structure. For example, “The dog bites the man” and “The man bites the dog” contain the same words and therefore can produce the same word-frequency vector, even though their meanings are different. BoW can also create large, sparse vectors when a corpus has a very large vocabulary. As a result, it may lose context and require substantial storage for many features.

## 6. Challenges for Somali NLP

Somali is often described as a low-resource language in NLP. Compared with high-resource languages such as English, fewer large digital text collections, manually annotated datasets, language-specific tools and evaluation benchmarks are available. This makes it harder to train, test and compare reliable Somali-language systems.

### Limited annotated datasets

Many NLP applications need examples labelled by people. A news classifier needs articles tagged by topic, while an offensive-language detector needs posts labelled according to clear annotation guidelines. Creating these datasets requires time, language expertise and quality control. The Somali information-retrieval corpus developed by Badel, Zhong, Tai and Zhou (2023) contains 2,335 documents and was created to address the shortage of dedicated Somali retrieval resources.

### Morphological complexity and word forms

Somali words can take different forms through grammatical and word-formation processes. If a system treats every surface form as an unrelated token, it may fail to connect forms that share a root or meaning. This can affect search, classification and other tasks. Lemmatization and morphology-aware processing can help, but they require suitable linguistic resources and evaluation data.

### Dialect variation

Somali includes varieties such as Maxaa Tiri and Maay. A model trained mainly on one variety may perform less effectively on another. If the training data under-represents a dialect, speakers of that variety may receive poorer results. This is both a technical coverage issue and a fairness concern.

### Mixed-language and informal text

Online Somali communication may mix Somali with English or Arabic, alongside abbreviations, emojis, numbers and inconsistent spelling. A tokenizer or classifier may treat different spellings of the same word as unrelated features. Code-switching and informal writing therefore make text normalisation and reliable interpretation more difficult.

These challenges are connected: limited data makes it harder to represent dialects, word forms and informal usage. Improving Somali NLP requires more diverse datasets, clear annotation practices, language-aware preprocessing and evaluation across different speakers and contexts.

## 7. Case Study: Somali News Classification

A relevant case study is Mohamed Mohamud Ali’s 2026 research paper, “Resource-efficient Somali news classification using TF-IDF and linear SVM: a supervised baseline on a curated news corpus”, published in Scientific Reports. The study investigates how a machine-learning system can automatically organise Somali news articles by topic.

### Task

The task is supervised text classification. The system receives a complete Somali news article and predicts one of eight topic categories: Caafimaad (Health), Ciyaaro (Sports), Dagaal (Conflict), Diini (Religion), Ganacsi (Business), Madadaalo (Entertainment), Siyaasad (Politics) or Tiknoolajiyad (Technology).

### Dataset

The researchers used a manually curated corpus of 7,240 Somali news articles collected from BBC Somali and VOA Somali. Each article was assigned one of the eight topic labels. These labels make the dataset suitable for supervised learning.

### Method

The researchers converted article text into word-level Term Frequency–Inverse Document Frequency (TF-IDF) unigram features. TF-IDF gives greater weight to words that are important in a particular document but less common across the full collection. The final classifier was a Linear Support Vector Machine (Linear SVM), a supervised algorithm used to separate examples into categories.

### Findings

The best Linear SVM configuration achieved 94.20% accuracy on a stratified 80/20 holdout test. Repeated stratified holdout testing produced mean accuracy of 93.11%, while stratified five-fold cross-validation produced mean accuracy of 93.20%. The paper also reports that the pipeline was computationally lightweight and did not require GPU acceleration.

### Connection to NLP foundations

This study demonstrates the relationship between NLP and machine learning. NLP processing converts Somali articles into numerical TF-IDF features, while supervised machine learning uses labelled examples to learn the relationship between those features and the news categories. The input is an article and the output is a predefined topic label, so the study directly illustrates text classification.

### Supporting Somali NLP research

A complementary study by Badel, Zhong, Tai and Zhou (2023) developed a Somali information-retrieval corpus containing 2,335 documents and evaluated pseudo-relevance feedback for query expansion. It demonstrates a different NLP task: retrieving relevant documents for a query. Together, the two studies show how Somali-language resources can support both classification and information retrieval.

## References

1. Ali, M. M. (2026). Resource-efficient Somali news classification using TF-IDF and linear SVM: A supervised baseline on a curated news corpus. Scientific Reports. https://doi.org/10.1038/s41598-026-68159-5

1. Badel, A., Zhong, T., Tai, W., & Zhou, F. (2023). Somali Information Retrieval Corpus: Bridging the Gap between Query Translation and Dedicated Language Resources. Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing, 7463–7469. https://doi.org/10.18653/v1/2023.emnlp-main.462

1. Mohamed, S. (2020). Using machine learning to build POS tagger for under-resourced language: The case of Somali. International Journal of Information Technology, 12, 717–729. https://doi.org/10.1007/s41870-020-00480-2

1. Scielo. (2024). Definition and uses of artificial intelligence, machine learning, and natural language processing. https://www.scielo.sa.cr/scielo.php?script=sci_arttext&pid=S1409-47032024000100533

1. Lexicon and rule-based word lemmatization approach for the Somali language. (2023). arXiv. https://arxiv.org/abs/2308.01785

1. Benchmarking explainable offensive language detection in Somali with human-annotated rationales. (2026). Scientific Reports. https://www.nature.com/articles/s41598-026-53781-0

1. Somali dialect identification in low-resource settings using machine learning and deep learning. (2026). Discover Data. https://doi.org/10.1007/s44248-026-00109-y
