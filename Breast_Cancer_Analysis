########## This datset is from Kaggle.com, in regards to Breast Cancer ('Real Breast Cancer Data'). I used MSSQL Server to query questions. #########




SELECT *
FROM BRCA

/* What is the total number of breast cancer cases in this dataset?
*/

SELECT COUNT(*) AS total_cases
FROM BRCA

/* What is the average age of patients with breast cancer? 

-- changing age varchar to int
*/

ALTER TABLE BRCA
ALTER COLUMN Age int


SELECT AVG(Age) AS avg_age 
FROM BRCA

/* Which gender has the most cases of breast cancer?
*/

SELECT Gender, COUNT(*) AS cases
FROM BRCA
GROUP By Gender

/* what is the distrubution status of patients in this dataset?
*/

SELECT patient_status, COUNT(*) 
FROM BRCA 
GROUP BY patient_status;

/* What is the most common stage of breast cancer in this dataset?
*/

SELECT Tumor_Stage, COUNT(*) AS cases 
FROM BRCA 
GROUP BY Tumor_Stage
ORDER BY cases DESC 

/* How many patients in this datset have ductal carcinoma histology?
*/

SELECT COUNT(*) 
FROM BRCA
WHERE Histology = 'Infiltrating Ductal Carcinoma'

/* What percentage of patients underwent lumpectomy surgery?
*/

SELECT (COUNT(*) * 100 / (SELECT COUNT(*) FROM BRCA)) AS percentage 
FROM BRCA 
WHERE Surgery_type = 'lumpectomy'


/* What is the most common histoloy type in this dataset for patients over the age of 50?
*/

SELECT Histology, COUNT(*) 
FROM BRCA 
WHERE age > 50 
GROUP BY Histology 
ORDER BY COUNT(*) DESC


/* How many patients in the dataset underwent any type of mastectomy surgery and are no longer alive?
*/

SELECT COUNT(*) 
FROM BRCA 
WHERE surgery_type LIKE '%mastectomy' AND patient_status = 'dead';

/* What is the average age of patients who underwent mastectomy surgery?
*/

SELECT AVG(age) 
FROM BRCA WHERE surgery_type LIKE '%mastectomy'



/* What is the percentage of patients in the dataset who underwent surgery and are still alive?
*/

SELECT (COUNT(*) * 100 / (SELECT COUNT(*) FROM BRCA WHERE surgery_type IS NOT NULL)) AS percentage 
FROM BRCA 
WHERE surgery_type IS NOT NULL AND patient_status = 'alive';

