# 🚀 Capstone Project: End-to-End AI System (1-Week Intensive)

**Duration:** 1 Week  
**Deliverable:** Working MVP + Demo + Presentation  
**Expectation Level:** High — this is a compressed, production-style sprint

---

## 📌 Overview

### What is this Capstone?

You will build a **complete AI system from scratch in one week**, following the full development lifecycle:

> Data → Model → Evaluation → MVP

This is a **high-intensity sprint** designed to simulate real-world constraints.

The capstone project is your opportunity to demonstrate everything you've learned by building a **real-world AI system from scratch**. You'll go through the complete AI development lifecycle: from identifying a problem and collecting data, to training models, evaluating performance, and deploying a working MVP.

**This is NOT a toy project.** Your capstone should:
- Solve a **real problem** you care about
- Use **real data** (not pre-cleaned datasets like MNIST)
- Result in a **working system** others can use
- Demonstrate **technical depth** across the entire course

### Learning Objectives

By completing this capstone, you will:
- ✅ Apply the full AI pipeline (data → deployment)
- ✅ Make informed decisions about model selection
- ✅ Handle messy, real-world data
- ✅ Evaluate and iterate on model performance
- ✅ Build and deploy a usable system
- ✅ Communicate technical work to non-technical audiences

---

## ⚠️ Critical Framing

This is **not a simplified project**.

You are expected to:
- Move quickly
- Make strong technical decisions
- Prioritize effectively
- Deliver a working system under pressure

---

## 🎯 Learning Objectives

- Apply the **full AI pipeline**
- Work with **messy, real-world data**
- Train and evaluate models under time constraints
- Build a **usable MVP**
- Communicate results clearly

---

## ⏱️ The Reality of This Sprint

You do NOT have time to:
- Perfect your data
- Try 5+ models
- Over-engineer architecture

You DO have time to:
- Build something real
- Make tradeoffs
- Deliver a working system

---

## 📅 1-Week Execution Plan

### Day 1 — Problem + Data Lock
- Define problem (1–2 sentences max)
- Select dataset (**must commit today**)
- Perform quick EDA
- Identify risks (missing data, imbalance, etc.)

### Day 2 — Data Prep + Baseline
- Clean data (minimal but correct)
- Train/test split
- Build baseline model

### Day 3 — Strong Model
- Train improved model
- Compare vs baseline

### Day 4 — Evaluation + Error Analysis
- Evaluate on test set
- Identify 5–10 failure cases
- Explain failures

### Day 5 — MVP Build
- Build UI (Streamlit / Gradio / Notebook)

### Day 6 — Polish
- Fix bugs
- Improve UX

### Day 7 — Demo
- Demo + presentation

---

## 🧠 Required Pipeline

1. Data sourcing  
2. EDA  
3. Data cleaning  
4. Baseline model  
5. Improved model  
6. Evaluation  
7. Error analysis  
8. MVP  

---

## Project Requirements

### Must-Haves

Your capstone MUST include:

✅ **Real-World Problem**
- Clearly defined use case
- Measurable success criteria
- Feasible in 4 weeks

✅ **Real Data**
- Not pre-cleaned benchmark datasets
- At least 500+ samples (more is better)
- Properly split (train/val/test)

✅ **Complete Pipeline**
- Data collection and cleaning
- EDA and feature engineering
- Model training and evaluation
- Error analysis
- Working deployment (MVP)

✅ **Technical Depth**
- Apply techniques from at least 3 different course units
- Demonstrate understanding of model selection
- Show iterative improvement
- **Strongly encouraged:** Integrate RAG if applicable to your problem

✅ **Working MVP**
- Can be notebook, web app, API, or Streamlit app
- Others can interact with it
- Handles edge cases gracefully

✅ **Documentation**
- README explaining project
- Code comments
- Notebook with EDA and experiments

### Nice-to-Haves (Bonus)

