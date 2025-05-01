# Survival Analysis & Customer Lifetime Value (CLV) for Telco Churn

This repository contains the code and report for Homework 3 in Survival Analysis, focused on modeling subscriber churn using accelerated failure-time (AFT) models and computing per-customer CLV. We compare Weibull, Log-Normal, Log-Logistic, and Exponential distributions, select the best-fit model by AIC, refit on significant covariates, and estimate an annual retention budget.

## Repository Structure


├── README.md               ← this file  
├── telco.csv               ← raw dataset (subscriber churn & demographics)   
├── Analysis.ipynb   ← Jupyter notebook with code, tables, plots & write-up  
├── requirements.txt        ← Python dependencies   


## Data Description

The \`telco.csv\` dataset includes 1 000 subscribers with these key columns:

- ID: unique subscriber identifier  
- region: geographic zone  
- tenure: months until churn or censoring  
- age: subscriber age  
- marital, retire, gender, ed: demographic factors  
- address: years at current address  
- income: annual income (K USD)  
- voice, internet, forward, custcat: service usage & category  
- churn: event flag (1 = churn, 0 = retained)  

## Installation

1. Clone the repository
   git clone git@github.com:manekoshkaryan/Survival_analysis_Homework_3.git
   cd telco-survival-clv
3. Install dependencies


   pip install -r requirements.txt


## Usage

### Run the script

python analysis.py


This will preprocess the data, fit all AFT models, plot survival curves, refit the final model, compute CLV, and print segment summaries and the retention budget.

### Explore in the notebook

Open analysis.ipynb in JupyterLab or Jupyter Notebook to see:

- Detailed model fitting steps  
- AIC comparison table  
- Survival curve plots  
- Final model summary & coefficient interpretations  
- CLV distributions by segment (KDE plots)  
- Markdown write-up of findings  


## Key Findings

- Best fit: Log-Normal AFT (AIC = 2954) captures early-peak churn then slower long-term exit  
- Top predictors: tenure at address, age, and service-bundle upgrades (E-Service, Plus, Total)  
- Churn accelerators: internet service, unmarried status, voice service  
- High-value segments: retirees (~\$52 K CLV), Plus-plan users (~\$47 K CLV), Basic + no-internet (~\$45 K CLV)  
- Retention budget: \$27.8 M to retain 80% of at-risk subscribers at \$5 K each  
- Recommendations: targeted loyalty perks for retirees/premium users, bundle discounts for vulnerable cohorts, and first-year engagement campaigns  

## License

This work is provided under the MIT License. Feel free to adapt or extend for your own analysis!
EOF