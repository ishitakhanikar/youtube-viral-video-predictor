# youtube-viral-video-predictor
The goal of this project is to analyze what makes a YouTube video go viral, based on video metadata, and to build a predictive model that estimates the likelihood of virality before uploading
This project not only provides analytical insights into YouTube trending patterns, but also integrates a live prediction prompt where users can enter video details (like title length, tag count, posting time, etc.) and get a Yes/No prediction along with a viral probability score.

📌 Objective

To build a predictive tool that helps estimate whether a YouTube video will go viral before it’s uploaded, based on common metadata attributes.

⸻

📁 Dataset Overview

Dataset: USvideos.csv
	•	Real-world data of trending YouTube videos
	•	Fields include: title, description, tags, views, likes, publish time, etc.

A new is_viral label was created using view count percentiles (top 20%).

⸻

🧹 Data Cleaning
	•	Used a try-except block to handle CSV parsing issues
	•	Filled nulls in text fields using .fillna("")
	•	Converted timestamps and string fields into usable numeric features

⸻

🛠 Feature Engineering

Engineered features included:
	•	title_length
	•	desc_length
	•	tag_count
	•	publish_hour
	•	publish_day
	•	engagement_rate = (likes + dislikes + comments) / views

⸻

📊 Exploratory Data Analysis
	•	Histograms for title and description lengths
	•	Scatterplots for views vs. lengths
	•	Countplots for publish time/day
	•	WordCloud of video titles

⸻

🤖 Predictive Modeling
	•	Trained a RandomForestClassifier using scikit-learn
	•	Handled class imbalance with class_weight="balanced"
	•	Viral = Top 20% of videos by view count
	•	Evaluation using Accuracy, Precision, Recall, and F1-score

⸻

🎯 Live Virality Predictor (Interactive)

The notebook includes a user input prompt where you can enter video metadata and receive a:
	•	Yes/No prediction
	•	Viral probability score (e.g., “7.3% chance of going viral”)

⸻

🧠 What I Learned

Through this project, I learned how to structure a full machine learning pipeline — from raw metadata to a live prediction tool. I gained hands-on experience in feature engineering, class balancing, evaluation beyond accuracy, and aligning user inputs with the model structure using pd.get_dummies(). I also practiced communicating results clearly and making tools usable for both technical and non-technical audiences.
