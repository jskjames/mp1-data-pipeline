# MP1 End-to-End Data Pipeline

This project is a command-line data pipeline that loads, validates, cleans, and saves data. The pipeline first checks that the input and configuration files exist and then loads both files. The validation module checks for required columns, removes rows with invalid numeric values, and converts configured columns to numeric data types. The processing module removes duplicate rows, handles missing values, and removes outliers according to `config/config.yaml`. The output module creates the output directory when needed and saves the cleaned data as a CSV file. The `src` directory contains the loading, validation, processing, output, and utility modules, while `pipeline.py` coordinates the complete workflow. After the pipeline finishes, it prints a cleaning report that summarizes the rows and columns removed.

## Example command

```bash
python pipeline.py --input fixtures/sample_data.csv --output output/clean.csv --config config/config.yaml --verbose
```

## Example output

The provided sample data begins with 100 rows. Validation removes 2 rows with invalid numeric values, and processing removes duplicate rows, rows with missing values, and rating outliers. The cleaned CSV contains 92 rows and is saved to `output/clean.csv`.
