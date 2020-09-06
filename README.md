# Technical Test for Data Scientist

Thank you for applying for a position with SAP. If you are reading this, it means that you have exhibited a set of desirable qualities during your first-stage interview. We would like to access your technical skills further by working on two simple problems. 

**Confidentiality requirements**: 
- Please do not share the task or data to anyone.
- Please delete the forked repository and your local files after the test.

## Introduction

This technical test is to assess the following:

- **Python profiency**: ability to write good-quaility code.
- **Machine Learning knoweldge**: ability to apply the appropriate feature engineering and modelling algorithms. 
- **Learning aptitude**: ability to learn on the job.

There are 2 parts to the test:

- **Part 1**: data preparation based on requirements.

- **Part 2**: Machine-learning task.

  

## Instructions

1. Fork this repository to your account.
2. Clone from your own repostitory.
3. Add your codes, documentation and/or plot in the jupyter notebooks.
4. Save your notebooks and output files (if any) in `submit/` folder.
5. When you are done, commit and push your code to your repository.
6. Create a Pull Request to this repository.
7. Please make your submission within 1 week from the day you fork this repository.
8. If you need any help, please contact ray.han@sap.com or traci.lim@sap.com.

## Part 1 (data preparation)

Your team is working on a contract related project. Your colleagues want to train text classification models with contract text data, and they need your help to prepare data for the task. This task is about **filtering relevant contracts** and **merging them with labels**. 

- In `data/`, you are given 2 compressed pandas dataframes, `df_cases_200906.gzip` and `df_label_200906.gzip`.

1. `df_cases_200906.gzip`:

  - Each row represents a unique contract.

  - Schema:

     ```
      CaseId          A unique ID given to group of contracts
      FileName        File name of contract
      Language        Language of contract
      StartDate       Start date of contract's creation date
      DocumentType    Type of contract
      IsExecuted      Boolean describing the execution status of contract
      OcrText         OCR result of contract pdf
      QualityScore    A numeric float (0 to 1), to access the quality of text from OCR conversion
      ```

2. `df_label_200906.gzip`

  - Each row represents a unique Case ID.

  - Schema:

     ```
      CaseId     A unique ID given to group of contracts
      label_1    boolean (description of label is not needed for test)
      label_2    boolean (description of label is not needed for test)
      ```

---

#### Requirements

- Main objective is to merge `label_1` and `label_2` into `df_cases_200906.gzip`, so that the team can train text classification models using data from the `OcrText` field.

-  A `CaseId` can contain either one contract, or a group of contracts. Each `CaseId` is given only 1 set of labels. For each `CaseId`, you have to concatentate all `OcrText` fields of all VALID contracts.

- Contracts are consider INVALID if any of the following occurs:

  - `IsExecuted==False`
  - `QualityScore<0.81`

- The final prepared dataset should contain the following columns:

   ```
    CaseId          	A unique ID given to group of contracts
    ValidFileNames  	List of all valid file names
    InvalidFileNames	List of all invalid file
    OcrText         	OCR result of contract pdf
    label_1    				boolean (description of label is not needed for test)
    label_2    				boolean (description of label is not needed for test)
    ```

- Export the final prepared dataset as `submit/df_final.gzip`.

#### Notes

- You are required to code in a Jupyter Notebook, using Python.
- Use the command to read gzip using pandas: `df = pd.read_pickle('df_cases_200906.gzip')`
- Save the following files into the `submit/` folder:
  - One Jupyter notebook, detailing the data preparation code
  - Final prepared dataset, `df_final.gzip` 
- Please make your notebook clean and readable, your code should run top to bottom without any errors. 
- The following will be evaluated:
  - Code correctness
  - Readibility 
  - Runtime 



## Part 2

Your submission in this section is NOT to train the best model. It is to **help us assess your ability to learn and apply NLP modelling techniques.** 

#### Instructions

- Dataset: https://www.kaggle.com/clmentbisaillon/fake-and-real-news-dataset
- Train 3 binary text-classfication models to detect Fake/True news, you are free to use 
  - Any text processing/feature-engineering setup: Bag-of-words, TF-iDF, pretrained, FastText, GloVe, BERT, XLNET, RoBERTa, etc.
  - Any algorithms:  XGBoost, LightGBM, CNN, LSTM, etc.

- Sample your own train and test set, and report test-set's F1 scores and accuracy for each of your models.
- Add a summary section to describe why you chose to train those models, and which is the most preferred.

#### Notes

- You are required to code in a Jupyter Notebook, using Python.
- Example libraries/frameworks you can use: TensorFlow, Keras, Pytorch, Huggingface's transformers, etc.
- Save the following files into the `submit/` folder:
  - One Jupyter notebook, detailing your entire ML pipeline as per instructions.
- Do not submit any locally-saved embedding files.
- Do not attempt to hyper-parameter tune your models.
- Other than the points listed in instructions, there are no strict rules on what to include in your jupyter notebook. You are free to apply data cleaning and exploratory data analysis on top of whatever that is required.
- The following will be evaluated:
  - Code correctness
  - Readibility 
  - Summary

---

Good luck!
