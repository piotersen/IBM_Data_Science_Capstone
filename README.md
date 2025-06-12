## 📜 About The Project

This project is a real-time data pipeline and visualization dashboard that simulates the monitoring of global earthquake events. The system is built on a distributed messaging architecture using Apache Kafka and provides a dynamic, auto-refreshing web-based dashboard for visualizing the most recent seismic alerts.

The core components of the system are:

* **Data Producer (`producer.py`)**: This script reads historical earthquake data from a CSV file (`database.csv`). It then simulates live events by randomly selecting an earthquake from this dataset and publishing its details (latitude, longitude, depth, magnitude) to a Kafka topic named `earthquakes` at regular intervals.

* **Data Consumer (`consumer.py`)**: This service listens to the `earthquakes` topic. When it receives an event, it uses a machine learning model (`severity_model.pkl`) to classify the earthquake's severity as either 'Moderate' or 'Severe'. The model is a `RandomForestClassifier` trained on magnitude and depth. If the model is not available, it falls back to a simple rule based on a magnitude threshold. The processed event, now enriched with a timestamp and a severity label, is appended to a log file (`alerts_log.csv`).

* **Machine Learning Model (`train_model.py`)**: A simple script to train the severity classification model using the historical data in `database.csv`. It saves the trained classifier and the feature names into a pickle file (`severity_model.pkl`) for the consumer to use.

* **Real-Time Dashboard (`dashboard.py`)**: A web application built with Streamlit that provides a user-friendly interface for monitoring the latest earthquake alerts. The dashboard reads the `alerts_log.csv` file, displays data from the last 10 minutes, and automatically refreshes every 60 seconds.

This project demonstrates a full-cycle data engineering workflow, including data generation, real-time processing with a message queue, ML-based data enrichment, and live visualization.

### ✨ Key Features

* **Real-Time Data Flow**: Built around Apache Kafka for low-latency message passing between components.
* **ML-Powered Enrichment**: A scikit-learn model classifies earthquake severity in real-time.
* **Interactive Visualization**: A dynamic Streamlit dashboard with auto-refresh, live statistics, and an interactive map of epicenters using Pydeck.
* **Decoupled Architecture**: Each component (producer, consumer, dashboard) runs independently, making the system scalable and robust.

### 🤖 Tech Stack

* **Data Streaming**: Apache Kafka
* **Backend & Data Processing**: Python
* **Dashboard**: Streamlit
* **Data Manipulation**: Pandas
* **Machine Learning**: Scikit-learn
* **Geospatial Visualization**: Pydeck
