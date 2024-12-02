# The-Drug-Decision-Matrix

The newly uploaded dataset contains information about 200 individuals, likely from a study involving drug prescriptions. It has 6 columns, each representing a characteristic or classification relevant to the analysis
Age:

Integer values representing the age of the individuals.
Sex:

Categorical values representing the gender of the individuals (F for Female, M for Male).
BP (Blood Pressure):

Categorical values indicating the blood pressure level of the individuals. Categories include:
HIGH
NORMAL
LOW
Cholesterol:

Categorical values indicating cholesterol levels, such as:
HIGH
NORMAL
Na_to_K (Sodium-to-Potassium Ratio):

A numerical feature representing the ratio of sodium to potassium levels in the blood. This ratio is likely a key indicator in the drug selection process.
Drug:

Categorical target variable representing the drug prescribed to the individual. Examples include:
DrugY
drugC
drugX
Dataset Characteristics:
Size: 200 rows and 6 columns.
Data Types:
Numerical: Age and Na_to_K.
Categorical: Sex, BP, Cholesterol, and Drug.
Completeness: There are no missing values in the dataset.
Potential Analyses:
Classify drug prescriptions:

Determine how features like age, gender, BP, cholesterol, and sodium-to-potassium ratio influence drug selection.
Explore health patterns:

Examine correlations between health metrics (e.g., Na_to_K, BP) and prescribed drugs.
Demographic breakdown:

Analyze the distribution of drugs prescribed across different age groups and genders.
Risk factor assessment:

Identify thresholds in Na_to_K and their relation to drug types.


code to identify drug is most commonly prescribed to individuals with high blood pressure and high cholesterol

high_bp_chol = drug_data[(drug_data['BP'] == 'HIGH') & (drug_data['Cholesterol'] == 'HIGH')]
most_common_drug = high_bp_chol['Drug'].value_counts().idxmax()
most_common_drug_count = high_bp_chol['Drug'].value_counts().max()
most_common_drug, most_common_drug_count

code to  Find the most frequent age range and sodium-to-potassium ratio range for individuals prescribed DrugX

drug_x_data = drug_data[drug_data['Drug'] == 'drugX']
na_to_k_bins = pd.cut(drug_x_data['Na_to_K'], bins=5)
most_common_age_range = drug_x_data['AgeGroup'].mode()[0]
most_common_na_to_k_range = na_to_k_bins.mode()[0]
most_common_age_range, most_common_na_to_k_range
