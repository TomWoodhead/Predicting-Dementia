<img src="https://noodle.digitalfutures.com/studentuploads/Screenshot_2025-05-20_at_10.14.26.PNG" alt="Screenshot" width="100%" style="display: block; margin-left: auto; margin-right:auto;">

# Predicting Demntia - A Random Forest Approach 🧠  

## 1 - Objective 📌  

Dementia is a broad term for an illness that causes a loss in cognitive function. The [NHS](https://www.nhs.uk/conditions/dementia/about-dementia/what-is-dementia/#:~:text=How%20common%20is%20dementia,have%20dementia%20in%20the%20UK.) estimates that in the UK, there are 994,000 people with dementia, and worryingly, a third of these are undiagnosed. There is no single test for dementia. Instead, medical professionals diagnose the condition based on a combination of examinations, clinical tests, and behavioural characteristics.  

In 2022, my wonderful mum passed away after a battle with Lewy Body Dementia. Early on, I recall her completing a cognitive test that I now know to be the Mini Mental State Exam (MMSE). This test is comprised of 30 questions, and a score of below 25 indicates dementia. My mum passed this test, but unfortunately for me and everybody whose life that she lit up, she was a false negative. 

<p align="center">
  <img src="https://noodle.digitalfutures.com/studentuploads/Screenshot_2025-05-14_at_13.31.57.png" alt="Screenshot" width="40%">
</p>


Nearing the end of my training as a Data Analyst at Digital Futures, I have the opportunity to explore a topic of my choosing. In memory of my mum, I have decided to apply the skills I have gained in machine learning to develop a predictive model for dementia. I hope to learn more about her set of circumstances and in particular, investigate my doubts about the effectiveness of the MMSE. More generally, I aspire to provide insight into how we might improve dementia diagnosis in the future. 

---  

## 2 - The Data 📊  


The dataset, available [here](https://www.kaggle.com/code/ruslankl/dementia-prediction-w-tree-based-models), is taken from the [Open Access Series of Imaging (OASIS)](https://sites.wustl.edu/oasisbrains/), a project by the Washington University School of Medicine which makes neuroimaging data freely available to the scientific community. The aim is to 'facilitate future discoveries' in clinical neuroscience. The data includes 373 records of dementia assessments with brain measurements, demographic information and results from the MMSE, the cognitive assessment on which my mum was erroneously classified as a negative.   

**Acknowledgment:** "Data were provided [in part] by OASIS,
OASIS-1: Cross-Sectional: Principal Investigators: D. Marcus, R, Buckner, J, Csernansky J. Morris; P50 AG05681, P01 AG03991, P01 AG026276, R01 AG021910, P20 MH071616, U24 RR021382."  

---  

## 3 - The Approach 🔍  


After feature engineering, selection and train-test splitting, an initial Random Forest model is estimated and fine-tuned to provide a benchmark model against which adaptations are assessed. I then explore how some individuals, like my mum, may be predisposed to performing well on the MMSE and as a result, emerge as false negatives. I execute this exploration by discounting MMSE scores by Years of Education. Finally, I explore how measures of brain volume can be adapted to improve results. Brain atrophy, the shrinking of the brain, is a feature of dementia, but also occurs naturally with age. I propose a method of isolating dementia induced atrophic effects from the effects of aging in general and include this measure in my estimation.   

---  

## 4 - Results ✅  


From the benchmark model to the final model, the MMSE is consistently the most important feature in terms of reducing the class impurity. However, upon analysis of the false negatives, I notice that they all have the same thing in common; they all have above average MMSE scores. This theme of high MMSE scores and false negatives precisely reflects the situation of my mum. However, by discounting the MMSE scores by years of education, recall is improved. This suggests that some individuals are predisposed to performing well on the MMSE despite cognitive decline, and in affect, their dementia can be masked. This finding is significant for 2 reasons. First, more people can get the diagnoses that they need if we consider factors that reflect general cognitive ability; that is cognitive ability in the absence of dementia. Second, as years of education is only a weak proxy for general cognitive ability, more effective discounting measures can be developed. 

Furthermore, I find that instead of using brain volume as a feature, using a measure which isolates dementia induced atrophic effects from those that occur through aging can improve the models recall. 


