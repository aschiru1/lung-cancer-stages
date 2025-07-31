## Patient Risk Evaluation Database System


This project is a **Database Management System (DBMS)** prototype developed using **MySQL and Python** to manage and analyze patient medical data for risk evaluation. It involves creating and manipulating a relational database with tables for patients, medical history, lifestyle risk factors, and diagnoses.

### Project Overview

The goal of this project is to simulate a backend system for managing patient risk profiles based on various medical and lifestyle parameters. The database schema captures multiple dimensions of a patient's health and uses structured data input to help healthcare providers make informed decisions.

---

###Database Schema

The following tables were created:

- **Patients**
  - `patient_id` (Primary Key)
  - `age`
  - `gender`

- **MedicalHistory**
  - `history_id` (Primary Key)
  - `patient_id` (Foreign Key)
  - `chronic_lung_disease` (Scale: 1-7)
  - `frequent_cold` (Scale: 1-7)
  - `dry_cough` (Scale: 1-7)
  - `snoring` (Scale: 1-7)

- **Diagnosis**
  - `diagnosis_id` (Primary Key)
  - `patient_id` (Foreign Key)
  - `risk_level` (ENUM: 'Low', 'Medium', 'High')

- **Lifestyle_Risks**
  - `risk_id` (Primary Key)
  - `diagnosis_id` (Foreign Key)
  - `patient_id` (Foreign Key)
  - `air_pollution` (Scale: 1-7)
  - `alcohol_use`, `dust_allergy`, `occupational_hazards`, `genetic_risk`, `chronic_lung_disease`, `balanced_diet`, `obesity`, `smoking`, `passive_smoking`, `chest_pain`, `coughing_of_blood`, `fatigue`, `weight_loss`, `shortness_of_breath`, `wheezing`, `swallowing_difficulty`, `clubbing_of_finger_nails`, `frequent_cold`, `dry_cough`, `snoring`

---

### Technologies Used

- **Python 3.x**
- **MySQL**
- **mysql-connector-python** package for connecting to the database

---

### How to Run

1. Install MySQL and create a user/database.
2. Install required package:
   ```bash
   pip install mysql-connector-python
   ```
3. Update the credentials in the notebook:
   ```python
   host="127.0.0.1",
   user="your_username",
   password="your_password",
   database="your_db"
   ```
4. Run the notebook cells to:
   - Connect to the database
   - Create tables
   - Insert and query data

---

### Features

- Modular schema design
- Input validation via SQL constraints (e.g., TINYINT range checks)
- Foreign key constraints to ensure data integrity

---

### Future Work

- Automate data input with a web or GU
- Connect to real-world EHR datasets (while preserving privacy)
- Deploy using cloud-hosted MySQL and JupyterHub

---
