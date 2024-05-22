# moneycontrol

# ETL and Tableau Visualization Project

## Overview

This project is an end-to-end ETL (Extract, Transform, Load) pipeline that reads various types of financial data from Moneycontrol.com, processes it using Python, stores it in MS SQL Server, and visualizes it with Tableau. The data includes trending news, active Indian market indices, active stocks, top gainers, top losers, and the top Indian companies based on market capitalization along with their 52-week stock movements.

## Project Workflow

1. **Data Extraction:**
   - Web scraping using BeautifulSoup in Python to gather data from Moneycontrol.com.
   - Data types include:
     - Trending news
     - Active Indian market indices
     - Active stocks
     - Top gainers
     - Top losers
     - Top Indian companies by market cap and their 52-week stock movements

2. **Data Transformation:**
   - Data wrangling in Python:
     - Removing null values from dataframes
     - Generating basic statistics for data quality and integrity checks
   - Loading cleaned data into MS SQL Server using SQLAlchemy

3. **Data Loading:**
   - Storing processed data in MS SQL Server
   - Performing additional data transformations and queries in SQL Server for column renaming and to answer specific analytical questions

4. **Data Visualization:**
   - Loading the processed data into Tableau
   - Creating dashboards with 3 tables and 5 different charts to provide insights

## Prerequisites

- **Python Libraries:**
  - BeautifulSoup
  - Requests
  - Pandas
  - SQLAlchemy
  - PyODBC (for connecting to MS SQL Server)

- **Database:**
  - MS SQL Server

- **Visualization:**
  - Tableau

## Setup and Installation

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
   ```

2. **Install Required Python Libraries:**
   ```sh
   pip install beautifulsoup4 requests pandas sqlalchemy pyodbc
   ```

3. **Database Configuration:**
   - Ensure MS SQL Server is installed and running.
   - Update the database connection string in the `config.py` file.

4. **Run the ETL Script:**
   ```sh
   python etl_script.py
   ```

5. **Tableau Visualization:**
   - Open Tableau
   - Connect to the MS SQL Server database
   - Load the data and create dashboards

## Detailed Steps

### Data Extraction

- **Web Scraping:**
  - The script `scraper.py` contains functions to scrape data from Moneycontrol.com using BeautifulSoup.
  - Data is fetched for various categories such as trending news, market indices, active stocks, top gainers, and losers.

### Data Transformation

- **Data Wrangling:**
  - The script `data_wrangling.py` processes the scraped data.
  - Null values are removed, and basic statistics are computed for each dataframe.

### Data Loading

- **Loading into MS SQL Server:**
  - Using SQLAlchemy, the cleaned data is loaded into MS SQL Server.
  - Further transformations and queries are performed directly in SQL Server for final data preparation.

### Data Visualization

- **Tableau Dashboard:**
  - Connect Tableau to the MS SQL Server database.
  - Create interactive dashboards that include:
    - 3 tables summarizing key data points
    - 5 different charts to visualize trends and insights

## Project Structure

```plaintext
.
├── data/
│   ├── raw/
│   ├── processed/
├── scripts/
│   ├── scraper.py
│   ├── data_wrangling.py
│   ├── etl_script.py
├── tableau/
│   ├── dashboard.twb
├── README.md
├── requirements.txt
└── config.py
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

## License

This project is licensed under the MIT License.
