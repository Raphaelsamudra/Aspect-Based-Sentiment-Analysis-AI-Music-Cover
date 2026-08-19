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
