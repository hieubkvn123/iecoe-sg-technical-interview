# Technical Test for Data Scientist Intern

Thank you for applying for a position with SAP. If you are reading this, it means that you have exhibited a set of desirable qualities during your first-stage interview. We would like to access your technical skills further. 

**Confidentiality requirements**: 
- Please do not share the task or data to anyone.
- Please delete the forked repository and your local files after the test. However, you are free to keep your code if you want. 

## Introduction

This technical test is to assess the following:

- **Python profiency**: ability to write good-quaility code.
- **Machine Learning knoweldge**: ability to apply the appropriate feature engineering and modelling algorithms. 
- **Learning aptitude**: ability to learn on the job.  

## Instructions

1. Fork this repository to your account.
2. Clone from your own repostitory.
3. Add your codes, documentation and/or plot in the jupyter notebooks.
4. Save your notebooks and output files (if any) in `submit/` folder.
5. When you are done, commit and push your code to your repository.
6. Create a Pull Request to this repository.
7. Please make your submission within 1 week from the day you receive this test.
8. If you are not sure of any of the intructions, please exercise your own judgement and proceed accordingly.
9. For non-test related queries, please contact traci.lim@sap.com, xi.isaac.chan@sap.com or ray.han@sap.com.



## Coding Test Brief

Your submission in this section is NOT to train the best model. It is to **help us assess your ability to learn and apply NLP modelling techniques.** 

#### Instructions

- Dataset: https://www.kaggle.com/clmentbisaillon/fake-and-real-news-dataset
- Train 3 binary text-classfication models to detect Fake/True news, you are free to use 
  - Any text processing/feature-engineering setup: Bag-of-words, TF-iDF, pretrained embeddings, FastText, GloVe, BERT, XLNET, RoBERTa, etc.
  - Any algorithms:  XGBoost, LightGBM, CNN, LSTM, etc.

- Sample your own train and test set, and report test-set's F1 scores and accuracy for each of your models.
- Add a summary section to describe why you chose to train those models, and which is the most preferred.

#### Notes

- You are required to code in a Jupyter Notebook, using Python.
- Example libraries/frameworks you can use: Sklearn, TensorFlow, Keras, Pytorch, Huggingface's transformers, etc.
- Feel free to take blocks of your code from existing public kaggle kernels or external tutorials online. Add a comment to indicate the source of your code if you do so.
- Save the following files into the `submit/` folder:
  - One Jupyter notebook, detailing your entire ML pipeline as per instructions.
- Do not submit any locally-saved embedding files.
- Do not attempt to hyper-parameter tune your models.
- If you lack CPU or GPU resources, feel free to use Google Colab, or re-sample your dataset to be smaller. 
- Other than the points listed in instructions, there are no strict rules on what to include in your jupyter notebook. You are free to apply data cleaning and exploratory data analysis on top of whatever that is required.
- The following will be evaluated:
  - Code correctness
  - Readibility 
  - Summary

---

Good luck!
