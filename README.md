# AutomaticShortAnswerGradingSystem-ASAG
Projected Grading the short answers model using Machine learning models as a classification problem

This project is a classification problem that aims to automatically grade short answer questions. The goal of this project is to develop a machine learning model that can accurately predict the grade of a short answer question given a set of features.

## Dataset
This study makes use of a text dataset gathered from a university. This dataset provides valuable insights into the performance of students in educational institutions, and it can be utilized in developing automated grading systems. The dataset is presented as a collection of Text CSV files. Each CSV file contains details on a particular set of questions, including the students' written responses to those questions and the points assigned to each response. The dataset contains 15 CSV files, with each file consisting of approximately 30 entries. The distribution of data for all the 28 questions are depicted in Fig Below: 

![image](https://user-images.githubusercontent.com/102232692/227260762-295a38f1-a911-4a27-9691-ba8a5b5d8e47.png)

The dataset is labeled with the question as the column header and the answers of the students as the entries in that column. In addition to that, there is another column that consists of the points awarded to each answer. The answers are graded between 0 and 2. Assuming this can be modeled as a classification problem, the grades are normalized to integer before performing the analyzing the dataset. The dataset is highly biased with number of zero grades as 752, one graded as 1152, and two graded as 77. The dataset is not enough for performing the multi classification so, the zero-graded and one-graded dataset is divided into training and testing whereas the two graded dataset is totally used for training the model. We have tried to make the zero and one graded dataset unbiased keeping two graded dataset a side. To make the dataset uniform, the grades are scaled in the range of 0-10. And the distribution of the data is as depicted in Fig. 1. below: 
 
![image](https://user-images.githubusercontent.com/102232692/227260813-0933d12d-a1eb-46a8-a188-4a0ab8cdf276.png)

As depicted in Fig graded dataset is converted into 5 graded dataset after scaling them in the range of 0-10. 


## Machine Learning Model
The proposed approach involves two phases: Pre-processing phase and the classification phase as depicted in Fig. 2. 

 
![image](https://user-images.githubusercontent.com/102232692/227261137-8c21786b-a045-499a-b378-d8392cc45a38.png)

As depicted in the Fig the preprocessing steps include:
 
1.	Grade Scaling: The grades are been multiplied with a scalar to convert and scale all the grades between 0 and 10. There are 5 different classes found in the dataset between 0 to 10 after scaling. 
2.	Removing of Outliers: The Question and answers are of different lengths which effects the uniformity in the dataset and the distribution of lengths are as depicted in Fig
         
![image](https://user-images.githubusercontent.com/102232692/227261267-07500f7f-fcc5-4994-a33f-8a8d18d1e019.png)

The outliers from the dataset are being removed to ensure the uniformity in the dataset. 
3.	Removing Nan’s: Ensures that there is no empty data after removing all the stop words.
4.	Answer Padding: Appended the “null” string to the answers to ensure the same length of the answers. 
5.	Text Sequence Conversion : In this step, the text sequence is converted into numerical data format to make the data ready for the model to take as input. tokenizer is a tool that helps to convert text data into numerical values. It essentially splits the text into individual words or tokens and then assigns a unique numerical value to each of them. The tokenizer can be trained on a corpus of text to learn the vocabulary and assign numerical values to each token.


## Conclusion
This project demonstrates the feasibility of using machine learning to automate the grading of short answer questions. By leveraging the power of classification algorithms and feature engineering, we can develop accurate and efficient grading systems that can save time and resources for educators and educational institutions.
