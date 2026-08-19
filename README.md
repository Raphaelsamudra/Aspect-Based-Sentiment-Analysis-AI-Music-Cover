# 🎵 Aspect-Based Sentiment Analysis of AI Music Covers

An Aspect-Based Sentiment Analysis (ABSA) project for analyzing YouTube comments related to AI-generated music covers.

This project identifies the sentiment expressed in comments and analyzes the sentiment based on four predefined aspects:

- 🎧 Listener Activity
- 🤖 AI Content & Technology
- 🎵 Music & Audio Quality
- 💬 Evaluation & Opinion

The classification process uses Logistic Regression, with and without SMOTE, to compare model performance when handling class imbalance.

---

## 📌 Project Overview

The development of AI-generated music covers has attracted various reactions from YouTube audiences. Comments may contain opinions about the quality of the music, AI technology, listener reactions, and general evaluations.

A general sentiment analysis only determines whether a comment is positive, neutral, or negative. However, it does not explain **what aspect of the content is being discussed**.

Therefore, this project applies Aspect-Based Sentiment Analysis (ABSA) to identify sentiment at the aspect level.

The analysis consists of several main stages:

1. 📥 Data preparation
2. 🧹 Text preprocessing
3. 🏷️ Aspect identification
4. ✍️ Manual sentiment validation
5. 📊 Dataset splitting
6. 🤖 Sentiment classification using Logistic Regression
7. ⚖️ Handling class imbalance using SMOTE
8. 📈 Model evaluation
9. 📊 Result visualization

---

## 🎯 Research Objectives

The main objectives of this project are:

- To identify aspects discussed in YouTube comments about AI music covers.
- To classify the sentiment associated with each aspect.
- To compare Logistic Regression performance with and without SMOTE.
- To evaluate the classification performance using a confusion matrix and other evaluation metrics.
- To visualize the distribution of aspects and sentiments.

---

## 🧩 Aspect Categories

Four aspects are used in this project.

### 1. 🎧 Listener Activity

This aspect represents comments related to the listener's experience, reactions, engagement, or activities toward the AI music cover.

Examples may include comments about:

- listening experience
- repeated listening
- audience reactions
- enjoyment
- requests or responses from listeners

### 2. 🤖 AI Content & Technology

This aspect represents comments discussing the use, quality, or characteristics of artificial intelligence in music creation.

Examples may include comments about:

- AI technology
- AI-generated vocals
- AI capabilities
- AI implementation
- opinions about the use of AI in music

### 3. 🎵 Music & Audio Quality

This aspect represents comments related to the musical or audio characteristics of the AI cover.

Examples may include comments about:

- vocal quality
- sound quality
- music arrangement
- audio clarity
- melody
- instrumental quality

### 4. 💬 Evaluation & Opinion

This aspect represents general evaluations, judgments, or opinions expressed by viewers.

Examples may include:

- praise
- criticism
- appreciation
- general opinions
- overall evaluation of the AI music cover

---

## 🗂️ Dataset

The project uses YouTube comments related to AI music cover content.

The dataset goes through several processing stages before being used for model training and evaluation.

The main data-related files include:

- `Data_Berasepek`
- `Data_Validasi_Manual`
- `Data_Validasi_Manual_corrected`
- `Hasil_Preprocessing_Data`
- `Hasil_Labeling_Final`
- `Hasil_ABSA`
- `normalisasi`
- `kamuskatabaku`

The manually validated and corrected data is used as an important reference for the sentiment classification process.

---

## 🔄 Data Processing Pipeline

The overall workflow can be summarized as follows:

```text
YouTube Comments
       ↓
Data Preparation
       ↓
Text Preprocessing
       ↓
Normalization
       ↓
Aspect Identification
       ↓
Manual Sentiment Validation
       ↓
Dataset Splitting
       ↓
Logistic Regression
       ↓
 ┌───────────────┐
 │               │
 ↓               ↓
Without SMOTE   With SMOTE
 │               │
 └───────┬───────┘
         ↓
Model Evaluation
         ↓
Visualization

```
# 🧹 Text Preprocessing

Text preprocessing is performed before the comments are used in the sentiment classification process.

The purpose of preprocessing is to reduce unnecessary variations in the text and prepare the comments for subsequent analysis.

