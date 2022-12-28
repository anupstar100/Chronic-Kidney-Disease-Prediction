# Chronic-Kidney-Disease-Prediction
## Abstract:
Chronic kidney disease (CKD) is a condition characterized by progressive loss of kidney function over time. It describes a clinical entity that causes kidney damage and affects the general health of the human body. Improper diagnosis and treatment of the disease can eventually lead to endstage renal disease and ultimately lead to the patient’s death. Machine Learning (ML) techniques have acquired an important role in disease prediction and are a useful tool in the field of medical science. In the present research work, we aim to build efficient tools for predicting CKD occurrence, following an approach which exploits ML techniques. More specifically, first, we apply class balancing in order to tackle the non-uniform distribution of the instances in the two classes, then features ranking and analysis are performed, and finally, several ML models are trained and evaluated based on various performance metrics.

## Introduction
The human body has two kidneys located at the back of the peritoneal cavity, which are vital organs necessary for its proper functioning. The main function of the kidneys is to regulate the balance of salt, water and other ions and trace elements in the human body, such as calcium, phosphorus, magnesium, potassium, chlorine and acids. At the same time, the kidneys secrete hormones such as erythropoietin, vitamin D and renin. More specifically, erythropoietin stimulates the production and maturation of red blood cells in the bone marrow, while vitamin D regulates calcium and phosphorus in the body, bone structure and many other actions. The kidneys are also the site of the action of hormones that are responsible for regulating blood pressure, fluid balance or bone metabolism and vascular calcifications. Finally, the kidneys eliminate all the useless products of metabolism, as well as drugs and other toxins that enter the body.

Diabetes and high blood pressure are the two main causes of chronic kidney disease. Diabetes is characterized by high blood sugar levels, causing damage to the kidneys and heart, blood vessels and eyes. Moreover, poor control of high blood pressure can be a major cause of heart attack, stroke and chronic kidney disease. Other conditions that affect the kidneys are glomerulonephritis, hereditary diseases, dysplasia, kidney stones, tumours, recurrent urinary tract infections, metabolic diseases, obesity and age.

CKD is a silent disease, as most sufferers have no symptoms until kidney function drops to 15–20% of normal. The main symptoms in the advanced stage of CKD are the feeling of fatigue and lack of energy, concentration problems, decreased appetite, sleep problems, muscle cramps at night, swelling in the legs and ankles, swelling around the eyes, dry skin with intense itching and frequent urination, especially at night.

The most important and effective parameter for the evaluation of renal function is the glomerular filtration rate (GFR), which practically evaluates the ability of the kidney to filter blood. The glomerular filtration rate is the best measure of renal function and is usually assessed (eGFR) by the results of a creatinine blood test. The eGFR value refers to milliliters per minute per 1.73 m2 (mL/min/1.73 m2). Renal function can be classified into 5 stages according to eGFR, as shown in Table 1.
![image](https://user-images.githubusercontent.com/98649231/209456474-afbe7fd6-96b4-47ad-aa7d-3707fbb007fb.png)

Early diagnosis and treatment of CKD is a serious challenge for the medical community. The treating physician (nephrologist) is called on the one hand to slow down the progression of the disease to more advanced stages, and if possible, to suspend it, and on the other hand, to treat the above-mentioned systemic manifestations.

The advances in sensor networks, communication technologies, data science and statistical processing have rendered ML techniques as important tools in various health-oriented applications, such as in the early diagnosis of several chronic conditions, the Internet of Things (IoT)-based pervasive (assisted) living environments (smart homes) for elderly fall detection, etc. Concerning the diseases, some characteristic ones are the following: Diabetes, Hypertension, Cholesterol, COVID-19, Chronic Obstructive Pulmonary Disease (COPD), Stroke, Cardiovascular Diseases (CVDs), Acute Liver Failure (ALF), Acute Lymphoblastic Leukemia, Sleep Disorders, Hepatitis, Cancer, Metabolic Syndrome, etc.

In the current research work, a Machine Learning-based approach will be presented for CKD disease. The main contributions of the adopted methodology are the following:
* A data preprocessing step that exploits the Synthetic Minority Oversampling Technique (SMOTE), which is essential to ensure that the dataset instances are distributed in a balanced way and, thus, designs effective classification models to predict the risk for CKD occurrence.
* A features analysis, which includes three specific sub-steps: (i) numerical attributes statistical description, (ii) order of importance measurement by employing three different methods, and (iii) capturing nominal features frequency of occurrence in tabular form.
* A comparative evaluation of various models’ performance is presented considering the most common metrics, such as Precision, Recall, F-Measure, Accuracy and AUC.
* A performance evaluation is demonstrated, where all models demonstrated exceptionally high outcomes, with Rotation Forest achieving the highest results in all metrics, thus constituting the main suggestion of this analysis.

## Dataset Description
  1. age --> Age (numerical) in years
  2. bp --> Blood Pressure (numerical) in mm/Hg
  3. sg --> Specific Gravity (nominal) - [1.005, 1.010, 1.015, 1.020, 1.025]
  4. al --> Albumin (nominal) - [0, 1, 2, 3, 4, 5]
  5. su --> Sugar (nominal) - [0, 1, 2, 3, 4, 5]
  6. rbc --> Red Blood Cells - [normal, abnormal]
  7. pc --> Pus Cell (nominal) - [normal, abnormal]
  8. pcc --> Pus Cell Clumps (nominal) - [present, notpresent]
  9. ba --> Bacteria (nominal) - [present, notpresent]
  10. bgr --> Blood Glucose Normal (numerical) in mgs/dl
  11. bu --> Blood Urea (numerical) in mgs/dl
  12. sc --> Serum Creatinin (numerical) in mgs/dl
  13. sod --> Sodium (numerical) in mEq/L
  14. pot --> Potassium (numerical) in mEq/L
  15. hemo --> Hemoglobin (numerical) in gms
  16. pcv --> Packed Cell Volume (numerical)
  17. wc --> White Blood Cell Count (numerical) in cells/cumm
  18. rc --> Red Blood Cell Count (numerical) in millions/cmm
  19. htn --> Hypertension (nominal) - [yes, no]
  20. dm --> Diabetes Mellitus (nominal) - [yes, no]
  21. cad --> Coronary Artery Disease (nominal) - [yes, no]
  22. appet --> Appetite (nominal) - [good, poor]
  23. pe --> Pedal Edema (nominal) - [yes, no]
  24. ane --> Anemia (nominal) - [yes, no]
  25. class --> Class (nominal) - [ckd, notckd]

* There are 400 rows and 26 columns.
* There are 12 numerical columns and rest are (14) categorical columns.

## Data Cleaning
1. First I dropped the `id` column.
2. Changed the column name to make it understandable.
![image](https://user-images.githubusercontent.com/98649231/209496218-04c30eb9-bc08-4a6c-b25c-4d2e831ca821.png)
3. Changed the data type of `specific_gravity`, `albumin`, `sugar` to 'object'.
4. Changed the data type of `packed_cell_volume`, `white_blood_cell_count`, `red_blood_cell_count` to numeric.
5. Checked the unique values of the categorical columns.
    * There were some incorrect values like '\tno', '\tyes', ' yes', '\tno', 'ckd\t', 'notckd'.
    * So I corrected them.
6. Mapped the target column `class` --> {'ckd' : 0, 'notckd' : 1}
    * 0 --> chronic kidney, 1 -- > not a chronic kidney

