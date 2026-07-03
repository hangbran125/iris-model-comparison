# Iris Model Comparison — Decision Tree vs. Random Forest vs. Logistic Regression

A compact, heavily-commented notebook that trains three classic classifiers on the
Iris dataset, compares their accuracy, and reads *past* accuracy into per-class
precision/recall and confusion matrices — the evaluation habits that carry straight
into security ML (where a missed attack costs far more than a false alarm).

---

## What it does

1. Loads Iris (150 samples, 4 features, 3 balanced classes) from scikit-learn.
2. Splits 80/20 with a fixed `random_state` so the split is reproducible.
3. Trains **Decision Tree**, **Random Forest**, and **Logistic Regression**, and
   prints each model's accuracy.
4. Prints a **classification report** and **confusion matrix** per model to see how
   each does on every individual class.

## Result

With an 80/20 split all three models perform well. Widening the test split to 40%
(less training data) separates them — **Logistic Regression held up best**, a
concrete demonstration of how model ranking depends on how much data you train on,
not just the algorithm.

## Run it yourself

```bash
pip install -r requirements.txt
jupyter notebook iris.ipynb
```

## Skills demonstrated

scikit-learn · train/test methodology and reproducibility (`random_state`) · model
comparison · evaluation beyond accuracy (precision, recall, F1, confusion matrix) ·
reasoning about the train/test trade-off.

## Why Iris, for a security portfolio

Iris is the "hello world" of classification — deliberately simple so the focus stays
on *method*: comparing models fairly and evaluating them the way you'd have to when
the positive class is "attack" and a false negative is the expensive mistake.

---

<sub>Week 1 of a structured AI-security learning program (ML foundations → LLM
security → red teaming). Part of a portfolio documenting that progression.</sub>
