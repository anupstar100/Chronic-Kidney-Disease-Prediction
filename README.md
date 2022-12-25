# Chronic-Kidney-Disease-Prediction
## Abstract:
Chronic kidney disease (CKD) is a condition characterized by progressive loss of kidney function over time. It describes a clinical entity that causes kidney damage and affects the general health of the human body. Improper diagnosis and treatment of the disease can eventually lead to endstage renal disease and ultimately lead to the patient’s death. Machine Learning (ML) techniques have acquired an important role in disease prediction and are a useful tool in the field of medical science. In the present research work, we aim to build efficient tools for predicting CKD occurrence, following an approach which exploits ML techniques. More specifically, first, we apply class balancing in order to tackle the non-uniform distribution of the instances in the two classes, then features ranking and analysis are performed, and finally, several ML models are trained and evaluated based on various performance metrics.
## Introduction
The human body has two kidneys located at the back of the peritoneal cavity, which are vital organs necessary for its proper functioning. The main function of the kidneys is to regulate the balance of salt, water and other ions and trace elements in the human body, such as calcium, phosphorus, magnesium, potassium, chlorine and acids. At the same time, the kidneys secrete hormones such as erythropoietin, vitamin D and renin. More specifically, erythropoietin stimulates the production and maturation of red blood cells in the bone marrow, while vitamin D regulates calcium and phosphorus in the body, bone structure and many other actions. The kidneys are also the site of the action of hormones that are responsible for regulating blood pressure, fluid balance or bone metabolism and vascular calcifications. Finally, the kidneys eliminate all the useless products of metabolism, as well as drugs and other toxins that enter the body. Diabetes and high blood pressure are the two main causes of chronic kidney disease. Diabetes is characterized by high blood sugar levels, causing damage to the kidneys and
heart, blood vessels and eyes. Moreover, poor control of high blood pressure can be a major
cause of heart attack, stroke and chronic kidney disease. Other conditions that affect the
kidneys are glomerulonephritis, hereditary diseases, dysplasia, kidney stones, tumours,
recurrent urinary tract infections, metabolic diseases, obesity and age [2,3].
CKD is a silent disease, as most sufferers have no symptoms until kidney function
drops to 15–20% of normal [4]. The main symptoms in the advanced stage of CKD are the
feeling of fatigue and lack of energy, concentration problems, decreased appetite, sleep
problems, muscle cramps at night, swelling in the legs and ankles, swelling around the
eyes, dry skin with intense itching and frequent urination, especially at night [5].
The most important and effective parameter for the evaluation of renal function is
the glomerular filtration rate (GFR), which practically evaluates the ability of the kidney
Big Data Cogn. Comput. 2022, 6, 98. https://doi.org/10.3390/bdcc6030098 https://www.mdpi.com/journal/bdccBig Data Cogn. Comput. 2022, 6, 98 2 of 15
to filter blood. The glomerular filtration rate is the best measure of renal function and is
usually assessed (eGFR) by the results of a creatinine blood test. The eGFR value refers to
milliliters per minute per 1.73 m2 (mL/min/1.73 m2). Renal function can be classified into
5 stages according to eGFR, as shown in Table 1 [6].
