# Airline Operations and Performance Dashboard

An interactive Power BI dashboard for exploring airline flight activity, passenger demand, route revenue and profitability, and arrival-delay performance.

## Dashboard

Open [AIRLINE_DASHBOARD.pbix](./AIRLINE_DASHBOARD.pbix) in Microsoft Power BI Desktop. The report includes:

- **KPI cards:** total flights, total passengers, total revenue, total profit, average arrival delay, and on-time performance.
- **Passengers by destination:** compares passenger volume across destinations.
- **Monthly revenue trend:** shows how revenue changes over time.
- **Top 10 profitable routes:** ranks routes by profit.
- **Average arrival delay by destination:** compares delay performance by destination.

The visuals are interactive; selecting a data point in a chart can filter or highlight related values in other visuals.

## Project files

| File | Description |
| --- | --- |
| [AIRLINE_DASHBOARD.pbix](./AIRLINE_DASHBOARD.pbix) | Power BI report and embedded model. |
| [RAW_DATA.csv](./RAW_DATA.csv) | Original 7,974-row airline dataset, including delay and cancellation fields. |
| [CLEAN_DATA.csv](./CLEAN_DATA.csv) | Cleaned 7,974-row airline dataset with 33 columns; delay and cancellation fields are excluded. |
| [simulated_flight_delays.csv](./simulated_flight_delays.csv) | Separate 500-row sample of simulated flight delays, dated from January 2026 to May 2027. |
| [airlines.ipynb](./airlines.ipynb) | Notebook for downloading, cleaning, and preparing airline data, and generating sample delay data. |

The raw and cleaned airline datasets cover January–December 2024. The notebook downloads the `waleedfaheem/airline-route-profitability-and-cost-analysis` dataset with KaggleHub, removes duplicates and rows missing available essential fields, converts data types, recalculates load factor when its inputs are present, and writes a cleaned CSV.

## Data and delay caveat

The notebook generates `Arrival_Delay` and `Cancelled` values for the cleaned airline records using a random simulation (seed 42). These are **simulated values, not observed operational outcomes**. It writes an enriched file named `airline_data_with_delays.csv`; that generated file is not included in the current project folder.

`simulated_flight_delays.csv` is a separate sample dataset. It is not a record-level match for the 2024 airline data, and its dates and flight identifiers do not describe the same dataset. Do not treat either simulated source as actual airline on-time performance.

## Reproducing the notebook workflow

1. Open `airlines.ipynb` in Jupyter Notebook or JupyterLab.
2. Use a Python environment with `kagglehub`, `pandas`, and `numpy` installed.
3. Run the cells in order. The first cells download the source data via KaggleHub; this requires internet access and access to the dataset.
4. The cleaning step writes `cleaned_airline_data.csv` to the notebook's working directory. Later cells generate sample delay data and an enriched `airline_data_with_delays.csv`.

The notebook's download-and-clean process is separate from the CSV files already included in the project directory.

## Tools

- Microsoft Power BI Desktop
- Python and Jupyter
- Python packages: `kagglehub`, `pandas`, and `numpy`
