# Fetal-Weight-Prediction-Preterm-Birth-Risk-Calculator-
We analyze pregnancy and birth data with Meir Hospital to improve fetal weight prediction. By finding patterns behind systematic EFW vs. actual weight errors, we reduce them using statistics and ML. The result is a clinician-facing calculator with a corrected estimate plus error direction, probability, and grams.
About # Submissions:
Presentation: A short slide deck that presents the project: the EFW vs. actual birthweight problem, why it matters clinically, key research motivation, competitor overview, main requirements, and a high-level system/architecture view. 

נושא פרויקט גמר (DOCX): The official project topic/overview: goals, why fetal-weight estimation errors matter, what you plan to investigate, and what the final correction calculator should deliver for clinicians. 


סקירת ספרות ומתחרים (DOCX): Literature review + competitive analysis: summarizes key research on systematic EFW errors, factors affecting accuracy, ML directions (including imbalance handling), and compares existing tools/models vs. your proposed solution. 



Final project Requirements (DOCX): Full requirements document: stakeholders, functional requirements (inputs/validation/outputs), non-functional requirements (latency, scalability, metrics), architecture requirements, tech stack, security, deployment, and testing plan. 



Project detailed design (DOCX): Detailed design: algorithm description, candidate models (baseline → ensembles), selection criteria, evaluation methodology, explainability
plan, API endpoints, validation rules, and component/communication design. 


מסמך peer review (DOCX): Peer-review notes you wrote on other teams’ projects: rankings, strengths/weaknesses, and presentation/requirements feedback (not your project spec, but your evaluation of others)

In Articles: 
Article 1: 
The systematic error in the estimation of fetal weight and the underestimation of fetal growth restriction (AJOG, 2017): Explains how systematic ultrasound EFW error can lead to missed fetal growth restriction (FGR), and presents an analytic model (using NICHD fetal growth data) arguing the error should be considered in screening/surveillance decisions.

Article 2: 
Interpretable deep neural networks for early neonatal birth weight prediction using multimodal maternal factors (JBI, 2025): Proposes an interpretable deep-learning approach (TabNet) that predicts birth weight early in pregnancy using maternal factors (including nutrition) and highlights which features drive predictions for clinical decision support. 

Article 3: 
Factors Affecting Clinical over and Underestimation of Fetal Weight—A Retrospective Cohort (J. Clin. Med., 2022): Large retrospective cohort from Meir Medical Center analyzing what increases over/under-estimation (e.g., gestational age, obesity, smoking, oligohydramnios) and the obstetric consequences (e.g., shoulder dystocia, cesarean, inductions). 

Article 4: 
Fetal Weight Estimation via Ultrasound Using Machine Learning (IEEE Access, 2019): ML pipeline to improve ultrasound-based fetal weight estimation, tackling class imbalance (LBW/HBW) using SMOTE + classification and a deep model (DBN) to reduce MAE/MAPE vs traditional formulas, especially at weight extremes. 

Article 5: 
Fetal health risk prediction using ensemble-based machine learning approaches (Knowledge and Information Systems, 2025): Uses cardiotocography (CTG) features to classify fetal health status (normal/suspect/pathological) with tuned ML and ensemble methods (stacking/voting/bagging), emphasizing early detection and decision support. 

Article 6: 
Accuracy in Fetal Weight Estimation by Ultrasound: Hiwale vs Hadlock (JOGI, 2025): Prospective comparison of two ultrasound formulas in a tertiary hospital (Indian population), reporting error patterns and concluding which formula is more accurate in their cohort.


In Model & Data:

Synthetic Pregnancy Dataset (CSV):  
A synthetic dataset containing 15,000 pregnancy and delivery-related records, generated according to the expected clinical parameters of the project. The dataset includes maternal characteristics, obstetric history, ultrasound-related features, delivery information, neonatal outcomes, and estimated fetal weight values.  
This dataset is used for ETL development, data cleaning, validation, exploratory data analysis, distribution analysis, correlation analysis, and initial model testing before receiving the real clinical dataset.

Important note:  
The synthetic dataset is not intended for medical conclusions or clinical decision-making. It is used only for development, testing, and validation of the data pipeline and modeling workflow.

Initial Model:  
An initial machine learning model was added to the repository together with the dataset. The model is used as part of the proof-of-concept stage for fetal weight estimation improvement. Its purpose is to test the full workflow from data preparation to prediction output, and to prepare for future integration with the clinician-facing calculator.

Current Workflow Supported by the Added Data and Model:
1. Batch data extraction from CSV.
2. Data cleaning and validation.
3. Exploratory data analysis (EDA).
4. Detection of missing values, invalid ranges, and logical contradictions.
5. Distribution analysis of numerical, binary, and categorical features.
6. Correlation and association analysis between features.
7. Initial model training/testing.
8. Preparation for future UI integration with FastAPI.

Planned Integration:
The trained model will later be connected to the project UI through the FastAPI backend. Clinicians will enter pregnancy and ultrasound-related parameters into the calculator, and the backend will use the saved model to return an improved fetal weight estimation, including correction direction and expected estimation error.
