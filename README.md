# ACHE-Inhibitor-ML-Model
A cheminformatics project using Python and machine learning to analyze and predict the bioactivity of compounds against the AChE protein, with hyperparameter tuning via GridSearchCV.
This project presents a complete machine learning workflow to predict the bioactivity of compounds against the Acetylcholinesterase (AChE) protein. Acetylcholinesterase is a critical drug target, particularly in the treatment of Alzheimer's disease. The goal of this project is to build a robust model that can predict the bioactivity (inhibitory power) of new compounds, thereby accelerating the drug discovery process.

Methodology and Workflow
The project is structured into several key phases:

Data Acquisition and Preprocessing:

Bioactivity data for compounds targeting AChE is retrieved from the ChEMBL database using the chembl_webresource_client library.

The data is meticulously cleaned, and missing values are handled. Inactive and ambiguous data points are filtered out to ensure the dataset is high-quality.

Compound bioactivity values (IC50) are converted to the standardized pIC50 format, which is a logarithmic scale better suited for machine learning models.

Exploratory Data Analysis (EDA):

The cleaned data is visualized to understand its distribution and characteristics.

A custom function is used to calculate the Lipinski's Rule of Five, a set of rules used to evaluate the drug-likeness of a compound. The results are visualized to show which compounds adhere to these rules.

A comparison of the molecular properties of active and inactive compounds is performed to identify key structural differences.

Molecular Descriptors and Feature Engineering:

Molecular descriptors, which are numerical representations of a molecule's properties, are calculated using the PaDEL-Descriptor software. These descriptors serve as the features for the machine learning model.

The generated features are preprocessed to remove highly correlated columns and reduce multicollinearity, improving the model's performance.

Model Building and Evaluation:

The dataset is split into training and testing sets.

A Random Forest Regressor model is chosen for its robustness and ability to handle complex, non-linear relationships.

Grid Search with cross-validation (GridSearchCV) is used to systematically tune the model's hyperparameters (such as n_estimators, max_features, and max_depth). This process finds the optimal set of parameters that result in the best predictive accuracy.

The best-performing model is then used to make predictions on the unseen test set. The model's performance is evaluated using the R-squared score, which measures how well the predictions align with the actual values.

Technologies Used
Python: The core programming language for the entire project.

Jupyter Notebook: Used for an interactive and reproducible analysis.

Pandas: For efficient data manipulation and analysis.

scikit-learn: For building and evaluating the machine learning models.

RDKit: A cheminformatics library used for handling molecular structures and properties.

Matplotlib: For data visualization and creating informative plots.

chembl_webresource_client: To programmatically access the ChEMBL database.

PaDEL-Descriptor: An external tool used to generate molecular descriptors.
