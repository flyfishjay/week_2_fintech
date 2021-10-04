# week_2_fintech-- Loan Qualifier app 

The Goal of the project is to dynamically ask for loan applicant data in order to filter
the loans that qualify(ie approved) by a pre-determined bank list.  This program was built using Jupyter lab 
but must be run from the terminal (GitBash) using the app.py file.



Technology used: 
This project was created using the following tech versions in Windows:
python 3.8.8
questionary 1.10.0
pathlib2 2.3.5 
fire 0.4.0
csv 
winpty



Installation:
"""Loan Qualifier Application.

This is a command line application to match applicants with qualifying loans.

Example:
    $ python app.py
"""
import sys
import fire
import questionary
from pathlib import Path

from qualifier.utils.fileio import load_csv, save_csv

from qualifier.utils.calculators import (
    calculate_monthly_debt_ratio,
    calculate_loan_to_value_ratio,
)

from qualifier.filters.max_loan_size import filter_max_loan_size
from qualifier.filters.credit_score import filter_credit_score
from qualifier.filters.debt_to_income import filter_debt_to_income
from qualifier.filters.loan_to_value import filter_loan_to_value


Usage: 
Run app.py form the CLI (GitBash)
Questionary will ask the user for input reharding loan and bank metrics

    credit_score = questionary.text("What's your credit score?").ask()
    debt = questionary.text("What's your current amount of monthly debt?").ask()
    income = questionary.text("What's your total monthly income?").ask()
    loan_amount = questionary.text("What's your desired loan amount?").ask()
    home_value = questionary.text("What's your home value?").ask()

Loan filters applied: 
  bank_data_filtered = filter_max_loan_size(loan, bank_data)
    bank_data_filtered = filter_credit_score(credit_score, bank_data_filtered)
    bank_data_filtered = filter_debt_to_income(monthly_debt_ratio, bank_data_filtered)
    bank_data_filtered = filter_loan_to_value(loan_to_value_ratio, bank_data_filtered)




Contributors:
FinTech Bootcamp
Jason Muenzen at jmuenzen@gmail.com and linkedin: www.linkedin.com/in/jason-muenzen-mba-frm


License governing this code:  GNU General Public License v2.


