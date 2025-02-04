# Racing Report Application

This application is a Flask-based web application designed to provide reports and driver information for racing events.
It includes API endpoints for data retrieval, web routes for browser display, and a CLI tool. Package will show
information about certain racer.

## Features

#### API Endpoints:

* /api/v1/report/: Endpoint to fetch report data in JSON or XML format.
* /api/v1/drivers/: Endpoint to fetch driver data in JSON or XML format.

#### Web Routes:

* /: Redirects to the report homepage.
* /report: Displays the homepage with the racing report.
* /report/drivers: Displays driver information.

#### CLI Tool:

* Loads data from files.

## Prerequisites

Ensure you have the following installed:

* Python 3.x
* Flask
* Flask-RESTful
* Flasgger

## Installation

1. Clone the repository:

```bash
git clone <repository_url>
cd <repository_directory>
```

2. Create a virtual environment and activate it:

```bash
git clone <repository_url>
cd <repository_directory>
```

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Set up the database:
   Configure your database connection settings in main_report_Alex_Drob/models.py and initialize the database.

## Usage

#### Running the Application

1. Run the web application:

```bash
python app.py
```

2. Access the application:
   Open your browser and go to http://localhost:5000

## Using the CLI Tool

#### Run the CLI tool to load data:

```bash
python main.py load-data <file_path>
```

## API Documentation

The API documentation is automatically generated by Flasgger. You can access it by navigating
to http://localhost:5000/apidocs/

## Application Structure

* app.py: The main application file for serving web pages.
* api.py: Contains the API resource definitions for returning data in JSON or XML format.
* main.py: CLI tool for loading data.
* main_report_Alex_Drob/api.py: Contains the API resource definitions.
* main_report_Alex_Drob/models.py: Contains the database models.
* templates/: Directory containing HTML templates.
* homepage.html: Template for the homepage.
* driver_info.html: Template for displaying driver information.
* drivers.html: Template for displaying the list of drivers.

## Routes and Endpoints

#### Web Routes

#### /:

* Redirects to /report.

#### /report:

* Displays the homepage with the racing report.
* Accepts an optional order query parameter (asc or desc) to sort the reports.

#### /report/drivers:

* Displays driver information.
* Accepts an optional driver_id query parameter to filter by driver ID.

#### API Endpoints

#### /api/v1/report/:

* Fetch report data.
* Supports order query parameter (asc or desc).
* Supports format query parameter (json or xml).

#### /api/v1/drivers/:

* Fetch driver data.
* Supports order query parameter (asc or desc).
* Supports format query parameter (json or xml).

## Example Requests

#### Fetching Reports

```bash
curl -X GET "http://localhost:5000/api/v1/report/?order=asc&format=json"
```

```bash
curl -X GET "http://localhost:5000/api/v1/report/?order=desc&format=xml"
```

#### Fetching Drivers

```bash
curl -X GET "http://localhost:5000/api/v1/drivers/?format=json"
```

```bash
curl -X GET "http://localhost:5000/api/v1/drivers/?format=xml"
```

## Error Handling

* The application handles 404 errors if a driver is not found with the provided driver_id.

## Contributing

1. Fork the repository.
2. Create a new branch: git checkout -b feature-branch-name.
3. Make your changes and commit them: git commit -m 'Add some feature'.
4. Push to the branch: git push origin feature-branch-name.
5. Submit a pull request.