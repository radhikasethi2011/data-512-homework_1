# data-512-homework_1


## How to Reproduce the Analysis

If you want to run the analysis yourself, here’s a step-by-step guide.

### 1. Clone the Repo

First, you need to get the code. Open your terminal, and run:

```bash
git clone https://github.com/yourusername/data-512-homework_1.git
cd data-512-homework_1
```

### 2. Install the Required Libraries

Make sure you have Python (preferably 3.7 or above). You’ll also need some Python libraries to make everything work. You can install them by running:

```bash
pip install -r requirements.txt
```

The main libraries we’re using:
- **requests**: For pulling data from the Wikimedia API.
- **pandas**: For handling the data.
- **matplotlib**: For creating graphs.

### 3. Data Acquisition

You’ll need to collect the pageview data using the Wikimedia Pageviews API. Open the Jupyter notebook and run the code:

```bash
jupyter notebook notebooks/data_acquisition.ipynb
```

This will:
- Get monthly pageviews for desktop and mobile for each article.
- Save the data in the `data/` folder as three JSON files:
  - `rare-disease_monthly_mobile_201507-202409.json`
  - `rare-disease_monthly_desktop_201507-202409.json`
  - `rare-disease_monthly_cumulative_201507-202409.json`

### 4. Data Processing & Analysis

After you’ve got the data, you can process and analyze it by running the analysis notebook:

```bash
jupyter notebook notebooks/data_analysis.ipynb
```

This will:
- Process the JSON files you collected.
- Create three graphs showing pageview trends:
  - Max and Min Average Page Views
  - Top 10 Peak Page Views
  - Fewest Months of Data
- Save the graphs as PNG files in the `images/` folder.

### 5. Output Files

Here’s what the code will generate:

- **Data Files (in JSON format):**
  - `rare-disease_monthly_mobile_201507-202409.json`: Monthly mobile pageview data (web + app).
  - `rare-disease_monthly_desktop_201507-202409.json`: Monthly desktop pageview data.
  - `rare-disease_monthly_cumulative_201507-202409.json`: Total monthly pageviews (desktop + mobile).

- **Graphs (in PNG format):**
  - `max_min_avg_views.png`: Line graph showing max and min average page views for desktop and mobile.
  - `top_10_peak_views.png`: Line graph showing the top 10 peak pageviews for desktop and mobile.
  - `fewest_months_data.png`: Line graph showing articles with the fewest months of data.

---

## Data Description

We’re working with pageview data from the [Wikimedia Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html), which provides views for articles on Wikipedia. The articles we’re analyzing are all related to rare diseases and were sourced from the National Organization for Rare Diseases (NORD).

### The data includes:
- **article_title**: The title of the Wikipedia article.
- **timestamp**: The date (in YYYYMM format) representing the month and year of the pageviews.
- **views**: Total pageviews for that month.

---


# Wikipedia Article Traffic Analysis: Rare Diseases

## Project Goal
The main goal of this project is to gather, analyze, and share monthly traffic data from a selected set of Wikipedia articles related to rare diseases. The data covers the period from July 1, 2015, through September 30, 2024, and comes from the Wikimedia Pageviews API. This project is part of the coursework for DATA-512, focusing on professionalism and reproducibility in data analysis.

## Data Sources and Licensing
The data was obtained from the Wikimedia Foundation's public Pageviews API. This data is available under the [Wikimedia Foundation Terms of Use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use) and follows the Creative Commons Attribution-ShareAlike 4.0 License ([CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)). This means the data can be reused and shared, as long as appropriate credit is provided, and any derivative work is shared under the same license.

## API Documentation
The project uses the following API to access the page traffic data:
- [Wikimedia Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html): This API provides access to monthly traffic data for desktop, mobile web, and mobile app views from July 2015 onward.

## Repository Structure

```bash
data-512-project/
├── data/
│   ├── Copy of rare-disease_cleaned_AUG_2024.csv
│   ├── rare-disease_monthly_cumulative_201507-202409.json
│   ├── rare-disease_monthly_desktop_201507-202409.json
│   └── rare-disease_monthly_mobile_201507-202409.json
├── images/
│   ├── fewest_months_data.png
│   ├── max_min_average_views.png
│   └── top_10_peak_views.png
├── notebooks/
│   ├── data_acquisition.ipynb
│   └── data_analysis.ipynb
├── LICENSE
└── README.md
```



