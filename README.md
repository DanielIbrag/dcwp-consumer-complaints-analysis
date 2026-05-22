# NYC DCWP Consumer Complaints Analysis

An exploratory data analysis of consumer complaints filed with the NYC Department of Consumer and Worker Protection (DCWP), using Python, SQL, and public open data.

## Overview

This notebook pulls ~66,000 complaint records from the [NYC Open Data portal](https://data.cityofnewyork.us/Business/DCWP-Consumer-Complaints/nre2-6m2s) (2019–present) and investigates patterns in how complaints are filed, resolved, and distributed across the five boroughs.

## Key Questions Explored

- **Trend analysis**: How have complaint volumes changed year-over-year, and which complaint types are growing fastest?
- - **Borough breakdown**: Which complaint categories dominate in each borough?
  - - **Resolution time**: How quickly are complaints resolved, and what share take longer than 30/90 days?
    - - **Intake channels**: How do New Yorkers file complaints — phone, online, in person?
      - - **Price-related complaints**: How has price gouging and overcharge activity shifted over time?
       
        - ## Data Source
       
        - | Field | Value |
        - |---|---|
        - | Dataset | DCWP Consumer Complaints |
        - | Publisher | NYC Open Data |
        - | Records | ~66,800 |
        - | Coverage | 2019 – present |
        - | API Endpoint | `https://data.cityofnewyork.us/resource/nre2-6m2s.json` |
       
        - ## How to Run
       
        - 1. Clone the repo:
          2.    ```bash
                   git clone https://github.com/DanielIbrag/dcwp-consumer-complaints-analysis.git
                   cd dcwp-consumer-complaints-analysis
                   ```

                2. Open the notebook:
                3.    ```bash
                         jupyter notebook nyc_consumer_complaints_analysis.ipynb
                         ```

                      3. Run all cells. Dependencies (`pandas`, `numpy`, `matplotlib`, `seaborn`, `requests`) are auto-installed in the first cell if not already present.
                  
                      4. > **Note:** The notebook fetches live data from the NYC Open Data API on each run, so results will reflect the most current dataset.
                         >
                         > ## Tech Stack
                         >
                         > - **Python 3.9+** — data fetching, ETL, visualization
                         > - - **pandas / numpy** — data wrangling and feature engineering
                         >   - - **matplotlib / seaborn** — charts and figures
                         >     - - **SQLite (in-memory)** — SQL analysis including window functions (`LAG`, `RANK OVER PARTITION BY`) and CTEs
                         >       - - **NYC Open Data SODA API** — paginated data retrieval
                         >        
                         >         - ## Selected Findings
                         >        
                         >         - - Complaint volumes spiked sharply during 2020–2021, driven by price gouging complaints during the COVID-19 pandemic.
                         >           - - Brooklyn and the Bronx account for the highest share of unresolved complaints by borough.
                         >             - - The majority of complaints are resolved within 30 days, but a meaningful tail extends beyond 90 days.
                         >               - - Online submission has grown as the dominant intake channel, overtaking phone complaints by 2022.
                         >                
                         >                 - ## Author
                         >                
                         >                 - Daniel Ibragimov — [dannyibragimov1@gmail.com](mailto:dannyibragimov1@gmail.com)