🌟 **RAG Integration** (Highly Recommended!)
- Implement RAG for knowledge-grounded responses
- Use Chroma or FAISS vector database
- Show retrieval quality analysis
- Demonstrate improvement over non-RAG baseline

🌟 **Advanced Techniques**
- Fine-tuning pre-trained models
- Ensemble methods
- Hybrid search (keyword + semantic)
- A/B testing different approaches

🌟 **Production Readiness**
- Deployed on cloud (Hugging Face Spaces, Streamlit Cloud, etc.)
- Error handling and logging
- User feedback mechanism

🌟 **Impact**
- Feedback from real users
- Comparison with existing solutions
- Quantified improvement

---

## The AI Pipeline (9 Steps)

You must follow the complete AI development pipeline:

### 1. Data Source Identification
**Goal:** Find where to get your data

**Questions to answer:**
- What data do I need to solve this problem?
- Is the data publicly available or do I need to collect it?
- What are the legal/ethical considerations?

**Common Sources:**
- Public datasets: Kaggle, Hugging Face Datasets, UCI ML Repository
- APIs: Twitter, Reddit, News APIs
- Web scraping: BeautifulSoup, Scrapy
- Company data: If working with a real organization

---

### 2. Data Collection
**Goal:** Gather raw data

**Tasks:**
- Download datasets or scrape websites
- Use APIs to fetch data
- Handle rate limits and pagination
- Save raw data (never modify original!)

**Tools:**
- `requests`, `beautifulsoup4`, `scrapy` for scraping
- `tweepy`, `praw` for social media APIs
- `datasets` library for Hugging Face datasets

**Example:**
```python
from datasets import load_dataset

# Load dataset
dataset = load_dataset("imdb")

# Or scrape data
import requests
from bs4 import BeautifulSoup

response = requests.get("https://example.com")
soup = BeautifulSoup(response.content, 'html.parser')
```

---

### 3. Exploratory Data Analysis (EDA)
**Goal:** Understand your data

**Questions to answer:**
- What does the data look like?
- Are there missing values or outliers?
- What's the distribution of labels/targets?
- Are there interesting patterns or correlations?

**Tasks:**
- Statistical summary (mean, median, std)
- Visualizations (histograms, scatter plots, word clouds)
- Class imbalance check
- Identify data quality issues

**Tools:**
- `pandas`, `numpy` for analysis
- `matplotlib`, `seaborn` for visualization
- `wordcloud` for text data

---

### 4. Data Cleaning
**Goal:** Prepare data for modeling

**Tasks:**
- Handle missing values (impute or drop)
- Remove duplicates
- Fix inconsistencies (typos, formatting)
- Text cleaning (for NLP): lowercase, remove special chars, etc.
- Outlier handling
- Create train/val/test splits (70/15/15 or 80/10/10)

**Important:**
- Document all cleaning decisions
- Keep raw data unchanged
- Save cleaned data separately

**Example:**
```python
# Text cleaning
text = text.lower()
text = re.sub(r'[^a-z0-9\s]', '', text)

# Train/test split
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

---

### 5. Picking the Correct Model
**Goal:** Choose architecture appropriate for your task

**Decision Framework:**

| Task Type | Recommended Models | When to Use |
|-----------|-------------------|-------------|
| **Text Classification** | DistilBERT, RoBERTa | Sentiment, topic classification |
| **Sequence-to-Sequence** | T5, BART | Summarization, translation |
| **Question Answering** | RAG + LLM | Knowledge-based Q&A |
| **Image Classification** | ResNet, EfficientNet | Object recognition |
| **Time Series** | LSTM, Transformer | Forecasting |
| **Tabular Data** | Random Forest, XGBoost | Structured data |

**Start Simple:**
1. **Baseline:** Simple model (logistic regression, rules)
2. **Mid-complexity:** Pre-trained model (DistilBERT)
3. **Advanced:** Fine-tuned or custom architecture

**Resources:**
- [Hugging Face Model Hub](https://huggingface.co/models) - Pre-trained models
- [Papers with Code](https://paperswithcode.com/) - State-of-the-art models by task

---

### 6. Train/Fine-Tune the Model
**Goal:** Build and train your model

**Tasks:**
- Implement baseline model
- Load pre-trained model (if using)
- Define training loop
- Set hyperparameters (learning rate, batch size, epochs)
- Track training metrics (loss, accuracy)
- Save checkpoints

**Important:**
- Use validation set for hyperparameter tuning
- Save best model (not just last model)
- Track experiments (use wandb or mlflow)

**Example (Fine-tuning with Transformers):**
```python
from transformers import AutoModelForSequenceClassification, Trainer

