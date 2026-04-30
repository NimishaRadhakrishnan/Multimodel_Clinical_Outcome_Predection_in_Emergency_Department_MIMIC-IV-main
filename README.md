# Multimodal_Clinical_Outcome_Prediction_in-_Emergency_Department_MIMIC-IV
Multimodal Clinical Monitoring in the Emergency Department (MC-MED) Dataset
The Multimodal Clinical Monitoring in the Emergency Department (MC-MED) dataset is a large-scale, de-identified clinical dataset designed to support advanced research in emergency medicine, clinical decision support systems, and multimodal machine learning. The dataset integrates structured electronic health record (EHR) data with high-resolution physiological monitoring signals, enabling comprehensive analysis of patient trajectories during emergency department (ED) visits.
Dataset Overview
MC-MED captures complete emergency department encounters at the visit level. Each visit is identified by a unique Clinical Serial Number (CSN), with patients identified by a Medical Record Number (MRN). All patient identifiers have been removed to ensure privacy and compliance with ethical research standards.
Core Data Files
1. visits.csv
This file provides high-level information for each ED visit. It includes patient demographics, arrival characteristics, clinical timestamps, and visit outcomes.

Key variables include:
- Patient age and sex
- Race and ethnicity
- Means of arrival (e.g., EMS, self)
- Chief complaint
- Triage vital signs and acuity
- Emergency department disposition (e.g., discharge, admission, ICU)
- Length of stay metrics and event timestamps
2. pmh.csv (Past Medical History)
This file contains patients’ historical medical conditions recorded prior to the ED visit. Diagnoses are encoded using ICD-9 and ICD-10 codes and mapped to Clinical Classifications Software (CCS) categories.

Key variables include:
- Diagnosis code type (ICD-9 or ICD-10)
- Diagnosis code
- Diagnosis description
- CCS category and description
3. meds.csv (Home Medications)
This file lists patients’ home medications prior to or during the ED encounter. It captures medication names, generic names, drug classes, and medication timing information.

Key variables include:
- Medication identifiers and names
- Drug class and subclass
- Medication start and end dates
- Active medication indicators
4. orders.csv
This file records all orders placed during the ED visit, including laboratory tests, imaging studies, and therapeutic interventions.

Key variables include:
- Order type (lab, imaging, medication, procedure)
- Procedure or test name
- Order timestamps
- Result and administration times
5. labs.csv
This file provides laboratory test results associated with ED visits. It includes individual lab components, measured values, abnormality flags, and reference ranges.

Key variables include:
- Lab test and component names
- Numeric and categorical result values
- Abnormal flags
- Normal reference ranges
6. rads.csv (Radiology)
This file contains radiology study information and summarized imaging impressions produced during the ED visit.

Key variables include:
- Imaging study name
- Study order and result timestamps
- Free-text radiology impression summaries
7. numerics.csv
This file provides minute-level numeric physiological measurements recorded during the ED stay. It represents continuous clinical monitoring data.

Measured variables include:
- Heart rate (HR)
- Respiratory rate (RR)
- Oxygen saturation (SpO2)
- Blood pressure (SBP, DBP, MAP)
- Temperature
- Perfusion index
- Pain score
- Oxygen flow rate (LPM_O2)
- Heart rate variability metrics (1min_HRV, 5min_HRV)
8. waveform_summary.csv
This file summarizes the availability of continuous physiological waveforms for each visit. While raw waveforms may be stored separately, this file indicates their presence and duration.

Waveform types include:
- Electrocardiogram (ECG)
- Photoplethysmography (Pleth)
- Respiratory waveforms

Key summary variables include total waveform duration and number of available segments.
Training, Validation, and Test Splits
The MC-MED dataset provides predefined data splits to support reproducible machine learning research. Two split strategies are included:
1. Random Patient-Level Split
In the random split, patient visits are divided into training (80%), validation (10%), and test (10%) sets. All visits associated with the same patient (MRN) are restricted to a single split to prevent data leakage.

Files:
- split_random_train.csv
- split_random_val.csv
- split_random_test.csv
2. Chronological Split
The chronological split simulates real-world deployment scenarios. All visits in the validation set occur after the training set, and all test visits occur after the validation set. Patients are again restricted to a single split.

Due to these constraints, the final split proportions are approximately 78% training, 11% validation, and 11% test.

Files:
- split_chrono_train.csv
- split_chrono_val.csv
- split_chrono_test.csv
Intended Use Cases
MC-MED is suitable for a wide range of research applications, including:
- Multimodal outcome prediction in emergency medicine
- Early risk stratification and triage support
- Temporal modeling of patient deterioration
- Integration of structured EHR data with physiological signals
- Evaluation of machine learning models under realistic chronological validation
  
 
Citations and References
Dataset and Publication
Kansal, A., Chen, E., Jin, B. T., Rajpurkar, P., & Kim, D. (2025). MC-MED, multimodal clinical monitoring in the emergency department. Scientific Data, 12, 1094. https://doi.org/10.1038/s41597-025-05419-5

Kansal, A., Chen, E., Jin, T., Rajpurkar, P., & Kim, D. (2025). Multimodal Clinical Monitoring in the Emergency Department (MC-MED) (version 1.0.1). PhysioNet. RRID:SCR_007345. https://doi.org/10.13026/wvyw-g663

GitHub Repository
Kansal, A., Chen, E., Jin, T., Rajpurkar, P., & Kim, D. (2025). MC-MED: Multimodal Clinical Monitoring in the Emergency Department (Version 1.0.1) [Computer software]. GitHub. https://github.com/physionet/mc-med

PhysioNet Reference
Goldberger, A. L., Amaral, L. A. N., Glass, L., Hausdorff, J. M., Ivanov, P. C., Mark, R. G., Mietus, J. E., Moody, G. B., Peng, C. K., & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation, 101(23), e215–e220. RRID:SCR_007345.