### Folders and Files
- **data/**: Contains datasets used in the project.
    - `Copy of rare-disease_cleaned_AUG_2024.csv`: Cleaned CSV file with metadata and monthly traffic data for Wikipedia articles on rare diseases.
    - `rare-disease_monthly_cumulative_201507-202409.json`: JSON file containing cumulative monthly traffic data (both desktop and mobile views).
    - `rare-disease_monthly_desktop_201507-202409.json`: JSON file containing monthly desktop traffic data.
    - `rare-disease_monthly_mobile_201507-202409.json`: JSON file containing monthly mobile traffic data.
  
- **images/**: Includes the output graphs generated from the analysis.
    - `fewest_months_data.png`: Visualization of articles with the fewest months of data.
    - `max_min_average_views.png`: Time series graph showing max and min average page views.
    - `top_10_peak_views.png`: Graph displaying the top 10 articles with peak page views over time.
  
- **src/**: Contains the Jupyter notebooks used to collect and analyze the data.
    - `data_acquisition.ipynb`: Notebook used to collect the data from the Wikimedia API.
    - `data_analysis.ipynb`: Notebook used for processing, analyzing, and visualizing the data.

## Data Files

### Input Data
1. **rare-disease_cleaned_AUG_2024.csv**: Metadata and monthly traffic for selected rare disease Wikipedia articles.

### Output Visualizations
1. **rare-disease_monthly_cumulative_201507-202409.json**: Cumulative (desktop + mobile) pageviews over the time period.
2. **rare-disease_monthly_desktop_201507-202409.json**: Desktop-specific pageviews.
3. **rare-disease_monthly_mobile_201507-202409.json**: Mobile-specific pageviews.

4. **Fewest_Months_of_Data_Desktop_and_Mobile.png**: Visualization highlighting articles with the least amount of data over time.
5. **Max_Min_Average_Views.png**: Visualization of articles with the highest and lowest average views for both mobile and desktop.
6. **Top_10_Peak_Page_Views_Desktop_and_Mobile.png**: Shows the top 10 articles with the highest peaks in page views.

## Data Schema

For the JSON files:
- `article_title`: The title of the Wikipedia article.
- `timestamp`: The date of the data (monthly).
- `views`: The number of views for the article in that month.


# Attributions & Provenance

- **Source Data License**: All the data comes from Wikimedia and is covered under their [Terms of Use](https://foundation.wikimedia.org/wiki/Terms_of_Use). The data is public and fully in line with their guidelines.
- **Code License**: The code for this project is licensed under the MIT License. You can find more details in the `LICENSE` file.
- **Code Attribution**: The structure of the API request code is based on work by Dr. David W. McDonald from the University of Washington and is used here with attribution under the Creative Commons CC-BY License.

---

## Resources & Documentation

### Wikimedia API Docs

- [Wikimedia Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html): This is the main documentation for the API we used to fetch the pageview data.
- [Wikimedia Analytics Code of Conduct](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews): Wikimedia’s rules for using their data.

### Additional Libraries

- [Python Requests](https://requests.readthedocs.io/en/master/): Used to fetch data from the Wikimedia API.
- [Pandas](https://pandas.pydata.org/pandas-docs/stable/): For manipulating the data.
- [Matplotlib](https://matplotlib.org/stable/contents.html): For plotting the graphs.

---


## Known Issues and Considerations
- **Missing Data**: Some articles have missing data for certain months, which may affect trend analysis.
- **Article Changes**: Wikipedia articles can be merged or renamed, which might lead to some inconsistencies in the page view data.
- **Outliers**: Sudden spikes in page views could result from external events such as media coverage, which can skew long-term trend analysis.

## Code Files
1. **data_acquisition.ipynb**: Contains the code that calls the Wikimedia API to retrieve pageview data.
2. **data_analysis.ipynb**: Contains the code for analyzing the data and generating the graphs.

## License and Documentation
- **[MIT License](https://opensource.org/licenses/MIT)**: The project code is licensed under the MIT License, allowing for open use and modification.
- **[Wikimedia Terms of Use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use)**: The Wikimedia data used in this project is subject to their terms of use.

## References and Resources
- [Wikimedia Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html)
- [The Practice of Reproducible Research](http://www.practicereproducibleresearch.org/core-chapters/2-assessment.html)
- [National Organization for Rare Diseases (NORD)](https://rarediseases.org)



That’s everything you need to know to reproduce the analysis! If you run into any issues, feel free to check the documentation links or leave a comment in the repo.
