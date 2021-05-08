# sepsis_detection
Early Detection of Sepsis using Machine Learning


Electronic Health Records (EHR) gives a lot of information regarding a patient's progress in health, who is admitted in an Intensive Care Unit. Sepsis is a critical condition suffered by a patient whom, if not treated in a timely manner can cause severe effects. Machine Learning algorithms have the ability to utilize Electronic Health Records to help doctor to detect the onset of sepsis. In this work we present Random Forest based ensemble machine learning technique to work on patient’s
data, also called vital sign inputs, from Intensive Care Unit. The proposed technique performs well on data which contain a major chunk as missing values due to the sparsity of measurement taken in an Intensive Care Unit. We used a combined classifier and early predictor approach to accomplish the task. The classifier do the job of classification when early prediction is not possible due to lack of data. While early predictor predicts the onset of sepsis based on the patient’s information it received from previous recordings of vital sign inputs. A utility metric score or confusion matrix is used to evaluate the early prediction. The utility function rewards early predictions and penalizes late predictions as well as false alarms. We were able to achieve a good performance based on the so called utility metric.
About Sepsis:
Sepsis is a life-threatening medical emergency. It is sometimes called as Septicemia.
There are 3 stages of Sepsis
1. Sepsis
2. Severe Sepsis
3. Septic shock
Traditional Diagnosis:
Diagnosis of sepsis involves blood tests, Other laboratory tests, various Imaging Techniques etc. But these traditional processes are time consuming and in some cases doctors to find it difficult to finalize the results.
SOFA score:
A kind of scoring methods were introduced for quantifying the organ dysfunction named Sequential Organ Failure Assessment (SOFA) scores. The SOFA score is based on six different scores (window size, w=6) which includes respiratory, cardiovascular, hepatic, coagulation, renal, & neurological systems. Higher the SOFA score leads to increased mortality rate for the patient. A SOFA score greater than or equal to 2 reflects a case of sepsis for the general hospital population suspected with sepsis symptoms. The quick SOFA score assists healthcare providers in estimating the risk of morbidity and mortality due to sepsis. Although another metric q-SOFA (quick SOFA) is introduced to identify sepsis with high sensitivity it never replaced the SOFA score.
Why Vital Signs?
Many worked in the area of early detection of sepsis to accurately predict the onset of sepsis from the vital sign inputs taken from patient from the time of
admission. Studies conducted on electronic health records using machine learning algorithms to accurately predict the onset of sepsis shows that early detection of sepsis is possible using vital sign inputs and demographic data of the patient.
Datasets Used:
List of features or attributes available in dataset are listed below:
Vital Signs
 Heart rate
 Oxygen Saturation
 Temperature
 Systolic BP, Diastolic BP
 Mean arterial pressure
 Respiration rate
 End tidal CO2
Laboratory values
 Blood pH, Bicarbonate level
 PaCO2 Partial pressure of carbon dioxide from arterial blood
 SaO2 Oxygen saturation from arterial blood
 Calcium, Chloride, Creatinine, Bilirubin
 Glucose , Lactic acid
 Magnesium, Phosphate, Potassium
 Troponin I, Hemoglobin
 WBC Leukocyte count
 Fibrinogen Platelets
 Blood urea nitrogen
Demographic values
Apart from vital signs and laboratory values the dataset also give demographic values such as age, gender, Hospital admission time and ICU length of stay. Since the measurements are done on a need to basis most of the values of the vitals and others were filled with NA’s. We used mean values from across the dataset to fill the NA’s since their presence can improve the efficiency of the predictions.
Method Used:
The method we develop uses a two classifier based approach in which one classifier serves to do the job of classification when the number of recording of the admitted patient is less than a window size (w). The other classifier is invoked when the w-th measurement is done for the patient in ICU. This classifier, so called predictor does the job of early prediction from the given window size, w.
We are going to use machine learning ensemble technique random forest for conducting our studies. A window size, (w=6) is used for early prediction of sepsis. Initially we use classification if the window size is less than six, if the results are showing onset of sepsis we use zero filling to create a window of data and verify the same using early predictor. If we have enough data we can do early prediction.
