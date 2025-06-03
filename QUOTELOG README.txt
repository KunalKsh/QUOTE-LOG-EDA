# 📊 Motor Insurance Quote Log Analysis

This project offers an end-to-end data analysis solution for motor insurance quote logs using Python. It features robust data cleaning, standardization, rejection reason mapping, and dynamic visualizations via interactive dashboards. Built with pandas, matplotlib, plotly, and ipywidgets, it enables users to explore insurer performance, rejection trends, and revenue metrics across various dimensions.

---

## 🚀 Features

This project combines structured preprocessing, business logic, and powerful visualizations to deliver actionable insights:

### 🔹 Excel Integration
- Loads `.xlsx` files using `openpyxl` and `pandas`.
- Automatically identifies and loads the first sheet.
- Assigns the first row as column headers and resets index for clean formatting.

### 🔹 Data Preprocessing
- Cleans column names by removing whitespace and standardizing text.
- Converts date columns using `pd.to_datetime()` and extracts `Month` in `YYYY-MM` format.

### 🔹 Manufacturer Name Standardization
- Maps 50+ inconsistent manufacturer entries (e.g., `"HERO MOTOCORP LTD"`, `"Hero Honda"`) to a clean `"Hero"` format.
- Uses `replace()` and `.str.strip()` for accurate grouping.

### 🔹 Body Type Categorization
- Consolidates similar entries (e.g., `"MOTOR CYCLE"`, `"BIKES"`) into standardized labels like `"Bike"`, `"Scooter"`, etc.

### 🔹 Rejection Reason Mapping
- Groups common failure modes (e.g., `"Endpoint request timed out"`, `"Invalid IDV Range"`) into human-readable categories.
- Supports quick filtering of rejection causes for diagnostics.

### 🔹 Exploratory Data Analysis (EDA)
- Identifies top insurers, states, dealers, and body types.
- Uses bar charts with exact counts and sorting to highlight high-frequency data.
- Approval vs rejection analysis with percentage overlays.

### 🔹 Interactive Dashboard
- Built with `ipywidgets`, `matplotlib`, and `plotly` for full interactivity.
- Filters available:
  - Month
  - ACPL State
  - Vehicle Body Type
  - Vehicle Manufacturer
- Visual outputs update dynamically:
  - Sunburst chart of Insurer → Branch → Rejection Status
  - Combined Table: Total Revenue, Average Revenue, Rejected True/False Counts

---


---

## 🧠 Features & Logic Used

This project combines structured preprocessing, robust business logic, and interactive visualization to analyze quote performance in the motor insurance domain.

### 🔸 1. Data Loading & Preparation
- Reads raw Excel file using `openpyxl` and `pandas`.
- Automatically detects the first sheet and uses its first row as headers.
- Strips whitespace and standardizes column names.

### 🔸 2. Manufacturer Standardization
- Uses a mapping dictionary to clean 50+ variations of vehicle manufacturers into standardized brand names.
- Improves grouping and consistency in charts and aggregations.

### 🔸 3. Body Type Normalization
- Maps entries like "MOTOR CYCLE", "BIKES", "SOLO", etc. to consistent body types like "Bike", "Scooter", or "Electric Scooter".

### 🔸 4. Rejection Reason Categorization
- Unifies multiple verbose rejection texts into key reasons:
  - `"Invalid Idv Range"` → `"IDV RANGE ERROR"`
  - `"variant is not-available"` → `"VARIANT UNAVAILABLE"`
  - `"Endpoint request timed out"` → `"TIME OUT ERROR"`
- Helps identify trends and bottlenecks in the quote process.

### 🔸 5. Interactive Visual Dashboards
- Built using `plotly` + `ipywidgets` in Jupyter.
- Filters data dynamically by:
  - Month
  - ACPL State
  - Vehicle Body Type
  - Vehicle Manufacturer
- Updates:
  - Sunburst chart: Insurer → Branch → Rejected/Approved
  - Revenue table with total and average revenue
  - Rejection stats with success rates

---

## 📂 Project Structure
📁 quote-log-analysis/
├── QUOTELOG-CODE.ipynb # Main Jupyter notebook with full code & widgets
├── data/
│ └── QUOTE LOGS.xlsx # Raw input Excel data
├── README.md # Project documentation (this file)
├── requirements.txt # Python dependencies
└── assets/ # Optional folder for screenshots/exports

