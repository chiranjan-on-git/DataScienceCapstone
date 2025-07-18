# Winning the Space Race with Data Science

![SpaceX Falcon 9 Launch](https://github.com/your-username/your-repo-name/blob/main/images/cover_image.png?raw=true)
*(Note: Replace `images/cover_image.png` with a path to a suitable image in your repo, or remove if no image is preferred)*

## Project Overview

This project leverages advanced data science techniques to analyze historical SpaceX launch data, aiming to gain insights into launch success factors and predict future outcomes. My ultimate goal is to provide valuable intelligence for aspiring space industry players, such as the hypothetical 'Space Y,' to strategically bid against SpaceX for future rocket launches, capitalizing on SpaceX's pioneering work in reusable rocket technology.

I utilized data gathered from the SpaceX REST API and web scraping from Wikipedia to build, analyze, and model launch outcomes. Machine Learning models were then applied to predict the successful landing of the first stage of Falcon rockets.

## Table of Contents

- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
    - [Data Collection](#data-collection)
    - [Data Wrangling](#data-wrangling)
    - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
    - [Interactive Visual Analytics](#interactive-visual-analytics)
    - [Predictive Analysis (Classification)](#predictive-analysis-classification)
- [Key Findings & Results](#key-findings--results)
    - [EDA Insights](#eda-insights)
    - [Machine Learning Model Performance](#machine-learning-model-performance)
- [How to Use](#how-to-use)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Author](#author)
- [License](#license)

## Motivation

SpaceX has revolutionized the space industry with its focus on reusable rocket technology, significantly driving down launch costs (e.g., Falcon 9 at $62 million, well below market average). Understanding the patterns and factors behind their successes and failures is crucial for new entrants or competitors. This project provides a data-driven analysis to inform strategic decisions, potentially enabling entities like 'Space Y' to offer competitive bids for rocket launches based on a deep understanding of market dynamics and technical performance.

## Data Sources

The dataset for this project was compiled from two primary sources to ensure both structured reliability and historical context:

1.  **SpaceX REST API (v4):** Provided structured and up-to-date information on SpaceX missions, including launch details, payloads, and outcomes. Key endpoints utilized:
    *   `/v4/capsules`
    *   `/v4/cores`
    *   `/v4/launches/past`

2.  **Wikipedia (Web Scraping):** Complementary historical and contextual data for Falcon 9 launches was extracted from related Wikipedia pages, parsed from HTML tables into a Pandas DataFrame.

## Methodology

My approach involved several key data science stages, from raw data collection to predictive modeling. Each stage is documented in dedicated Jupyter notebooks.

### Data Collection

*   **Objective:** Gather comprehensive launch data from SpaceX API and historical data from Wikipedia.
*   **Process:**
    *   I utilized the `requests` library to interact with the SpaceX REST API.
    *   I performed web scraping using libraries like `BeautifulSoup` to extract and parse HTML tables from Wikipedia.
*   **Notebook:** [Data Collection Notebook]([YOUR_GITHUB_URL_FOR_DATA_COLLECTION_NOTEBOOK])
    *   *(Remember to replace `[YOUR_GITHUB_URL_FOR_DATA_COLLECTION_NOTEBOOK]` with the actual link to your notebook on GitHub)*

### Data Wrangling

*   **Objective:** Clean, preprocess, and transform the collected data, and create a target variable for supervised learning models.
*   **Process:**
    *   Data Preprocessing: Handling missing values, converting data types.
    *   Feature Engineering: Creating relevant features from raw data.
    *   Classification of Desired Outcomes: Defining a `Landing_Outcome` label (e.g., successful landing vs. unsuccessful/no attempt) for machine learning.
    *   I extracted insights on:
        *   Number of launches per site.
        *   Number and occurrence of each orbit type.
        *   Mission outcomes for various orbits.
*   **Notebook:** [Data Wrangling Notebook]([YOUR_GITHUB_URL_FOR_DATA_WRANGLING_NOTEBOOK])

### Exploratory Data Analysis (EDA)

*   **Objective:** Discover patterns, relationships, and anomalies in the data using visualization and SQL queries.
*   **Visualizations Performed:**
    *   Scatter Plots: FlightNumber vs. PayloadMass, FlightNumber vs. LaunchSite, PayloadMass vs. LaunchSite, FlightNumber vs. Orbit, PayloadMass vs. Orbit.
    *   Bar Chart: Success rate by Orbit type.
    *   Line Chart: Success rate over the years.
*   **SQL Queries Performed:**
    *   Displaying unique launch sites.
    *   Listing records for launch sites beginning with 'CCA'.
    *   Total payload mass by NASA (CRS) boosters.
    *   Average payload mass by booster version F9 v1.1.
    *   Date of the first successful ground pad landing.
    *   Successful drone ship landings with specific payload ranges (4000-6000 kg).
    *   Total number of successful and failure mission outcomes.
    *   Names of booster versions carrying maximum payload mass.
    *   2015 launch records with 'Failure (drone ship)' outcome.
    *   Ranking of landing outcomes within a specific date range (2010-06-04 to 2017-03-20).
*   **Notebooks:**
    *   [EDA with Data Visualization Notebook]([YOUR_GITHUB_URL_FOR_EDA_VIZ_NOTEBOOK])
    *   [EDA with SQL Notebook]([YOUR_GITHUB_URL_FOR_EDA_SQL_NOTEBOOK])

### Interactive Visual Analytics

*   **Objective:** Create interactive maps and dashboards for deeper, user-driven exploration of launch data.
*   **Folium Map:**
    *   Marking all launch sites on a map.
    *   Marking success/failed launches for each site with color-coded markers.
    *   Calculating distances between launch sites and their proximities (coast, cities, etc.).
*   **Plotly Dash Dashboard:**
    *   **Success Pie Chart:** Visualizes overall success/failure rates and per-site rates.
    *   **Payload Range Slider:** Allows filtering data by payload mass (0-10,000 kg in 1,000 kg steps) to analyze correlation with mission outcomes.
    *   **Payload vs. Success Rate Scatter Plot:** Shows the relationship between payload mass and launch outcome, color-coded by booster version.
*   **Notebooks:**
    *   [Interactive Map with Folium Notebook]([YOUR_GITHUB_URL_FOR_FOLIUM_NOTEBOOK])
    *   [Dashboard with Plotly Dash Notebook]([YOUR_GITHUB_URL_FOR_PLOTLY_DASH_NOTEBOOK])

### Predictive Analysis (Classification)

*   **Objective:** Build, tune, and evaluate machine learning models to predict the successful landing of the first stage of Falcon rockets.
*   **Process:**
    1.  **Data Preprocessing:** Preparing features for model input.
    2.  **Data Splitting:** Dividing data into training and testing sets.
    3.  **Model Training and Evaluation:**
        *   Models evaluated: Logistic Regression, Support Vector Machine (SVM), Decision Tree, k-Nearest Neighbors (kNN).
        *   Optimal parameters chosen using `GridSearchCV`.
        *   Performance evaluated using accuracy and confusion matrices.
    4.  **Model Improvement:** Iterative refinement of models.
    5.  **Selection of the most accurate model:** Identifying the best performing model.
*   **Notebook:** [Predictive Analysis Notebook]([YOUR_GITHUB_URL_FOR_PREDICTIVE_ANALYSIS_NOTEBOOK])

## Key Findings & Results

### EDA Insights

*   **Launch Site Performance:** KSC LC-39A recorded the highest success rate at 76.9% and contributed to 41.9% of all successful launches, establishing itself as a prime location. From Flight #70 onwards, VAFB SLC 4E was phased out, replaced by CCAFS SLC 40 and KSC LC 39A. CCAFS SLC 40 showed a lower success rate compared to the other sites.
*   **Payload Impact:** Payloads weighing between 2,000 kg and 5,000 kg demonstrated the highest success rates, indicating an optimal range for current booster capabilities. VAFB SLC 4E is ideal for payloads under 10,000 kg, while other sites handle heavier payloads with higher success rates.
*   **Booster Performance:** Boosters FT, B4, and B5 exhibited the best performance within the successful payload range, highlighting their reliability. The F9 v1.1 booster version had the lowest success rate.
*   **Orbit Type Success:** Orbits ES L1, GEO, HEO, and SSO showed 100% success. SO orbits had 0% success. Other orbits like GTO and VLEO had success rates ranging from 50% to 80%. Around Flight #64, VLEO became a primary focus for launches. For VLEO, payloads often exceeded 13,000 kg, while most other orbits had payloads under 8,000 kg.
*   **Launch Success Yearly Trend:** A rising success rate was observed from 2013 to 2020, with a notable 25% drop in 2018, the highest rate achieved in 2019, and a slight dip in 2020.

### Machine Learning Model Performance

*   **Overall Accuracy:** The four machine learning classification models (Logistic Regression, SVM, Decision Tree, kNN) achieved an overall accuracy of **83%** on the test set.
*   **Best Performing Model:** The **Decision Tree Model** demonstrated the highest individual accuracy at **89%**.
*   **Failure Prediction:** All models correctly predicted 100% of the failures (true negatives).
*   **False Positives:** While effective, some false positives (incorrectly predicting success) were observed across predictions.
    *   *Note on specific test set performance:* For a particular test data split, all four models (Logistic Regression, SVM, Decision Tree, kNN) achieved an identical accuracy of **0.833333**, resulting in the same confusion matrix pattern (3 true positives, 3 false positives, 0 true negatives, 12 false negatives - *based on the image provided, assuming 'landed' is positive and 'did not land' is negative*). This indicates consistent performance across these models for that specific test case.

## How to Use

To explore this project:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```
2.  **Install dependencies:** It's recommended to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    pip install -r requirements.txt
    ```
3.  **Run Jupyter Notebooks:**
    ```bash
    jupyter notebook
    ```
    This will open Jupyter in your browser. Navigate to the `notebooks/` directory and open the `.ipynb` files in sequential order (or as per your interest) to see the code, analysis, and visualizations.

## Technologies Used

*   Python 3.x
*   Jupyter Notebook
*   Pandas (for data manipulation)
*   NumPy (for numerical operations)
*   Requests (for API calls)
*   BeautifulSoup4 (for web scraping)
*   Scikit-learn (for machine learning models)
*   Plotly (for interactive visualizations and Dashboards)
*   Folium (for interactive mapping)
*   SQL (for data querying and analysis)

## Project Structure
