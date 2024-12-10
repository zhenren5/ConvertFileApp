# File Format Converter Web Application

This web application allows users to easily convert files between different formats: **CSV**, **JSON**, and **XLSX**. It provides a simple interface to upload a file, select the desired output format, and download the converted file.



## Features

-   Convert CSV files to JSON or XLSX
-   Convert JSON files to CSV or XLSX
-   Convert XLSX files to CSV or JSON
-   Support for file upload and download via a user-friendly web interface


## Installation

To set up the project locally, follow these steps:

### 1. Clone the repository

`git clone https://github.com/zhenren5/ConvertFileApp.git` 

### 2. Set up a virtual environment (optional but recommended)

It's good practice to create a virtual environment for Python projects to isolate dependencies. You can create a virtual environment using the following commands:

`python3 -m venv venv
source venv/bin/activate   # On Windows use: venv\Scripts\activate` 

### 3. Install dependencies

To install the necessary Python libraries, run the following command:

`pip install -r requirements.txt` 

This will install all the required dependencies listed in the `requirements.txt` file.

## Usage

### 1. Start the Flask Development Server

Once the dependencies are installed, you can start the Flask web application:

`cd app`
`flask run` 

This will start the server, and you should be able to access the application in your browser at `http://127.0.0.1:5000`.

### 2. Convert Files

-   Go to the web interface in your browser.
-   Upload a file in CSV, JSON, or XLSX format.
-   Choose the format you want to convert it to (e.g., CSV to JSON, XLSX to CSV).
-   Download the converted file once the conversion is complete.