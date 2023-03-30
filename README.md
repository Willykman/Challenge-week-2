# Challenge-week-2
Loan Qualifier Application
Uses Python to match potential loan borrowers with various banks in a list based on filtering through standard customer data such as credit scores, debt-to-income ratio, etc.

This app queries the customer on various financial data to match qualifying loans.

IThe following edits/additions were madee to the provided code.

Edited provided line code from
from qualifier.utils.fileio import load_csv
to
from qualifier.utils.fileio import load_csv, save_csv

Added if statement with questions to save qualifying loans and one for path.
    if not qualifying_loans:
        sys.exit("Sorry, there are no qualifying loans!")

    saveFile = questionary.confirm("Would you like to save the qualifying loans?").ask()

    if saveFile:
        csvpath = questionary.text(
            "Please enter a filepath for the saved data: (,/)"
        ).ask()
        save_csv(Path(csvpath), qualifying_loans)
        
        

