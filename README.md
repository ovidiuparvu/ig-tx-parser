# IG.com transaction history parser

This repository contains improperly tested prototype code.

## How to download transaction history from IG.com?

Steps:
1. Log into your IG.com account.
2. Click the top-right dropdown containing your profile name and the "My IG" text.
3. Click the "My IG" button from the dropdown.
4. Click the "Live Accounts" panel.
5. From the dropdown under "You are viewing:" select the account for which the transaction history should be printed.
6. Click the "History" button from the navigation bar on the left side of the window.
7. From the "Date" dropdown click "Custom period".
8. Set the date period for which the transaction history should be printed (e.g. 01/01/2015-05/04/2022).
    - Note that the transaction history should include BUY transactions that are outside the date range for which capital gains should be computed. This is in order to be able to compute the difference between the SELL and the BUY price of the financial products sold during the date range for which capital gains should be computed.
9. Click the "Show History" button.
10. Click the "Download CSV" button.

## How to parse the transaction history downloaded from IG.com?

Steps:
1. Clone this repository locally.
2. Set up python in the environment in which you want to parse the transaction history.
3. Install the python virtualenv package if it is not installed already.
```bash
python -m pip install -U virtualenv
```
4. Create and activate a new Python virtual environment for the transaction history parsing.
```bash
python -m venv venv;
. venv/bin/activate;
```
5. Install the required Python packages using the `requirements.txt` file from this repository.
```bash
python -m pip install -r requirements.txt
```
6. Run JupyterLab.
```bash
jupyter-lab
```
7. Open in JupyterLab the `PrintCapitalGains.ipynb` notebook from this repository.
8. At the bottom of the first cell in the notebook update the value of the:
    1. `tx_history_file_path` variable to point to the transaction history csv file downloaded from IG.com.
    2. `start_financial_year` and/or `start_datetime` and `stop_datetime` variables in order to define the date range for which capital gains should be computed.
9. Run all the cells in the notebook.