The preprocessing stage includes the preparation and transformation of the original comment data into a cleaner representation.

The project also uses a supporting Indonesian standard-word dictionary:

`kamuskatabaku.xlsx`

This file is used as a supporting resource for the normalization process.

The preprocessing outputs are stored separately from the final analysis results to maintain a clear research workflow.

# 🔤 Text Normalization

Text normalization is performed to standardize words before they are used in further analysis.

This stage is particularly useful for handling informal or non-standard forms commonly found in YouTube comments.

The normalization process uses the Indonesian standard-word dictionary:

`kamuskatabaku.xlsx`

The dictionary is used as a supporting resource to identify and convert non-standard words into their standardized forms.

The resulting normalized data is then used in the subsequent aspect identification and sentiment analysis stages.

# 🏷️ Aspect Identification

After text normalization, each comment is analyzed to determine the aspect being discussed.

The analysis uses four predefined aspect categories:

1. 🎧 **Listener Activity**
2. 🤖 **AI Content & Technology**
3. 🎵 **Music & Audio Quality**
4. 💬 **Evaluation & Opinion**

The aspect identification process associates each relevant comment with one or more predefined aspects based on the content of the comment.

The aspect categories are used as the basis for the subsequent sentiment analysis.

The aspect distribution generated from this process is provided in:

`aspect_distribution.csv`

The corresponding visualization is provided in:

`aspect_distribution.png`

# ✍️ Manual Validation

Manual validation is performed to validate the sentiment labels generated during the analysis process.

A sample of comments is manually reviewed and assigned sentiment labels based on their actual content.

The sentiment categories used during manual validation are:

- 🟢 **Positive**
- ⚪ **Neutral**
- 🔴 **Negative**

The manually validated data is maintained in:

`Data_Validasi_Manual`

A corrected version of the validation data is also maintained in:

`Data_Validasi_Manual_corrected`

The corrected validation dataset is used as the reference dataset for the subsequent sentiment classification and model evaluation.

The distribution of the manually validated sentiment labels is visualized in:

`sentiment_label_distribution.png`

# 😊 Sentiment Classification

The validated comments are classified into three sentiment categories:

| Sentiment | Description |
|-----------|-------------|
| 🟢 **Positive** | Expresses a positive reaction, appreciation, or opinion |
| ⚪ **Neutral** | Does not clearly express a positive or negative sentiment |
| 🔴 **Negative** | Expresses a negative reaction, criticism, or opinion |

The sentiment labels obtained from the validation process are used as the reference labels for the machine learning classification process.

The sentiment distribution can be examined through:

`sentiment_label_distribution.png`

The sentiment distribution for each predefined aspect is provided in:

`sentiment_per_aspect.png`

# ✂️ Dataset Splitting

The validated dataset is divided into training and testing datasets for the machine learning process.

The **training dataset** is used to train the Logistic Regression model, while the **testing dataset** is used to evaluate the model's performance on previously unseen data.

The dataset splitting process is performed before the model training stage.

The distribution of the training and testing datasets is visualized in:

`dataset_split.png`

This separation allows the model to be trained and evaluated using different portions of the dataset.

# 🤖 Machine Learning

## Logistic Regression

**Logistic Regression** is used as the main machine learning algorithm for sentiment classification.

The model is trained to classify comments into three sentiment categories:

- 🟢 **Positive**
- ⚪ **Neutral**
- 🔴 **Negative**

The Logistic Regression model is evaluated under two conditions:

### Without SMOTE

The model is trained using the original class distribution of the training dataset.

### With SMOTE

SMOTE is applied to the training dataset before the Logistic Regression model is trained.

The two approaches are compared to examine the classification performance with and without handling class imbalance.

# ⚖️ SMOTE

**SMOTE (Synthetic Minority Over-sampling Technique)** is used to address class imbalance in the training dataset.

SMOTE generates synthetic samples for minority classes based on existing minority-class observations.

The purpose of applying SMOTE is to create a more balanced class distribution in the training data and reduce potential bias toward the majority class.

In this project, Logistic Regression is evaluated using two approaches:

```text
Logistic Regression
       │
       ├── Without SMOTE
       │
       └── With SMOTE
```

SMOTE is applied to the training dataset only.

The testing dataset is kept separate from the oversampling process so that model performance can be evaluated using unseen data.

