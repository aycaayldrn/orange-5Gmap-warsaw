# Orange 5G Coverage Analysis in Warsaw

## Project Overview
This project provides a geospatial analysis of **5G coverage in Warsaw**, focusing on the performance of **Orange** in comparison to its major competitors: **Play, Plus, and T-Mobile**. The analysis utilizes:
- **Ookla's Open Dataset** for mobile speed tests
- **Operator-specific 5G coverage data** for geo-spatial mapping
- **GeoPandas** and **Folium** for interactive map visualizations
- **KPI metrics** for evaluating network performance and coverage superiority

---

## Features
1. **Geospatial Data Slicing:**  
   - Extracted Warsaw-specific data from nationwide datasets using boundary masks.

2. **5G Operator Mapping:**  
   - Visualized coverage areas for:
     - 🟧 Orange
     - 🟪 Play
     - 🟩 Plus
     - 🟨 T-Mobile  

3. **Interactive Folium Map:**  
   - Multi-layered visualization to toggle between operators.
   - Color-coded for clear distinction and better visual analytics.

4. **Heatmap Representation:**  
   - Displayed the distribution and density of Ookla download speeds across Warsaw.

5. **KPI Metrics Calculation:**  
   - Area coverage in square kilometers (km²).
   - Average download and upload speeds.
   - Latency analysis for each operator.
   - Total number of tests and unique devices per area.

6. **Competitive Analysis:**  
   - Highlighted regions where:
     - Orange outperforms others (Green)
     - Others outperform Orange (Red)
     - Marginal differences (< 5 Mbps) (Yellow)

7. **Performance Report Generation:**  
   - Exported results to:
     - `5g_success_coverage_percentage.csv` → Coverage statistics
     - `warsaw_5g_performance_map.html` → Interactive map for presentation

---

## 🗂️ Project Structure
```
orange-5Gmap-warsaw/
│
├── data/                         # Original datasets
│   ├── warsaw_boundary.geojson    # Warsaw boundary polygons
│   ├── operators_5g_coverage.geojson # Operator-specific coverage data
│   ├── gminy.shp                  # Administrative boundary shapes
│   └── warsaw_mobile_q4_2024.parquet # Ookla speed test data
│
├── notebooks/                    # Jupyter Notebooks for analysis
│   ├── 01_data_loading.ipynb      # Load and pre-process data
│   ├── 02_data_slicing.ipynb      # Slice data by Warsaw boundaries
│   ├── 03_operator_coverage.ipynb # Generate operator maps
│   └── 04_kpi_analysis.ipynb      # Calculate KPIs and export results
│
├── outputs/                      # Generated outputs (Git LFS tracked)
│   ├── orange_5g_coverage_warsaw.geojson
│   ├── play_5g_coverage_warsaw.geojson
│   ├── plus_5g_coverage_warsaw.geojson
│   ├── tmobile_5g_coverage_warsaw.geojson
│   ├── warsaw_5g_performance_map.html
│   └── 5g_success_coverage_percentage.csv
│
├── requirements.txt              # List of dependencies
├── main.py                       # Main execution script (optional)
├── .gitattributes                # Git LFS configuration
├── .gitignore                    # Ignored files and folders
└── README.md                     # Project documentation
```




## Installation
1. **Clone the repository**:
    ```bash
    git clone https://github.com/aycaayldrn/orange-5Gmap-warsaw.git
    cd orange-5Gmap-warsaw
    ```

2. **Create a virtual environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate    # On Windows use: venv\Scripts\activate
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

---

## Usage
To execute the analysis and generate the maps:
```bash
jupyter notebook
```

## KPI Analysis
The following metrics are calculated and exported to CSV:

| **Metric**                 | **Description**                                       |
|----------------------------|-------------------------------------------------------|
|  **Coverage Area (km²)**   | Total coverage area for each operator                 |
|  **Download Speed (Mbps)** | Average download speed across regions                 |
|  **Upload Speed (Mbps)**   | Average upload speed across regions                   |
|  **Latency (ms)**          | Average latency per operator                          |
|  **Device Count**          | Total unique devices tested                           |

---

## Interactive Map Preview
The interactive map is available in:  
**`warsaw_5g_performance_map.html`**

- **Click on each layer** to see operator-specific coverage.
- **Toggle layers** to analyze overlapping zones.
- **Zoom and Pan** to explore Warsaw's 5G coverage in detail.