model = AutoModelForSequenceClassification.from_pretrained(
    "distilbert-base-uncased",
    num_labels=2
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=train_dataset,
    eval_dataset=val_dataset
)

trainer.train()
```

---

### 7. Evaluate the Model
**Goal:** Measure performance objectively

**Metrics to Use:**

| Task | Primary Metrics | When to Use |
|------|----------------|-------------|
| Classification | Accuracy, F1, Precision, Recall | Imbalanced data needs F1 |
| Regression | MAE, RMSE, R² | Depends on error tolerance |
| Generation | BLEU, ROUGE, Human eval | Summarization, translation |
| Retrieval | Precision@K, Recall@K, MRR | Search, recommendation |

**Important:**
- Always use **test set** (unseen data) for final evaluation
- Compare to baseline
- Statistical significance (if possible)

**Example:**
```python
from sklearn.metrics import classification_report, confusion_matrix

# Get predictions
predictions = model.predict(X_test)

# Evaluate
print(classification_report(y_test, predictions))
print(confusion_matrix(y_test, predictions))
```

---

### 8. Error Analysis
**Goal:** Understand where and why your model fails

**Tasks:**
- Identify misclassified examples
- Find patterns in errors (common themes?)
- Check for bias (does it fail on certain demographics?)
- Analyze edge cases

**Questions to Ask:**
- Which examples does the model get wrong?
- Are errors random or systematic?
- Are there data quality issues in errors?
- Does the model need more training data in certain areas?

**Example:**
```python
# Find misclassified examples
errors = X_test[predictions != y_test]

# Analyze error patterns
for i, example in enumerate(errors[:10]):
    print(f"Example {i}:")
    print(f"Text: {example}")
    print(f"True: {y_test[i]}, Predicted: {predictions[i]}")
    print()
```

**Next Steps:**
- Collect more data for problematic cases
- Adjust model architecture
- Try different preprocessing
- Add more features

---

### 9. Deploying the Model & Building an MVP
**Goal:** Make your model usable by others

**MVP Requirements:**
- User can interact with model (input → output)
- Simple interface (doesn't need to be fancy)
- Handles errors gracefully
- Fast enough for demo (<5 seconds per prediction)
- **If using RAG:** Show document retrieval in action

**Deployment Options:**

| Platform | Difficulty | Best For | Cost |
|----------|-----------|----------|------|
| **Jupyter Notebook** | Easy | Quick demos | Free |
| **Streamlit** | Easy | Interactive web apps, **RAG demos** | Free |
| **Gradio** | Easy | ML demos | Free |
| **Hugging Face Spaces** | Medium | Sharing models, **RAG systems** | Free tier |
| **FastAPI + Docker** | Hard | Production APIs | Pay for hosting |

**Recommended for RAG Projects: Streamlit**
```python
import streamlit as st
from your_rag_system import rag_chain

st.title("My RAG-Powered Q&A System")

question = st.text_input("Ask a question:")
if st.button("Search & Answer"):
    # Show retrieved documents
    with st.expander("📄 Retrieved Documents"):
        docs = retriever.invoke(question)
        for i, doc in enumerate(docs, 1):
            st.write(f"**Chunk {i}:**")
            st.write(doc.page_content[:200] + "...")
    
    # Show answer
    answer = rag_chain.invoke(question)
    st.success(f"**Answer:** {answer}")
