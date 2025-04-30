Exp 1 : Streamlit Dashboard

Welcome to the Streamlit Dashboard experiment!
This repository showcases a simple interactive web application built with Streamlit, allowing users to explore, upload, and visualize data — all deployed inside a Docker container.

Project Overview:

This project demonstrates:
Interactive sidebar navigation between multiple pages.
Uploading and previewing CSV datasets.
Basic data summary and shape exploration.
Static and dynamic visualizations using Matplotlib and Streamlit's built-in chart components.
Dockerized deployment for easy reproducibility.

Repository Structure:

![image](https://github.com/user-attachments/assets/11b31653-031c-49ab-8520-df0af8b5102b)

Running the App with Docker:

Make sure you have Docker installed on your system.

Clone the Repository:

git clone https://github.com/<your-username>/streamlit-dashboard.git
cd streamlit-dashboard

Build the Docker Image:

docker build -t streamlit-dashboard .

Run the Docker Container:

docker run -p 8501:8501 streamlit-dashboard

Access the Application:

Open your web browser and go to:
https://app-dashboard-7rbrj9pfmvfxmxjnqemgmt.streamlit.app

ScreenShot:
![image](https://github.com/user-attachments/assets/625bc402-9d9b-4f25-bc03-c1bde16de292)

Features:

🏠 Home Page

Welcome screen with app overview.
Streamlit logo display.
Sidebar-based page navigation.

📂 Data Explorer

Upload CSV files.
Preview dataset (first few rows).
View dataset statistics (mean, median, standard deviation, etc.).
See dataset shape (rows and columns).

📊 Visualization

Static plot of a sine wave using Matplotlib.
Dynamic random data visualizations using Streamlit's line_chart.

Requirements:

This application requires the following Python packages:
streamlit
pandas
numpy
matplotlib
plotly

These will be installed automatically during Docker build via the requirements.txt.

Dockerfile Summary:

The Dockerfile:
Uses python:3.9-slim as the base image.
Installs dependencies from requirements.txt.
Copies the app files.
Exposes port 8501 (Streamlit's default).
Runs the main.py Streamlit app on container start.

License:
This project is made for educational and experimental purposes only.
Feel free to use and modify it as needed!




