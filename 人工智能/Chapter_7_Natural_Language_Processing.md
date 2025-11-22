# Chapter 7: Natural Language Processing

## Overview

Natural Language Processing (NLP) is a branch of artificial intelligence that focuses on the interaction between computers and human language. It involves developing algorithms and systems that can understand, interpret, and generate human language in a valuable way. This chapter covers the fundamental concepts, techniques, and applications in NLP.

## 1. Introduction to Natural Language Processing

### Definition and Scope

**Natural Language Processing (NLP):** A field of artificial intelligence that focuses on enabling computers to understand, interpret, and generate human language. NLP combines computational linguistics with statistical, machine learning, and deep learning models.

### Challenges in NLP

1. **Ambiguity:** Words can have multiple meanings (polysemy)
2. **Syntax Complexity:** Sentence structure can be complex
3. **Context Dependency:** Meaning often depends on context
4. **Cultural and Domain Variations:** Language varies by culture and domain
5. **Real-time Processing:** Need for efficient processing

## 2. Components of Natural Language Understanding

### 2.1 Morphological Analysis
**Purpose:** Analyze word structure and formation
- **Tokenization:** Breaking text into individual words/tokens
- **Stemming:** Reducing words to their root form (e.g., "running" → "run")
- **Lemmatization:** Converting words to their dictionary form (e.g., "better" → "good")

### 2.2 Syntactic Analysis (Parsing)
**Purpose:** Determine the grammatical structure of sentences
- **Part-of-speech (POS) tagging:** Assign grammatical categories to words
- **Dependency parsing:** Identify grammatical relationships between words
- **Constituency parsing:** Build tree structures showing phrase structure

**Example of Syntactic Analysis:**
```
"Students study AI"

POS tags: Students(Noun) study(Verb) AI(Noun)
Parse tree:
    S
   /|\
  NP VP
 /   /|\
Noun V  NP
 |   |   |
Students study AI
```

### 2.3 Semantic Analysis
**Purpose:** Extract meaning from text
- **Word sense disambiguation:** Determine meaning based on context
- **Named entity recognition (NER):** Identify entities like names, places, organizations
- **Semantic role labeling:** Identify who did what to whom

### 2.4 Pragmatic Analysis
**Purpose:** Understand context and intent
- **Discourse analysis:** Understanding relationships between sentences
- **Speech act theory:** Understanding what speaker is trying to accomplish
- **Context modeling:** Incorporating situational context

## 3. Natural Language Generation

### 3.1 Components
1. **Content determination:** What information to include
2. **Text structuring:** How to organize information
3. **Sentence aggregation:** Combining related elements
4. **Lexical choice:** Selecting appropriate words
5. **Referring expression generation:** Creating appropriate references
6. **Linguistic realization:** Generating grammatical text

### 3.2 Applications
- Text summarization
- Machine translation
- Chatbots and virtual assistants
- Automated report generation

## 4. Key NLP Techniques

### 4.1 Tokenization
**Process:** Breaking text into smaller units (tokens) such as words, phrases, or sentences.

**Types:**
- Word tokenization
- Sentence tokenization
- Subword tokenization (like Byte-Pair Encoding)

### 4.2 Bag of Words (BoW) Model
**Concept:** Represent text as a bag of its words, disregarding grammar and word order
- Creates a vector where each dimension represents a unique word
- Values can be binary, count, or TF-IDF scores

### 4.3 TF-IDF (Term Frequency-Inverse Document Frequency)
**Purpose:** Measure importance of a word in a document relative to a corpus

**Formula:**
```
TF-IDF(t,d) = TF(t,d) × IDF(t)
Where:
- TF(t,d) = (Number of times term t appears in document d) / (Total number of terms in document d)
- IDF(t) = log(Total number of documents / Number of documents containing term t)
```

### 4.4 Word Embeddings
**Purpose:** Represent words as dense vectors in continuous vector space

**Popular Models:**
- **Word2Vec:** Creates word vectors through prediction tasks
- **GloVe:** Global Vectors for Word Representation
- **FastText:** Considers subword information

