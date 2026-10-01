# AI Course Recommendation System 🎓

An AI-powered **Content-Based Course Recommendation System** that recommends suitable online courses based on a user's **skills and interests**.

The system uses **TF-IDF** to represent course text and **Cosine Similarity** to measure how well a user's profile matches available courses. It also includes a simple **Knowledge Graph** connecting:

**User → Skills/Interests → Topics → Courses**

---

## 🚀 Project Overview

The goal of this project is to build a personalized learning recommendation system using Natural Language Processing (NLP) and similarity-based recommendation techniques.

A user enters skills and interests such as:

```text
Skills:
Python, Machine Learning, Data Analysis, Statistics

Interests:
Artificial Intelligence, Data Science
```

The system then:

1. Builds a text profile for the user.
2. Converts the user profile and course information into TF-IDF vectors.
3. Calculates Cosine Similarity between the user and every course.
4. Returns the **Top 5 most relevant courses**.
5. Displays the similarity score for each recommendation.
6. Generates a Knowledge Graph connecting the user, skills, topics, and recommended courses.

---

## ✨ Features

- Content-Based Recommendation System
- TF-IDF Vectorization
- Cosine Similarity
- Top 3–5 course recommendations
- Similarity scores
- Course rating and difficulty level
- User skills and interests as input
- Knowledge Graph visualization
- Interactive Gradio UI
- Built and tested in Google Colab

---

## 📊 Dataset

The project uses a **Coursera courses dataset** containing course information such as:

- Course Name
- University
- Difficulty Level
- Course Rating
- Course URL
- Course Description
- Skills

The original dataset contains **3,522 rows**. After duplicate removal, the working dataset contains **3,424 courses**.

### Data Cleaning

The preprocessing pipeline includes:

- Duplicate removal
- Course Rating conversion to numeric
- Handling non-numeric `"Not Calibrated"` ratings
- Text normalization
- Lowercasing
- HTML removal
- URL removal
- Special-character removal
- Whitespace normalization

The dataset was checked for missing values in the main text fields used by the recommender.

---

## 🧠 Recommendation Method

### 1. Feature Construction

The following information is combined into one text representation:

```text
Course Name
+ Skills
+ Course Description
+ Difficulty Level
```

### 2. TF-IDF

TF-IDF (Term Frequency–Inverse Document Frequency) converts course text into numerical vectors.

```python
TfidfVectorizer(
    stop_words="english",
    max_features=5000
)
```

The final TF-IDF matrix contains:

```text
3424 courses × 5000 features
```

### 3. Cosine Similarity

Cosine Similarity measures the similarity between the user's profile and every course:

```python
cosine_similarity(user_vector, tfidf_matrix)
```

The courses with the highest similarity scores are selected as recommendations.

---

## 🕸️ Knowledge Graph

The project also represents relationships between the user and recommended courses using a graph.

### Structure

```text
User
 ├── Python
 │     └── Programming
 │             └── Course
 │
 ├── Machine Learning
 │     └── Artificial Intelligence
 │             └── Course
 │
 └── Data Analysis
       └── Data Science
               └── Course
```

The graph is generated using **NetworkX** and visualized with **Matplotlib**.

---

## 🖥️ Interactive UI

The project includes an interactive **Gradio** interface.

The user can enter:

- Skills
- Interests

and click:

**Recommend Courses**

The interface displays:

- Top recommended courses
- University
- Difficulty Level
- Course Rating
- Similarity Score
- Knowledge Graph

---

## 🛠️ Technologies

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Scikit-learn | TF-IDF and Cosine Similarity |
| NetworkX | Knowledge Graph |
| Matplotlib | Graph visualization |
| Gradio | Interactive UI |
| Google Colab | Development environment |

---

## 📁 Project Structure

```text
AI-Course-Recommendation/
│
├── AI_Course_Recommendation.ipynb
├── README.md
├── requirements.txt
└── screenshots/
    ├── ui.png
    ├── recommendations.png
    └── knowledge_graph.png
```

> Add your actual notebook and screenshots to the repository using the filenames above.

---

## ▶️ How to Run

### Option 1 — Google Colab

1. Open the notebook in Google Colab.
2. Run the cells in order.
3. Install the required libraries if needed:

```bash
pip install -r requirements.txt
```

4. Run the recommendation pipeline.
5. Launch the Gradio interface.

### Option 2 — Local Environment

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd AI-Course-Recommendation
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Then open the notebook:

```bash
jupyter notebook
```

---

## 📌 Example

### User Input

```text
Skills:
Python, Machine Learning, Data Analysis, Statistics

Interests:
Artificial Intelligence, Data Science
```

### Example Output

```text
1. What is Data Science?
   Similarity Score: 0.4397

2. Data Science for Business Innovation
   Similarity Score: 0.4378

3. Exploratory Data Analysis
   Similarity Score: 0.4375

4. Introduction to Data Science in Python
   Similarity Score: 0.4180

5. Introduction to Applied Machine Learning
   Similarity Score: 0.4151
```

*Similarity values may change depending on preprocessing, dataset version, and user input.*

---

## 🎯 Learning Objectives

This project demonstrates practical understanding of:

- Data Cleaning
- Text Preprocessing
- Feature Engineering
- NLP fundamentals
- TF-IDF
- Cosine Similarity
- Content-Based Recommendation
- Knowledge Graph Representation
- Data Visualization
- Interactive AI/ML interfaces

---

## 🔮 Future Improvements

Possible extensions include:

- Semantic embeddings using Transformer models
- Sentence-BERT based recommendations
- Hybrid recommendation using content and ratings
- Better automatic topic extraction
- User preference history
- Personalized difficulty-level filtering
- Recommendation explanations
- Deployment as a full web application

---

## 👨‍💻 Project

**AI Course Recommendation System**

Built with Python, NLP, Machine Learning, and Knowledge Graph techniques.
