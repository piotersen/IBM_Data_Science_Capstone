## 📜 About The Project

This project is the capstone for the IBM Data Science Professional Certificate. It analyzes a decade of SpaceX Falcon 9 launch data to identify the key factors determining the success of first-stage rocket landings and builds a machine learning model to predict these outcomes.

SpaceX has revolutionized the aerospace industry by making space launches more affordable, largely due to its ability to reuse the first stage of the Falcon 9 rocket. The success of landing this first stage is critical for determining the final cost of a launch. This project aims to answer a key question: **What factors contribute to a successful first-stage landing?**

To achieve this, we executed a comprehensive data science workflow, which included:
1.  **Data Collection**: Gathering historical launch data from the SpaceX API and performing web scraping on Wikipedia to enrich the dataset.
2.  **Data Wrangling & EDA**: Cleaning and preparing the data for analysis. We used SQL for initial exploration and Python libraries (Pandas, Matplotlib, Seaborn) for in-depth exploratory data analysis to uncover initial trends.
3.  **Interactive Visualization**: Creating interactive maps with Folium to visualize launch sites and landing outcomes geographically.
4.  **Machine Learning Prediction**: Building and evaluating several classification models to predict whether the first stage will land successfully. Our analysis revealed that the **Decision Tree Classifier** was the most effective model for this task.

Our key findings indicate that launch success is strongly correlated with the launch site's operational experience, the specific orbital trajectory (e.g., GEO, SSO), and continuous technological improvements over the years. The KSC LC-39A launch site was identified as having the highest success rate.

This project showcases a full data science pipeline, from data acquisition and cleaning to advanced analytics and predictive modeling.

### ✨ Key Features

* **Multi-Source Data Collection**: Combines data from a REST API and web scraping.
* **In-Depth Exploratory Data Analysis (EDA)**: Utilizes SQL and data visualization to identify trends and relationships.
* **Interactive Geospatial Analysis**: Uses Folium to create interactive maps of launch sites and success rates.
* **Predictive Modeling**: Compares multiple machine learning algorithms to find the best predictor for landing success.
* **Comprehensive Reporting**: The project culminates in a detailed presentation summarizing the methodology, results, and conclusions.

### 🤖 Tech Stack

* **Data Collection**: Python (`requests`, `BeautifulSoup`)
* **Data Analysis**: Python (`pandas`, `numpy`), SQL
* **Data Visualization**: `matplotlib`, `seaborn`, `folium`
* **Machine Learning**: `scikit-learn`
* **Reporting**: Jupyter Notebook, PowerPoint/PDF