**Properties of Good Embeddings:**
- Words with similar meanings have similar vectors
- Can capture semantic relationships (King - Man + Woman ≈ Queen)

## 5. Neural Network Models in NLP

### 5.1 Recurrent Neural Networks (RNNs)
**Purpose:** Handle sequential data in NLP tasks
- Maintain hidden state that captures information about previous inputs
- Suitable for tasks like language modeling and machine translation

**Limitations:** Vanishing gradient problem in long sequences

### 5.2 Long Short-Term Memory (LSTM)
**Enhancement:** Special RNN architecture to handle long-term dependencies
- Uses gates (input, forget, output) to control information flow
- Addresses vanishing gradient problem

### 5.3 Transformers
**Revolutionary Architecture:** Based on attention mechanisms rather than recurrence
- **Self-attention:** Each position attends to all positions in previous layer
- **Multi-head attention:** Multiple attention subspaces
- **Positional encoding:** Incorporates sequence position information

**Applications:** BERT, GPT, and other state-of-the-art models

## 6. NLP Tasks and Applications

### 6.1 Text Classification
- Sentiment analysis
- Spam detection
- News categorization

### 6.2 Named Entity Recognition (NER)
- Identify and classify entities (persons, organizations, locations)
- Extract structured information from unstructured text

### 6.3 Machine Translation
- Translate text from one language to another
- Statistical and neural approaches

### 6.4 Question Answering
- Extract answers from documents
- Understanding context and queries

### 6.5 Text Summarization
- Extractive: Select important sentences from source
- Abstractive: Generate new text summarizing content

### 6.6 Speech Recognition and Synthesis
- Automatic Speech Recognition (ASR): Convert speech to text
- Text-to-Speech (TTS): Convert text to spoken language

## 7. Statistical Machine Translation

### 7.1 Approach
Based on statistical models that learn to translate from large bilingual text corpora.

**Core Components:**
- **Translation model:** P(f|e) - probability of foreign sentence f given English sentence e
- **Language model:** P(e) - probability of English sentence being fluent
- **Search algorithm:** Find best translation given models

### 7.2 Process
1. Collect large parallel corpora
2. Align words and phrases statistically
3. Build probabilistic models
4. Use models to translate new sentences

## 8. Deep Learning in NLP

### 8.1 End-to-End Learning
- Neural networks can learn representations directly from data
- No need for manual feature engineering
- Better performance on many tasks

### 8.2 Attention Mechanisms
- Focus on relevant parts of input for each output
- Enable handling of long sequences
- Key component in modern NLP architectures

### 8.3 Pre-trained Models
- **BERT:** Bidirectional Encoder Representations from Transformers
- **GPT:** Generative Pre-trained Transformer
- **T5:** Text-to-Text Transfer Transformer

## 9. Applications of NLP in AI Systems

### 9.1 Chatbots and Virtual Assistants
- Natural conversation interfaces
- Task completion through natural language
- Context management

### 9.2 Information Extraction
- Extract structured data from unstructured text
- Knowledge base construction
- Content analysis

### 9.3 Sentiment Analysis
- Determine sentiment from text
- Customer feedback analysis
- Social media monitoring

### 9.4 Information Retrieval
- Improve search engine results
- Semantic search
- Content recommendation

## 10. Sample Exam Question Analysis (from your exam material)

**Sample Question:** "Know the process of natural language understanding, and will be able to use basic word segmentation and syntactic analysis methods to analyze natural language phrases"

**Key Focus Areas:**
1. **Natural Language Understanding Process:**
   - Morphological analysis (word segmentation)
   - Syntactic analysis (parsing)
   - Semantic analysis
   - Pragmatic analysis

2. **Word Segmentation:**
   - Tokenization methods
   - Handling morphologically rich languages
   - Dealing with compound words

3. **Syntactic Analysis:**
   - Understanding parse trees
   - Part-of-speech tagging
   - Dependency vs. constituency parsing
   - Grammar rules in parsing

