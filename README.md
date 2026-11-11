# EstateWise AI

EstateWise AI is a Streamlit app that explores historical residential flat listings in India and estimates asking prices from property details.

## Features

- Explore and clean property listing data
- Train and evaluate regression models for asking price estimates
- Try estimates in an interactive Streamlit app

## Setup on Windows

Install Git and Python 3.13. From PowerShell, run these commands:

```powershell
git clone https://github.com/Sahelisau/EstateWise-AI.git
cd EstateWise-AI
py -3.13 -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Add the dataset

The dataset is not included in the source files. Download the [House Price dataset on Kaggle](https://www.kaggle.com/datasets/juhibhojani/house-price), create the folder below, and place the original archive there with this filename:

`data/raw/india_property_listings_81_cities.zip`

```powershell
New-Item -ItemType Directory -Force data\raw | Out-Null
```

Check the dataset license and attribution before sharing the data. The project code license does not cover the dataset.

## Prepare the data and train the model

Run these from the project folder, waiting for each step to finish:

```powershell
.\.venv\Scripts\python.exe -m src.eda
.\.venv\Scripts\python.exe -m src.train
```

## Start the app

```powershell
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Open the local URL shown in the terminal. Press Ctrl+C there to stop the app.

## Data limitations

The listings contain asking prices, not confirmed sale prices. They are a snapshot without listing dates, so the model estimates prices from property details. It does not forecast future prices, show current availability, or provide a professional property valuation.
