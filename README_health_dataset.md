# Messy Synthetic Health Records Dataset

## Purpose
A deliberately messy, entirely synthetic dataset for practicing data cleaning, exploratory data analysis, feature engineering, and later machine-learning experiments.

**Important:** These are fictional records generated for practice. They are not real patient data and must not be used for clinical decisions.

## Files
- `messy_synthetic_health_records.csv` — easiest for Python/pandas workflows.
- `messy_synthetic_health_records.xlsx` — Excel version with filters and frozen header row.

## Size
Approximately 2,500 base records, plus duplicate rows added intentionally.

## Columns
- `patient_id`: synthetic patient identifier; some IDs have inconsistent formatting or collisions.
- `full_name`: fictional name.
- `age_years`: age in years; contains missing values, strings, and invalid values.
- `sex`: sex/gender field with inconsistent spelling/capitalization/abbreviations.
- `district`: district; inconsistent casing and variants.
- `facility`: health facility name.
- `visit_date`: visit date with multiple formats and missing values.
- `visit_type`: Outpatient, Inpatient, Emergency, Follow-up.
- `height_cm`, `weight_kg`: measurements; some values are text or use comma decimals.
- `bmi`: BMI values, including some suspicious values; can be checked against height and weight.
- `systolic_bp_mmHg`, `diastolic_bp_mmHg`: blood pressure; some missing/text/impossible values.
- `heart_rate_bpm`: heart rate in beats/minute.
- `temperature_c`: body temperature in Celsius; may include unit suffixes.
- `spo2_percent`: oxygen saturation percentage; may include `%` strings.
- `glucose_mmol_L`: glucose measurement in mmol/L.
- `smoking_status`: Never, Former, Current, Unknown, with inconsistent labels.
- `alcohol_use`: alcohol-use category with inconsistent labels.
- `chronic_condition`: None, Hypertension, Diabetes, Asthma, HIV, Multiple; some variants.
- `medication_count`: number of medications; contains occasional invalid values.
- `length_of_stay_days`: hospital stay length; zero often means outpatient/no stay, but inspect carefully.
- `readmitted_30d`: intended target label (0/1) for a future readmission prediction exercise; some labels are missing.
- `data_source`: source system/form label.

## Deliberate data-quality problems
- Missing values across numeric and categorical columns.
- Mixed data types (numbers stored as strings).
- Inconsistent categories, capitalization, abbreviations, and whitespace.
- Multiple date formats.
- Decimal commas and unit suffixes.
- Impossible or suspicious values (e.g., negative ages, extreme vital signs).
- Exact duplicate rows and near-duplicate records.
- Inconsistent patient ID formats and a few ID collisions.
- BMI values that may not match height/weight.
- A few missing or malformed target labels.

## Suggested project path
1. Profile the raw data: shape, dtypes, missingness, duplicates, unique values.
2. Standardize column names and categorical labels.
3. Normalize patient IDs, then investigate ID collisions before deleting anything.
4. Parse dates explicitly and check impossible/future dates.
5. Convert numeric fields carefully (decimal commas, unit suffixes, invalid tokens).
6. Validate ranges and cross-column logic (BMI vs height/weight; systolic vs diastolic BP; length of stay vs visit type).
7. Decide how to handle missingness and duplicate/near-duplicate records; document each decision.
8. Produce a cleaned dataset plus a cleaning log.
9. Do EDA and create a reproducible pipeline.
10. Later, model `readmitted_30d` as a binary target. This is a teaching exercise only: the target is randomly assigned in this synthetic dataset and is **not clinically meaningful**, so predictive performance is not evidence of real-world usefulness. For a more realistic ML project, regenerate the target from a transparent simulated risk mechanism, or use an appropriately licensed, de-identified public dataset.

## Ethics and limitations
All names and measurements are fictional. This dataset is for education, not diagnosis, treatment, or real-world healthcare deployment.
