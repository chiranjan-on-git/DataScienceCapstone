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
- [Project Files](#project-files)
- [Author](#author)
- [License](#license)

## Motivation

SpaceX has revolutionized the space industry with its focus on reusable rocket technology, significantly driving down launch costs (e.g., Falcon 9 at $62 million, well below market average). Understanding the patterns and factors behind their successes and failures is crucial for new entrants or competitors. This project provides a data-driven analysis to inform strategic decisions, potentially enabling entities like 'Space Y' to offer competitive bids for rocket launches based on a deep understanding of market dynamics and technical performance.

## Data Sources

The dataset for this project was compiled from two primary sources to ensure both structured reliability and historical context:

1.  **SpaceX REST API (v4):** Provided structured and up-to-date information on SpaceX missions, including launch details, payloads, and outcomes.
2.  **Wikipedia (Web Scraping):** Complementary historical and contextual data for Falcon 9 launches was extracted from related Wikipedia pages, parsed from HTML tables into a Pandas DataFrame.

## Methodology

My approach involved several key data science stages, from raw data collection to predictive modeling. Each stage is documented in dedicated Jupyter notebooks or Python scripts.

### Data Collection

*   **Objective:** Gather comprehensive launch data from SpaceX API and historical data from Wikipedia.
*   **Process:**
    *   I utilized the `requests` library to interact with the SpaceX REST API.
    *   I performed web scraping using libraries like `BeautifulSoup` to extract and parse HTML tables from Wikipedia.
*   **Relevant Files:**
    *   [`jupyter-labs-spacex-data-collection-api.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-spacex-data-collection-api.ipynb)
    *   [`jupyter-labs-webscraping.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-webscraping.ipynb)

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
*   **Relevant File:**
    *   [`labs-jupyter-spacex-Data wrangling.ipynb`](https://github.com/your-username/your-repo-name/blob/main/labs-jupyter-spacex-Data%20wrangling.ipynb)

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
*   **Relevant Files:**
    *   [`jupyter-labs-eda-dataviz-v2.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-eda-dataviz-v2.ipynb)
    *   [`jupyter-labs-eda-sql-coursera_sqllite.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-eda-sql-coursera_sqllite.ipynb)

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
*   **Relevant Files:**
    *   [`lab_jupyter_launch_site_location.ipynb`](https://github.com/your-username/your-repo-name/blob/main/lab_jupyter_launch_site_location.ipynb) (For Folium Map)
    *   [`Code_SN Labs_Dash.txt`](https://github.com/your-username/your-repo-name/blob/main/Code_SN%20Labs_Dash.txt) (Contains Python code for the Plotly Dash dashboard app)

### Predictive Analysis (Classification)

*   **Objective:** Build, tune, and evaluate machine learning models to predict the successful landing of the first stage of Falcon rockets.
*   **Process:**
    1.  **Data Preprocessing:** Preparing features for model input.
    2.  **Data Splitting:** Dividing data into training and testing sets.
    3.  **Model Training and Evaluation:**
        *   Models evaluated: Logistic Regression, Decision Tree, and k-Nearest Neighbors (kNN). *(Note: Support Vector Machine (SVM) was a planned evaluation, but its results are not explicitly shown in the provided execution trace for the notebook.)*
        *   Optimal parameters chosen using `GridSearchCV`.
        *   Performance evaluated using accuracy and confusion matrices.
    4.  **Model Improvement:** Iterative refinement of models.
    5.  **Selection of the most accurate model:** Identifying the best performing model.
*   **Relevant File:**
    *   [`SpaceX_Machine Learning Prediction_Part_5.ipynb`](https://github.com/your-username/your-repo-name/blob/main/SpaceX_Machine%20Learning%20Prediction_Part_5.ipynb)

## Key Findings & Results

### EDA Insights

*   **Launch Site Performance:** KSC LC-39A recorded the highest success rate at 76.9% and contributed to 41.9% of all successful launches, establishing itself as a prime location. From Flight #70 onwards, VAFB SLC 4E was phased out, replaced by CCAFS SLC 40 and KSC LC 39A. CCAFS SLC 40 showed a lower success rate compared to the other sites.
*   **Payload Impact:** Payloads weighing between 2,000 kg and 5,000 kg demonstrated the highest success rates, indicating an optimal range for current booster capabilities. VAFB SLC 4E is ideal for payloads under 10,000 kg, while other sites handle heavier payloads with higher success rates.
*   **Booster Performance:** Boosters FT, B4, and B5 exhibited the best performance within the successful payload range, highlighting their reliability. The F9 v1.1 booster version had the lowest success rate.
*   **Orbit Type Success:** Orbits ES L1, GEO, HEO, and SSO showed 100% success. SO orbits had 0% success. Other orbits like GTO and VLEO had success rates ranging from 50% to 80%. Around Flight #64, VLEO became a primary focus for launches. For VLEO, payloads often exceeded 13,000 kg, while most other orbits had payloads under 8,000 kg.
*   **Launch Success Yearly Trend:** A rising success rate was observed from 2013 to 2020, with a notable 25% drop in 2018, the highest rate achieved in 2019, and a slight dip in 2020.

### Machine Learning Model Performance

*   **Overall Accuracy:** The classification models (Logistic Regression, Decision Tree, kNN) collectively demonstrated an overall accuracy of **83%** on the test set.
*   **Individual Model Accuracy:** For the specific test data split and hyperparameter tuning presented:
    *   Logistic Regression: **0.83333**
    *   Decision Tree: **0.83333**
    *   kNN: **0.83333**
    *(Note: The `Decision Tree` section's overall best score in `GridSearchCV` was 0.8767857, but its score on the final `X_test` subset, like other models, was 0.83333. This consistent accuracy across models implies that for this particular test subset, they made identical predictions in terms of success/failure counts.)*
*   **Failure Prediction:** All models correctly predicted 100% of the failures (true negatives in the confusion matrix).
*   **False Positives:** Some false positives (incorrectly predicting success) were observed across predictions.

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
    This will open Jupyter in your browser. All `.ipynb` files are located in the root directory and can be opened directly. It is recommended to run them in the order they appear in the `Methodology` section.

4.  **Run Plotly Dash App (Optional):**
    To run the interactive dashboard locally, execute the Python script:
    ```bash
    python "Code_SN Labs_Dash.txt"
    ```
    The app should then be accessible in your web browser, typically at `http://127.0.0.1:8050/`.

## Technologies Used

*   Python 3.x
*   Jupyter Notebook
*   Pandas (for data manipulation)
*   NumPy (for numerical operations)
*   Requests (for API calls)
*   BeautifulSoup4 (for web scraping)
*   Scikit-learn (for machine learning models: Logistic Regression, Decision Tree, KNeighborsClassifier)
*   Plotly (for interactive visualizations and Dashboards)
*   Dash (for building the web dashboard)
*   Folium (for interactive mapping)
*   SQL (SQLite, for data querying and analysis)
*   Matplotlib & Seaborn (for static visualizations)

## Project Files

This repository contains the following main files in the root directory:

*   [`Code_SN Labs_Dash.txt`](https://github.com/your-username/your-repo-name/blob/main/Code_SN%20Labs_Dash.txt): Python script for the interactive Plotly Dash web application.
*   [`README.md`](https://github.com/your-username/your-repo-name/blob/main/README.md): This project overview document.
*   [`SpaceX_Machine Learning Prediction_Part_5.ipynb`](https://github.com/your-username/your-repo-name/blob/main/SpaceX_Machine%20Learning%20Prediction_Part_5.ipynb): Jupyter notebook detailing the predictive analysis, including data preprocessing, model training (Logistic Regression, Decision Tree, kNN), and evaluation.
*   [`jupyter-labs-eda-dataviz-v2.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-eda-dataviz-v2.ipynb): Jupyter notebook for Exploratory Data Analysis using various data visualizations.
*   [`jupyter-labs-eda-sql-coursera_sqllite.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-eda-sql-coursera_sqllite.ipynb): Jupyter notebook for Exploratory Data Analysis using SQL queries.
*   [`jupyter-labs-spacex-data-collection-api.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-spacex-data-collection-api.ipynb): Jupyter notebook for collecting SpaceX launch data from the SpaceX REST API.
*   [`jupyter-labs-webscraping.ipynb`](https://github.com/your-username/your-repo-name/blob/main/jupyter-labs-webscraping.ipynb): Jupyter notebook for web scraping Falcon 9 launch records from Wikipedia.
*   [`lab_jupyter_launch_site_location.ipynb`](https://github.com/your-username/your-repo-name/blob/main/lab_jupyter_launch_site_location.ipynb): Jupyter notebook for building an interactive map of SpaceX launch sites using Folium.
*   [`labs-jupyter-spacex-Data wrangling.ipynb`](https://github.com/your-username/your-repo-name/blob/main/labs-jupyter-spacex-Data%20wrangling.ipynb): Jupyter notebook for data wrangling, cleaning, and feature engineering.
*   `requirements.txt`: Lists all Python dependencies required to run the project.
*   `LICENSE`: The license file for this project.
*   `images/` (optional): A directory for any images used in the README.

## Author

**Chiranjan Yathish**  
*IBM Developer Skills Network*  
*Project Date: 15/01/2025*

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/your-username/your-repo-name/blob/main/LICENSE) file for details.

---

**Final Checklist before uploading to GitHub:**

1.  **Create a `requirements.txt` file:** In your project's root directory, with your virtual environment activated, run `pip freeze > requirements.txt`. This will list all the necessary Python packages.
2.  **Create an `images/` directory (optional):** If you want the cover image (or any other screenshots), create a folder named `images` in your root directory and place your `cover_image.png` (or other image files) there. Adjust the path in the README if you use a different image name or no image.
3.  **Create a `LICENSE` file:** Copy the MIT license text into a file named `LICENSE` in the root of your repository.
4.  **Replace `your-username` and `your-repo-name`:** Go through the README and replace these placeholders in all GitHub URLs with your actual GitHub username and repository name.
