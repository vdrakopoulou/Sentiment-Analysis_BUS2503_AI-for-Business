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
  Full case study and student handout (business context, methods, questions).

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

:contentReference[oaicite:0]{index=0}
::contentReference[oaicite:1]{index=1}

Sources

You said:
the isntructions do not read good....please include everything in a copy code

ChatGPT said:

Thought for 45 seconds

ChatGPT said:
# H&M Seasonal Campaign – Sentiment Analysis  
BUS2503 / AI for Business

This repository contains the **case study** and **teaching materials** for a sentiment analysis project based on H&M social‑media comments.

Students will:

- Read the business case
- Explore a labelled sentiment dataset
- Run a ready‑made Python pipeline
- Rebuild the pipeline in KNIME (no coding)
- Write up results for assessment

---

## 1. Files in this folder

- `Sentiment Analysis_Veliota_Drakopoulou.pdf`  
  Full case study and student handout (business background, questions, marking expectations).

- `hm_sentiment_reviews.csv`  
  Sample dataset of H&M‑style social‑media comments.  
  Key columns:
  - `comment_text` – text of the comment  
  - `platform` – Instagram / X / Facebook (may be missing)  
  - `sentiment` – label: `Positive`, `Neutral`, or `Negative`

- `hm_sentiment_analysis_template.py`  
  Python template script that:
  - Loads `hm_sentiment_reviews.csv`
  - Splits into train/test
  - Builds a TF–IDF + Logistic Regression model
  - Prints accuracy, classification report, confusion matrix
  - Shows example predictions

- `knime_workflow_steps.txt`  
  Step‑by‑step instructions for building the same sentiment pipeline in **KNIME Analytics Platform** using drag‑and‑drop nodes (no code).

- `requirements.txt`  
  List of Python packages needed by the template script (e.g. `pandas`, `scikit-learn`, `nltk`).

---

## 2. Quick start for students

### Step 1 – Get the files

1. On GitHub, click the green **Code** button → **Download ZIP**.
2. Unzip the folder on your computer.
3. You should see the files listed above.

### Step 2 – Read the case study

1. Open `Sentiment Analysis_Veliota_Drakopoulou.pdf`.
2. Read:
   - Business context (H&M campaign)
   - Data description
   - Lab / assignment tasks
3. Note what you are expected to **submit** for your course.

---

## 3. Option A – Run the Python template locally (PC / Mac)

> This option is for students who have Python installed (or are happy to install it).

1. Open a **terminal / command prompt** in the unzipped folder (where the files live).

2. (Optional but recommended) Create and activate a virtual environment:

   ```bash
   python -m venv venv
   # macOS / Linux
   source venv/bin/activate
   # Windows
   venv\Scripts\activate.bat
Install the required libraries:
pip install -r requirements.txt
Run the template script:
python hm_sentiment_analysis_template.py
The script will:
Load hm_sentiment_reviews.csv
Train a TF–IDF + Logistic Regression model
Print accuracy, a classification report, and a confusion matrix
Print some example comments with predicted sentiment
For the assignment, you can:
Change TF–IDF settings (e.g. max_features, ngram_range)
Try a different classifier (e.g. LinearSVC)
Re‑run and compare results (note any improvement or decline)
4. Option B – Run the Python template in Google Colab (no installation)
Recommended if you don’t want to install Python on your own machine.
Go to https://colab.research.google.com and create a New notebook.
In the left “Files” panel, click Upload and upload:
hm_sentiment_reviews.csv
hm_sentiment_analysis_template.py
requirements.txt (optional but helpful)
In the first Colab cell, install requirements:
!pip install -r requirements.txt
In a new cell, either:
Copy‑paste the contents of hm_sentiment_analysis_template.py, or
Run:
%run hm_sentiment_analysis_template.py
Check the printed accuracy and reports.
Save your notebook for submission: File → Download → Download .ipynb.
5. Option C – Rebuild the pipeline in KNIME (visual / no‑code)
This option is for students who prefer a drag‑and‑drop interface instead of code.
Download and install KNIME Analytics Platform:
https://www.knime.com/knime-analytics-platform
Open KNIME and create a new workflow:
KNIME Explorer → right‑click Local → New → New KNIME Workflow…
Name it something like HM_Sentiment_NoCode.
Follow knime_workflow_steps.txt carefully.
In summary, you will build a pipeline:
CSV Reader → read hm_sentiment_reviews.csv
Strings to Document → convert comment_text to a Document
Text preprocessing nodes:
Case Converter (lowercase)
Punctuation Erasure
Number Filter (optional)
Stop Word Filter
Bag of Words Creator
TF or TF–IDF
Document Vector
Partitioning → train/test split
Logistic Regression Learner (or similar)
Logistic Regression Predictor
Scorer → accuracy + confusion matrix
Take screenshots of:
Your KNIME workflow layout
The Scorer view (confusion matrix + accuracy)
These screenshots usually form part of your lab report.
6. Using ChatGPT as a helper (if allowed by your course)
If your instructor permits the use of ChatGPT, you can use it as a co‑tutor, for example:
To explain concepts:
“Explain TF–IDF in simple words with a short example.”
“What does a confusion matrix show in sentiment analysis?”
To help debug code:
Paste the error message and the relevant part of your script and ask:
“What does this error mean and how can I fix it?”
To suggest improvements:
“My Logistic Regression sentiment model has 78% accuracy.
Suggest three changes (with tiny code edits) that I could try to improve it.”
Important:
You must still understand any code or text you submit. Do not blindly copy‑paste ChatGPT output into your assignment.
7. Typical assessment tasks (check your case study PDF for details)
Depending on how your instructor uses this repository, you may be asked to:
Describe the business problem and data in your own words
Show basic exploration of hm_sentiment_reviews.csv (e.g. label counts)
Report model performance (accuracy, confusion matrix, key observations)
Compare Python and KNIME implementations
Optionally, reflect on how you used ChatGPT as a learning tool
Write recommendations to H&M’s marketing team based on your findings
Always follow the exact instructions and marking scheme in
Sentiment Analysis_Veliota_Drakopoulou.pdf.
8. License / usage
This repository is intended as a teaching resource for BUS2503 / AI for Business and related courses.
Please credit Dr Veliota Drakopoulou if you reuse or adapt these materials.
Do not add any real personally identifiable information to this repository or derivative datasets.

:contentReference[oaicite:0]{index=0}
::contentReference[oaicite:1]{index=1}

Sources