## Practice Problems and Solutions

### Problem 1: Part-of-Speech Tagging
**Question:** Tag each word in the sentence "The students study artificial intelligence at the university" with its part of speech.

**Solution:**
- The: Determiner (DT)
- students: Noun (NNS)
- study: Verb (VBP)
- artificial: Adjective (JJ)
- intelligence: Noun (NN)
- at: Preposition (IN)
- the: Determiner (DT)
- university: Noun (NN)

### Problem 2: Syntactic Analysis
**Question:** Draw a simple parse tree for "Students study AI" and identify the constituent parts.

**Solution:**
```
    S (Sentence)
   /|\
  NP VP (Noun Phrase, Verb Phrase)
 /   /|\
Noun V  NP
 |   |   |
Students study AI

Constituents:
- NP (Noun Phrase): "Students"
- VP (Verb Phrase): "study AI"
- NP (Noun Phrase): "AI"
```

### Problem 3: TF-IDF Calculation
**Question:** Calculate TF-IDF for the word "learning" in a document containing 100 words where "learning" appears 5 times, in a corpus of 1000 documents where "learning" appears in 50 documents.

**Solution:**
- TF("learning", doc) = 5/100 = 0.05
- IDF("learning") = log(1000/50) = log(20) ≈ 1.30
- TF-IDF = 0.05 × 1.30 = 0.065

### Problem 4: Ambiguity in NLP
**Question:** Explain the different types of ambiguity in natural language and provide an example of each.

**Solution:**
1. **Lexical ambiguity:** A word has multiple meanings
   - Example: "bank" (financial institution vs. riverbank)
   
2. **Syntactic ambiguity:** The same sentence has multiple parse structures
   - Example: "I saw the man with the telescope" (who has the telescope?)
   
3. **Semantic ambiguity:** Multiple interpretations of meaning
   - Example: "Flying planes can be dangerous" (Is flying dangerous or are planes dangerous?)

4. **Pragmatic ambiguity:** Context-dependent interpretation
   - Example: "Can you pass the salt?" (question about ability vs. request)

### Problem 5: NLP Pipeline
**Question:** Arrange the following NLP processing steps in the correct order for analyzing a sentence: semantic analysis, morphological analysis, word segmentation, syntactic analysis, pragmatic analysis.

**Solution:**
Correct order:
1. Word segmentation (tokenization)
2. Morphological analysis
3. Syntactic analysis
4. Semantic analysis
5. Pragmatic analysis

This follows the typical NLP pipeline from lower-level to higher-level linguistic processing.

## Key Takeaways

- NLP involves multiple levels of linguistic analysis from morphological to pragmatic
- Natural language understanding requires breaking down language into components
- Word segmentation is the first step in most NLP pipelines
- Syntactic analysis determines grammatical structure of sentences
- Modern NLP increasingly relies on neural networks and deep learning
- Statistical methods were foundational, but neural approaches now dominate
- Real-world NLP systems must handle ambiguity and context
- Applications range from translation to information extraction

## Additional Practice Problems

### Advanced Problem 1: Ambiguity Resolution
**Question:** Identify the type of ambiguity in: "Visiting relatives can be tiresome." How would an NLP system address this?

**Solution:**
This is syntactic ambiguity (structural ambiguity). The phrase can be parsed as:
1. "Visiting relatives [can be tiresome]" - relatives who are visiting are tiresome
2. "[Visiting relatives] [can be tiresome]" - the act of visiting relatives is tiresome

An NLP system might address this through:
- Probabilistic parsing to find most likely parse
- Semantic analysis to determine which interpretation makes more sense
- Context analysis from surrounding text
- World knowledge encoded in the system

### Advanced Problem 2: Named Entity Recognition
**Question:** For the sentence "Apple Inc. CEO Tim Cook announced new iPhone models in California," identify all named entities and their types.

**Solution:**
- "Apple Inc." - Organization
- "Tim Cook" - Person
- "iPhone" - Product (sometimes classified under organization/product)
- "California" - Location