```

**RAG Demo Checklist:**
- [ ] Shows document retrieval (not just final answer)
- [ ] Displays similarity scores (optional but cool!)
- [ ] Handles "not found" gracefully
- [ ] Fast response (<3 seconds)
- [ ] Clear which documents were used

**Deployment Checklist:**
- [ ] Model loads successfully
- [ ] Handles empty input
- [ ] Handles long input
- [ ] Shows clear output
- [ ] Has instructions for users
- [ ] Runs without errors

---

## 🚫 Constraints

- ≤1 day on cleaning  
- ≤2–3 models  
- No over-engineering  

---

## 🧪 MVP Requirements

- Accept input  
- Return output  
- <5s runtime  

---

## 📦 Deliverables

- GitHub repo  
- README  
- EDA notebook  
- Model code  
- MVP app  
- Presentation  

---

## 🏆 Evaluation Rubric

| Category | Weight |
|----------|--------|
| Problem | 10% |
| Data | 20% |
| Model | 25% |
| Evaluation | 20% |
| MVP | 15% |
| Presentation | 10% |

---

## 🔥 Final Thought

Build fast. Think clearly. Ship something real.

---

## Project Ideas Bank

**Can't think of a project?** Pick from this list of real-world problems:

### 🏥 Healthcare & Wellbeing

1. **Mental Health Chatbot** 🔥 **RAG RECOMMENDED**
   - Build conversational agent for mental health support
   - Dataset: Counseling conversations, Reddit mental health posts, therapy resources
   - Tech: **RAG + LLM** (ground responses in therapeutic techniques), sentiment analysis
   - **RAG Component:** Index mental health resources, CBT techniques, crisis helplines

2. **Medical Report Summarizer** 🔥 **RAG RECOMMENDED**
   - Summarize long medical documents for patients
   - Dataset: Medical papers, clinical notes (use synthetic/public data)
   - Tech: T5, BART, **RAG for medical terminology lookup**
   - **RAG Component:** Medical knowledge base for accurate term definitions

3. **Symptom Checker**
   - Input symptoms → suggest possible conditions
   - Dataset: Medical Q&A datasets
   - Tech: Classification + knowledge base

### 📰 News & Media

4. **Fake News Detector**
   - Classify news articles as real or fake
   - Dataset: Kaggle fake news datasets, political fact-checking sites
   - Tech: DistilBERT, RoBERTa

5. **News Article Summarizer**
   - Generate TL;DR for long articles
   - Dataset: CNN/DailyMail, BBC News
   - Tech: BART, T5

6. **Bias Detector in News**
   - Identify political bias in news articles
   - Dataset: AllSides media bias, News articles
   - Tech: Fine-tuned BERT

### 🛒 E-Commerce & Business

7. **Product Review Analyzer**
   - Analyze product reviews for pros/cons/sentiment
   - Dataset: Amazon reviews, Yelp reviews
   - Tech: Sentiment analysis + aspect extraction

8. **Smart Product Recommender**
   - Recommend products based on user preferences
   - Dataset: Amazon product data, MovieLens
   - Tech: Collaborative filtering + embeddings

9. **Customer Support Chatbot** 🔥 **RAG PERFECT FIT**
   - Answer FAQs about a product/service
   - Dataset: Company FAQ, support tickets, product documentation
   - Tech: **RAG + LLM** (essential for accurate, grounded responses)
   - **RAG Component:** Index FAQs, troubleshooting guides, product manuals

### 📚 Education

10. **Essay Grader**
    - Automatically grade student essays
    - Dataset: Kaggle essay scoring datasets
    - Tech: Regression model + BERT embeddings

11. **Personalized Study Plan Generator**
    - Create study plans based on student performance
    - Dataset: Khan Academy data, quiz results
    - Tech: Recommendation system

12. **Lecture Summarizer**
    - Summarize lecture transcripts/videos
    - Dataset: YouTube lecture transcripts, CourseNotes
    - Tech: Whisper (transcription) + T5 (summarization)

### 🌍 Social Good

13. **Disaster Tweet Classifier**
    - Identify real disaster tweets vs non-disaster
    - Dataset: Kaggle disaster tweets dataset
    - Tech: DistilBERT classification

14. **Hate Speech Detector**
    - Detect and classify hate speech in text
    - Dataset: Hate speech datasets from Kaggle, Twitter
    - Tech: RoBERTa, content moderation

15. **Climate Change News Tracker**
    - Track and summarize climate news
    - Dataset: News APIs (Guardian, NewsAPI)
    - Tech: Web scraping + summarization

### 💼 Professional

16. **Resume Screener**
    - Match resumes to job descriptions
    - Dataset: Kaggle resume datasets
    - Tech: Embedding similarity, classification

17. **Meeting Minutes Generator**
    - Generate meeting summaries from transcripts
    - Dataset: Meeting transcripts (AMI corpus)
    - Tech: Abstractive summarization

18. **Legal Document Q&A** 🔥 **RAG PERFECT FIT**
    - Answer questions about legal documents
    - Dataset: Legal contracts, terms of service, case law
    - Tech: **RAG system** (essential for citation and accuracy)
    - **RAG Component:** Index legal documents, retrieve relevant sections for queries

### 🎨 Creative

19. **Writing Style Transfer**
    - Convert text from formal → casual or vice versa
    - Dataset: Parallel corpora (formal/informal pairs)
    - Tech: Seq2Seq models

20. **Poetry Generator**
    - Generate poems in specific styles
    - Dataset: Poetry Foundation, Kaggle poetry datasets
    - Tech: GPT-2 fine-tuning, prompt engineering

### 🔍 Search & Information

21. **Academic Paper Search Engine** 🔥 **RAG PERFECT FIT**
    - Search research papers by topic/question
    - Dataset: ArXiv papers, Semantic Scholar, PubMed
    - Tech: **Vector search + RAG** (core to functionality)
    - **RAG Component:** Index papers, retrieve relevant sections, generate summaries

22. **Recipe Recommender**
    - Suggest recipes based on ingredients you have
    - Dataset: Recipe datasets (Kaggle, RecipeNLG)
    - Tech: Ingredient matching + embeddings

23. **GitHub Issue Tagger**
    - Auto-tag GitHub issues with labels
    - Dataset: Public GitHub issues
    - Tech: Multi-label classification

### 🎮 Entertainment

24. **Movie Recommendation System**
    - Recommend movies based on user preferences
    - Dataset: MovieLens, IMDb
    - Tech: Collaborative filtering

25. **Game Review Sentiment Analyzer**
    - Analyze game reviews to predict game quality
    - Dataset: Steam reviews, Metacritic
    - Tech: Sentiment analysis + rating prediction

---

---

## Resources

### Datasets

- **[Kaggle Datasets](https://www.kaggle.com/datasets)** - Largest collection, all domains
- **[Hugging Face Datasets](https://huggingface.co/datasets)** - NLP-focused, easy to load
- **[UCI ML Repository](https://archive.ics.uci.edu/ml/)** - Classic ML datasets
- **[Google Dataset Search](https://datasetsearch.research.google.com/)** - Search engine for datasets
- **[Papers with Code Datasets](https://paperswithcode.com/datasets)** - Research datasets

### Pre-Trained Models

- **[Hugging Face Models](https://huggingface.co/models)** - 200K+ pre-trained models
- **[TensorFlow Hub](https://tfhub.dev/)** - Pre-trained TensorFlow models
- **[PyTorch Hub](https://pytorch.org/hub/)** - Pre-trained PyTorch models
- **[ONNX Model Zoo](https://github.com/onnx/models)** - Cross-framework models

### Development Tools

- **[Streamlit](https://streamlit.io/)** - Build web apps in Python
- **[Gradio](https://gradio.app/)** - ML demo interfaces
- **[Jupyter Notebooks](https://jupyter.org/)** - Interactive development
- **[Google Colab](https://colab.research.google.com/)** - Free GPU notebooks
- **[Weights & Biases](https://wandb.ai/)** - Experiment tracking

### Deployment Platforms

- **[Hugging Face Spaces](https://huggingface.co/spaces)** - Free ML app hosting
- **[Streamlit Cloud](https://streamlit.io/cloud)** - Deploy Streamlit apps
- **[Render](https://render.com/)** - Deploy web apps and APIs
- **[Railway](https://railway.app/)** - Simple deployment platform

### Learning Resources

- **[Hugging Face Course](https://huggingface.co/course)** - Free NLP course
- **[Fast.ai](https://www.fast.ai/)** - Practical deep learning
- **[MLOps Guide](https://ml-ops.org/)** - Deployment best practices
- **[Full Stack Deep Learning](https://fullstackdeeplearning.com/)** - Production ML

---

## Submission Guidelines

### What to Submit

Submit all materials via GitHub repository by **end of Week 8**:

1. **Code Repository** (GitHub)
   - All code (notebooks, scripts)
   - Data (if <100MB) or instructions to download
   - Model weights (or link to hosted model)
   - README with setup instructions

2. **Documentation**
   - `README.md`: Project overview, setup, usage
   - `EDA.ipynb`: Exploratory data analysis notebook
   - `EXPERIMENTS.md`: Summary of model experiments and results
   - `DEPLOYMENT.md`: How to run the MVP

3. **Presentation**
   - Slides (PDF or PowerPoint)
   - Demo video (optional, 3-5 minutes)

### README Template

Your README should include:

```markdown
# Project Title

