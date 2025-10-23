
# Historical Data CSV Loader (Google Colab)

This Colab notebook allows you to upload and load the `historical_data.csv` file into a pandas DataFrame for analysis.

## Steps to Use

1. Open the Colab notebook.
2. Run the code cell that uploads `historical_data.csv`.
3. A file picker will appear — select `historical_data.csv` from your local machine.
4. The CSV will be loaded into a pandas DataFrame called `df_trader`.
5. The notebook will display:
   - Number of rows and columns
   - Column names (first 15 columns)
   - Sample data (first 5 rows)

## Example Code

```python
import pandas as pd
from google.colab import files
import io
from IPython.display import display

# Upload and read the CSV
uploaded_trader = files.upload()  # Select historical_data.csv
trader_path = list(uploaded_trader.keys())[0]
df_trader = pd.read_csv(io.BytesIO(uploaded_trader[trader_path]))

print("✅ Trader data loaded:", df_trader.shape)
display(df_trader.head())