# 📊 Model Evaluation

The performance of the Logistic Regression model is evaluated using several classification metrics.

The evaluation metrics used in this project include:

- 📈 **Accuracy**
- 🎯 **Precision**
- 🔍 **Recall**
- ⭐ **F1-score**
- 🔲 **Confusion Matrix**

These metrics are used to evaluate the model's ability to classify sentiment into positive, neutral, and negative categories.

The evaluation is performed separately for the models with and without SMOTE.

The numerical evaluation results are stored in the `results/` directory.

The main evaluation files are:

`evaluation_smote.csv`

`summary_no_smote.csv`

# 🔲 Confusion Matrix

A confusion matrix is used to evaluate and visualize the classification performance of the Logistic Regression model.

The confusion matrix shows the number of correctly and incorrectly classified samples for each sentiment category.

The evaluation considers three sentiment categories:

- 🟢 **Positive**
- ⚪ **Neutral**
- 🔴 **Negative**

The repository contains confusion matrix visualizations for both modeling approaches:

- 🤖 **Logistic Regression with SMOTE**
- 🤖 **Logistic Regression without SMOTE**

The resulting visualizations are stored in the `results/` directory:

`confusion_matrix_smote.png`

`confusion_matrix_no_smote.png`

These visualizations allow the classification performance of the two approaches to be compared across the predefined aspects.

# 📈 Data Visualization

Several visualizations are generated to support the interpretation of the analysis results.

These visualizations provide an overview of the aspect distribution, sentiment distribution, sentiment by aspect, dataset splitting, and frequently occurring words.

---

## 📊 Aspect Distribution

The aspect distribution shows the distribution of comments across the predefined aspect categories.

The result is available in:

`aspect_distribution.csv`

The corresponding visualization is:

`aspect_distribution.png`

---

## 😊 Sentiment Label Distribution

The sentiment label distribution shows the number of comments classified into the three sentiment categories:

- 🟢 **Positive**
- ⚪ **Neutral**
- 🔴 **Negative**

The visualization is provided in:

`sentiment_label_distribution.png`

---

## 💬 Sentiment per Aspect

The sentiment per aspect visualization shows the distribution of sentiment associated with each predefined aspect.

The visualization helps illustrate how positive, neutral, and negative sentiments are distributed across the different aspects.

The result is provided in:

`sentiment_per_aspect.png`

---

## ☁️ Sentiment Word Cloud

A word cloud is used to visualize frequently occurring words in the analyzed sentiment data.

The visualization is provided in:

`wordcloud_sentiment.png`

---

## 📊 Dataset Split

The dataset split visualization shows the distribution of the training and testing datasets used in the machine learning process.

The visualization is provided in:

`dataset_split.png`

# 📁 Repository Structure

The repository is organized into several directories and files to separate the analysis code, supporting data, and generated results.

```text
Aspect-Based-Sentiment-Analysis-AI-Music-Cover/
│
├── 📓 Code_ANALISIS_AI_COVER.ipynb
│
├── 📂 data/
│   └── 📄 kamuskatabaku.xlsx
│
├── 📂 results/
│   ├── 📊 aspect_distribution.csv
│   ├── 📊 aspect_distribution.png
│   ├── 📊 evaluation_smote.csv
│   ├── 📊 summary_no_smote.csv
│   ├── 📊 sentiment_aspect_summary.csv
│   ├── 🔲 confusion_matrix_smote.png
│   ├── 🔲 confusion_matrix_no_smote.png
│   ├── 📈 dataset_split.png
│   ├── 😊 sentiment_label_distribution.png
│   ├── 💬 sentiment_per_aspect.png
│   └── ☁️ wordcloud_sentiment.png
│
└── 📄 README.md
```

### 📓 `Code_ANALISIS_AI_COVER.ipynb`

The main Jupyter Notebook containing the implementation of the analysis, including data processing, aspect identification, sentiment classification, Logistic Regression, SMOTE, model evaluation, and visualization.

### 📂 `data/`

Contains supporting data used during the analysis process.

The repository includes:

`kamuskatabaku.xlsx`

This file contains the Indonesian standard-word dictionary used as a supporting resource during text normalization.

### 📂 `results/`

Contains the numerical results and visualizations generated from the analysis.

