# H&M Seasonal Campaign – Sentiment Analysis (BUS2503 / AI for Business)

This repository contains the case study and replication materials for:

> **H&M Seasonal Campaign – Sentiment Analysis**  
> Course: BUS2503 – AI for Business  
> Instructor: Dr Veliota Drakopoulou

Students use this package to:

- Explore a labelled H&M‑style sentiment dataset  
- Run a ready‑made Python sentiment pipeline  
- Recreate the analysis in KNIME with a no‑code / low‑code workflow  
- Read the full case study and answer the handout questions

---

## 1. Repository contents

All files in the root folder:

- **`Sentiment Analysis_Veliota_Drakopoulou.pdf`**  
  Full case study and student handout (business context, methods, questions). :contentReference[oaicite:0]{index=0}  

- **`hm_sentiment_reviews.csv`**  
  Sample dataset of social‑media style comments with columns such as:
  - `comment_text` – the text of the comment  
  - `platform` – platform name (Instagram / X / Facebook)  
  - `sentiment` – label: `Positive`, `Neutral`, or `Negative`  

- **`hm_sentiment_analysis_template.py`**  
  Python script template for a TF–IDF + Logistic Regression sentiment model.  
  Students can run this as‑is, then modify it for experiments (e.g. try different models, parameters).

- **`knime_workflow_steps.txt`**  
  Step‑by‑step instructions for building the same sentiment pipeline in **KNIME Analytics Platform** using drag‑and‑drop nodes (no coding).

- **`requirements.txt`**  
  Python package requirements for the template script (e.g. `pandas`, `scikit-learn`, `nltk`, etc.).

- **`README.md`** (this file)  
  Overview and quick‑start instructions.

---

## 2. Quick start for students

### Option A – Run the Python template locally

1. **Download the repository**
   - Click the green **Code** button → **Download ZIP**  
   - Unzip it on your computer.

2. **Open a terminal / command prompt** in the unzipped folder.

3. **Create a virtual environment** (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate    # macOS / Linux
   venv\Scripts\activate.bat   # Windows
Install requirements:
pip install -r requirements.txt
Run the template script:
python hm_sentiment_analysis_template.py
The script will:
Load hm_sentiment_reviews.csv
Split into train/test sets
Build a TF–IDF + Logistic Regression model
Print accuracy, classification report, and confusion matrix
Show example predictions on a few comments
Experiment (for the assignment):
Change model parameters (e.g. max_features, ngram_range)
Try a different classifier (e.g. LinearSVC)
Add extra evaluation or logging
Document what changed and how it affected performance
Option B – Run the Python template in Google Colab
Go to https://colab.research.google.com/ and create a New Notebook.
Upload the following files into Colab:
hm_sentiment_reviews.csv
hm_sentiment_analysis_template.py
requirements.txt (optional)
In the first Colab cell, install requirements:
!pip install -r requirements.txt
In a new cell, either:
Copy‑paste the content of hm_sentiment_analysis_template.py, or
Use:
%run hm_sentiment_analysis_template.py
Run all cells and review the printed metrics and predictions.
Save the notebook (File → Download → .ipynb) for submission.
Option C – Build the workflow in KNIME (no code)
Install KNIME Analytics Platform if you haven’t already:
https://www.knime.com/knime-analytics-platform
Start KNIME and create a new workflow:
KNIME Explorer → right‑click Local → New → New KNIME Workflow…
Name it e.g. HM_Sentiment_NoCode.
Follow the instructions in knime_workflow_steps.txt.
In summary, you will build this pipeline:
CSV Reader → read hm_sentiment_reviews.csv
Strings to Document → convert comment_text to a Document
Text preprocessing nodes:
Case Converter → lowercase
Punctuation Erasure
Number Filter (optional)
Stop Word Filter
Bag of Words Creator
TF or TF–IDF
Document Vector → numeric feature table
Partitioning → train/test split
Logistic Regression Learner → train model
Logistic Regression Predictor → predict on test set
Scorer → confusion matrix and accuracy
Take screenshots of:
Your workflow layout
The Scorer output (accuracy + confusion matrix)
These go into your lab report / assignment.
3. Using ChatGPT as a Gen‑AI assistant (optional / recommended)
Students may (subject to course policy) use ChatGPT as a co‑tutor to:
Ask for explanations (e.g. “Explain TF–IDF in simple terms”).
Ask for help interpreting the confusion matrix.
Ask for ideas on how to improve the model (different parameters or algorithms).
Example prompt:
I have a dataset hm_sentiment_reviews.csv with columns comment_text and sentiment (Positive/Neutral/Negative).
I’m using scikit‑learn with TF–IDF + Logistic Regression.
My accuracy is about 78%.
Suggest three concrete changes I could try (with short code snippets) to potentially improve accuracy.
Important:
Students are still responsible for understanding and being able to explain any code or text they submit.
4. Suggested workflow for students
Read the PDF case study in Sentiment Analysis_Veliota_Drakopoulou.pdf.
Explore the data in Excel/Sheets (look at hm_sentiment_reviews.csv, count labels, read example comments).
Run the Python template or build the KNIME workflow (or both).
Compare results (accuracy, confusion matrix) and discuss strengths/limitations.
(Optional) Use ChatGPT to:
Clarify concepts
Suggest improvements
Classify a small sample of comments and compare with the model
Write your report, answering the questions in the case study handout.
5. License / usage
This repository is intended as a teaching resource for BUS2503 / AI for Business and related courses.
Please credit Dr Veliota Drakopoulou if you reuse or adapt these materials.
Do not include real personally identifiable information in any additional data you add to this repository.
