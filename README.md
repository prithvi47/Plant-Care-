Plant Care


--Project Overview

Plant care is a powerful deep learning web application built to help farmers and enthusiasts quickly identify and manage common plant leaf diseases. By leveraging a Convolutional Neural Network (CNN), the application can classify a leaf image into one of 38 different classes (diseases or healthy states) across 14 major crop species.
The web interface, powered by Flask, provides an intuitive platform to upload an image and instantly receive a diagnosis, along with actionable remedies and suggested products to treat the affliction.


✨ Key Features

* ⚡ Real-time Prediction: Uses a trained PyTorch CNN model for near-instant disease classification upon image upload.
* 📚 Comprehensive Database: Provides detailed disease descriptions and "Possible Steps" (prevention/treatment guidelines) sourced from disease_info.csv.
* 🛒 Integrated Marketplace: Suggests relevant supplements/fungicides with direct purchase links, powered by supplement_info.csv to bridge diagnosis and solution.
* 🌐 Deploy-Ready: Optimized for deployment on platforms like Heroku using a standard Procfile and requirements.txt.


💻 Tech Stack & Architecture

The application's logic is split between a Python backend and a PyTorch deep learning component.
* Backend Framework: Flask (app.py) for routing, serving HTML, handling image uploads, and managing data display.
* Deep Learning: PyTorch (torch, torchvision) for model definition (CNN.py) and inference.
* Data Sources: Pandas is used to ingest and query two critical datasets:
    * disease_info.csv: Stores disease names, descriptions, and treatment steps.
    * supplement_info.csv: Maps diseases to recommended supplements/products.
* Deployment: Gunicorn (Procfile) for production-grade WSGI server execution.


⚙️ Setup and Installation Guide

To run this project locally, follow these steps:

1. Prerequisites

You must have Python 3.x and pip installed on your system.

2. Clone the Repository

git clone

3. Install Dependencies

Install all required Python packages using the provided requirements.txt file.
Bash

pip install -r requirements.txt

4. Model Requirement

The core functionality depends on the trained model weights. You must download and place your trained PyTorch model file in the root directory:

5. Run the Application

Execute the main Python script to start the Flask development server:

python app.py
The application will launch and be accessible at: http://127.0.0.1:5000/

📁 File Structure

File	Description
app.py	Main Flask application and prediction pipeline logic.
CNN.py	Defines the PyTorch CNN model architecture (a Sequential model with 3 conv blocks).
disease_info.csv	Core data: Disease names, descriptions, and remedial steps.
supplement_info.csv	Market data: Recommended products, images, and buy links for each disease.
requirements.txt	List of all necessary Python dependencies (Flask, PyTorch, Pandas, etc.).
Procfile	Configuration for web server deployment (e.g., web: gunicorn app:app).
static/	Static assets: CSS, JavaScript, and user-uploaded images.
templates/	HTML files (e.g., home.html, index.html, submit.html).
plant_disease_model_1_latest.pt	The trained PyTorch model weights.