## Problem Statement
[What problem are you solving? Why is it important?]

## Dataset
[Where did you get the data? How much data? Any preprocessing?]

## Methodology
[What models did you try? What was your approach?]

## Results
[What metrics did you achieve? How does it compare to baseline?]

## MVP
[Link to live demo or instructions to run locally]

## Setup Instructions
```bash
pip install -r requirements.txt
python app.py
```

## Future Work
[What would you do with more time?]

## Credits
[Any external code/resources used?]

### GitHub Repository Structure

```
your-capstone-project/
├── README.md
├── requirements.txt
├── data/
│   ├── raw/              # Original data
│   ├── processed/        # Cleaned data
│   └── README.md         # Data documentation
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_baseline.ipynb
│   └── 03_experiments.ipynb
├── src/
│   ├── data_processing.py
│   ├── model.py
│   └── utils.py
├── app.py                # Streamlit/Gradio app
├── models/               # Saved model weights
└── presentation/
    └── slides.pdf
```

---

## Final Checklist

Before demo day, ensure:

**Code & Data**
- [ ] GitHub repo is public and well-organized
- [ ] README has clear setup instructions
- [ ] All notebooks run without errors
- [ ] Data is documented (source, size, splits)

**Model**
- [ ] Baseline model results documented
- [ ] Final model trained and saved
- [ ] Evaluation metrics calculated on test set
- [ ] Error analysis completed

**MVP**
- [ ] MVP is functional (runs without errors)
- [ ] Handles edge cases gracefully
- [ ] Has clear user instructions
- [ ] Response time < 5 seconds

**Presentation**
- [ ] Slides prepared (10-15 slides)
- [ ] Demo practiced (5 minutes)
- [ ] Can explain technical decisions
- [ ] Ready for Q&A

**Submission**
- [ ] GitHub repo URL submitted
- [ ] Demo link submitted (if deployed)
- [ ] Presentation slides uploaded

---