The directory includes model evaluation results, aspect distributions, sentiment distributions, confusion matrices, dataset split visualization, and word cloud visualization.

### 📄 `README.md`

Contains the documentation of the project, including the project overview, methodology, tools, repository structure, and instructions for using the notebook.

# 📂 Directory Description

## `data/`

The `data/` directory contains supporting data used during the analysis process.

The repository includes:

`kamuskatabaku.xlsx`

This file contains the Indonesian standard-word dictionary used as a supporting resource during the text normalization process.

The complete YouTube comment dataset and manually validated datasets are not included in the public repository.

---

## `results/`

The `results/` directory contains the selected numerical results and visualizations generated during the analysis.

The directory includes:

- 📊 Aspect distribution
- 📈 Model evaluation results
- 😊 Sentiment label distribution
- 💬 Sentiment distribution by aspect
- 🔲 Confusion matrices
- 📊 Dataset split visualization
- ☁️ Sentiment word cloud

---

## `Code_ANALISIS_AI_COVER.ipynb`

This is the main Jupyter Notebook used to implement the analysis workflow.

The notebook contains the processing and modeling stages, including:

- 🧹 Text preprocessing
- 🔤 Text normalization
- 🏷️ Aspect identification
- ✍️ Manual validation
- 😊 Sentiment classification
- 🤖 Logistic Regression
- ⚖️ SMOTE
- 📊 Model evaluation
- 📈 Data visualization

---

## `README.md`

This file contains the documentation for the project, including the project overview, analysis workflow, tools and technologies, repository structure, and instructions for using the notebook.

# 🛠️ Tools & Technologies

This project uses the following tools and technologies for data processing, machine learning, evaluation, visualization, and repository management.

## 🐍 Python

**Python** is used as the main programming language for implementing the data processing and machine learning workflow.

---

## 📓 Jupyter Notebook

**Jupyter Notebook** is used as the development environment for implementing and documenting the analysis.

The main analysis notebook is:

`Code_ANALISIS_AI_COVER.ipynb`

---

## 📦 Python Libraries

### 🐼 Pandas

Used for data manipulation, data cleaning, dataset processing, and handling tabular data.

### 🔢 NumPy

Used for numerical operations and data processing.

### 🤖 Scikit-learn

Used for machine learning and model evaluation, including:

- Logistic Regression
- Dataset splitting
- Feature processing
- Classification metrics
- Confusion Matrix

### ⚖️ imbalanced-learn

Used to implement **SMOTE (Synthetic Minority Over-sampling Technique)** for handling class imbalance in the training dataset.

### 📊 Matplotlib

Used to generate data visualizations and analytical charts.

### 📈 Seaborn

Used to generate statistical visualizations, including confusion matrix visualizations.

### ☁️ WordCloud

Used to generate the word cloud visualization from the analyzed text data.

### 📄 OpenPyXL

Used to read and process Excel files used in the project.

---

## 📑 Microsoft Excel

Microsoft Excel is used to support dataset preparation, manual validation, data inspection, and correction of research data.

---

## 🐙 GitHub

**GitHub** is used as the repository platform for storing and documenting the project source code, supporting files, and selected analysis results.

# 🚀 How to Use

Follow the steps below to run the analysis notebook.

## 1. Clone the Repository

Clone this repository to your local computer using Git:

```bash
git clone https://github.com/Raphaelsamudra/Aspect-Based-Sentiment-Analysis-AI-Music-Cover.git
```

Then enter the project directory:

```bash
cd Aspect-Based-Sentiment-Analysis-AI-Music-Cover
```

---

## 2. Install Python

Make sure that **Python 3.x** is installed on your computer.

Check the installed Python version using:

```bash
python --version
```

---

## 3. Install Required Libraries

Install the required Python libraries using:

```bash
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn wordcloud openpyxl jupyter
```

The libraries are required for data processing, text analysis, machine learning, SMOTE, evaluation, and visualization.

---

## 4. Start Jupyter Notebook

Start Jupyter Notebook by running:

```bash
jupyter notebook
```

A Jupyter Notebook page will open in your web browser.

---

## 5. Open the Analysis Notebook

Open the main notebook:

`Code_ANALISIS_AI_COVER.ipynb`

The notebook contains the main implementation of the analysis workflow.

