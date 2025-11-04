# Apple-Microsoft-A-Comparative-Financial-Performance-Analysis-2010-2024

# Financial Performance Analysis: Apple vs. Microsoft (2010-2024)

This repository contains the files and analysis for a comprehensive Power BI dashboard project comparing the financial performance, operational efficiency, and future outlook of Apple and Microsoft over a 15-year period.
---

## 📊 Project Objective

This project goes beyond simple reporting to answer the "why" and "how" behind the performance of these two tech giants. The dashboard is built as a 4-page story:
* **Page 1: The "What"** - A high-level executive summary.
* **Page 2: The "How"** - A deep dive into profitability and cost structures.
* **Page 3: The "Deeper Why"** - An analysis of operational efficiency and leverage.
* **Page 4: The "What's Next"** - A forward-looking forecast and model comparison.

---

## 🛠️ Tools & Technologies
* **Data Extraction:** Python (Pandas, Requests) in Google Colab
* **Data Source:** Alpha Vantage API
* **Data Cleaning:** Power BI (Power Query)
* **Data Modeling:** Power BI (DAX, Star Schema)
* **Data Visualization:** Power BI Desktop
* **Comparative Forecasting:** Python (Scikit-learn) & Power BI

---

## 📈 Project Phases

### 1. Data Acquisition (Python)
* Used Python's `requests` library to connect to the Alpha Vantage API.
* Fetched 15+ years of annual income statement data for both AAPL and MSFT.
* Combined and saved the raw data into a single CSV file.

### 2. Data Preparation (Power Query)
* Filtered the data to include only **annual reports** from **2010 to 2024** for a balanced comparison.
* Normalized all financial figures (dividing by 1 billion) to create "($B)" metrics for readability.
* Created a custom `Dim_Date` (Calendar) table to enable robust time-intelligence functions.

### 3. Data Modeling & DAX
* Established a clean **Star Schema** relationship (Many-to-One) between the `Financials` (Fact) table and the `Dim_Date` (Dimension) table.
* Authored **15+ advanced DAX measures** to power the analysis, including:
    * **Profitability:** `Gross Margin %`, `Operating Margin %`, `Net Margin %`
    * **Growth:** `Revenue YoY Growth %`, `Operating Income YoY Growth %`, `Revenue CAGR %`
    * **Efficiency:** `Cost Efficiency Ratio`, `Cost of Revenue %`, `R&D %`, `SG&A %`
    * **Forecasting:** `Revenue for Forecast` (a robust measure to handle data gaps for the forecast engine).

### 4. Dashboard Design & Key Insights
The dashboard consists of 4 main pages + 1 hidden drillthrough page.

#### Page 1: Executive Summary
* **(Insert Screenshot of Page 1)**
* **Purpose:** A one-glance overview of performance.
* **Key Insight:** Apple dominates in scale, but Microsoft shows superior operational efficiency (higher Operating Margin %).

#### Page 2: Profitability Deep Dive
* **(Insert Screenshot of Page 2)**
* **Purpose:** To explain *how* and *why* their profit models differ.
* **Key Insight:** Microsoft's high Gross Margin (~70%) is explained by its low Cost of Revenue (~30%) for software, while Apple's is lower (~46%) due to high hardware costs (~54%).

#### Page 3: Operational Efficiency & Leverage
* **(Insert Screenshot of Page 3)**
* **Purpose:** To measure *how efficiently* each company scales and spends.
* **Key Insight:** Microsoft demonstrates superior efficiency, generating ~$0.98 in profit per $1 of OpEx vs. Apple's ~$0.46. It also shows stronger operating leverage (profit growing faster than sales).

#### Page 4: Forecasting & Trends
* **(Insert Screenshot of Page 4)**
* **Purpose:** To project future performance and compare forecasting methods.
* **Key Insight:** Power BI's forecast (which weighs recent trends) is optimistic for Microsoft. The simpler Python (Linear Regression) model is more pessimistic, highlighting the sensitivity of forecasts to the chosen model.

### 5. Python Forecasting Integration
* Used **Python (Scikit-learn)** to build a simple Linear Regression model on the historical revenue data.
* Exported the forecast results (2025-2028) to a CSV.
* Imported this CSV back into Power BI to create a comparison chart showing:
    1.  Actual Historical Revenue
    2.  Power BI's Forecast
    3.  Python's Forecast

---

## 🚀 Key Conclusions
* **Apple: Champion of Scale.** Success is driven by its massive revenue, brand power, and hardware ecosystem.
* **Microsoft: Champion of Efficiency.** Success is driven by its high-margin software/cloud model, superior cost efficiency, and strong operating leverage.
* **Future:** Both are strong, but Microsoft's operational model shows greater efficiency momentum, projecting it to nearly close the absolute profit gap with Apple by 2028.