---

## 6. Prepare the Required Data

Make sure the supporting files are placed in the appropriate directories.

The Indonesian standard-word dictionary is located at:

`data/kamuskatabaku.xlsx`

The complete YouTube comment dataset and manually validated datasets are not included in the public repository.

---

## 7. Run the Notebook

Run the notebook cells sequentially from the beginning to the end.

The main workflow consists of:

```text
📥 Data Preparation
        ↓
🧹 Text Preprocessing
        ↓
🔤 Text Normalization
        ↓
🏷️ Aspect Identification
        ↓
✍️ Manual Validation
        ↓
😊 Sentiment Classification
        ↓
✂️ Dataset Splitting
        ↓
🤖 Logistic Regression
        ↓
⚖️ SMOTE / Without SMOTE
        ↓
📊 Model Evaluation
        ↓
📈 Data Visualization
```

---

## 8. View the Results

The generated results and visualizations are available in the:

`results/`

directory.

The results include model evaluation files, aspect distribution, sentiment distribution, confusion matrices, dataset split visualization, sentiment per aspect, and word cloud visualization.

# 📋 Result Files

The following files contain the main numerical results and visualizations generated during the analysis.

| File | Description |
|------|-------------|
| `evaluation_smote.csv` | Evaluation results for the Logistic Regression model using SMOTE |
| `summary_no_smote.csv` | Summary of the Logistic Regression model without SMOTE |
| `sentiment_aspect_summary.csv` | Summary of sentiment distribution based on aspect |
| `aspect_distribution.csv` | Distribution of comments across the predefined aspects |
| `aspect_distribution.png` | Visualization of aspect distribution |
| `dataset_split.png` | Visualization of the training and testing dataset split |
| `sentiment_label_distribution.png` | Visualization of the overall sentiment label distribution |
| `sentiment_per_aspect.png` | Visualization of sentiment distribution for each aspect |
| `confusion_matrix_smote.png` | Confusion matrix for the Logistic Regression model using SMOTE |
| `confusion_matrix_no_smote.png` | Confusion matrix for the Logistic Regression model without SMOTE |
| `wordcloud_sentiment.png` | Word cloud visualization of the analyzed sentiment data |

# 🔬 Reproducibility

The repository is organized to make the analysis workflow easier to understand and reproduce.

The general reproduction process is:

```text
1. Clone the repository
        ↓
2. Install the required libraries
        ↓
3. Prepare the required data
        ↓
4. Open the Jupyter Notebook
        ↓
5. Run the notebook sequentially
        ↓
6. Review the generated results
```

The main analysis is provided in:

`Code_ANALISIS_AI_COVER.ipynb`

The notebook contains the main stages of the analysis, from data preprocessing and aspect identification to sentiment classification, model evaluation, and visualization.

Because some research datasets are not included in the public repository, complete reproduction of the original analysis may require access to the original research data.

# ⚠️ Data Availability

The public repository does not include the complete raw YouTube comment dataset or the full manually validated dataset.

The repository focuses on providing the main analysis notebook, supporting resources, and selected analysis results.

The publicly available materials include:

- 📓 Analysis notebook
- 📖 Indonesian standard-word dictionary
- 📊 Selected numerical results
- 📈 Data visualizations
- 📝 Project documentation

The manually validated and corrected datasets are retained separately as part of the research data and are not publicly distributed through this repository.

# 👤 Author

**Raphaelsamudra**

This repository contains the implementation and supporting materials for an academic project on Aspect-Based Sentiment Analysis of YouTube comments related to AI music covers.

---

⭐ Thank you for visiting this repository!

README.md
│
├── 🧹 Text Preprocessing
├── 🔤 Text Normalization
├── 🏷️ Aspect Identification
├── ✍️ Manual Validation
├── 😊 Sentiment Classification
├── ✂️ Dataset Splitting
├── 🤖 Machine Learning
├── ⚖️ SMOTE
├── 📊 Model Evaluation
├── 🔲 Confusion Matrix
├── 📈 Data Visualization
├── 📁 Repository Structure
├── 📂 Directory Description
├── 🛠️ Tools & Technologies
├── 🚀 How to Use
├── 📋 Result Files
├── 🔬 Reproducibility
├── ⚠️ Data Availability
└── 👤 Author
