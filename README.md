# Password-Manager

The Password Manager is a web application built with Flask, a Python web framework, that allows users to store and search for passwords based on the application name. The passwords are stored in a SQLite database.

## Prerequisites

Before running the application, make sure you have the following requirements:

* Python 3.x installed
* Flask and its dependencies installed
* SQLite database

## Installation

1. Clone the repository or download the code files to your local machine.
2. In the project directory, create a virtual environment to isolate the dependencies of the application. You can use venv module to create a virtual environment.
```
python -m venv myenv
```
3. Activate the virtual environment.
   * On Windows:
```
myenv\Scripts\activate
```
   * On macOS and Linux:
```
source myenv/bin/activate
```
4. Install the required dependencies by running the following command:
```
pip install -r requirements.txt
```

## Configuration
The Flask application requires a configuration for the database connection. Open the app.py file and locate the following line:
```
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///passwords.db'
```
Ensure that the path provided in SQLALCHEMY_DATABASE_URI matches the location where you want to store the SQLite database file. By default, it is set to passwords.db in the current directory.

## Running the Application
To run the Flask application, follow these steps:

1. Make sure you are in the project directory and your virtual environment is activated.
2. Initialize the database by running the following command:
```
flask db init
```
This will create the necessary migration directory.
3. Apply the initial migration to create the required database tables:
```
flask db migrate
flask db upgrade
```
4. Start the Flask development server by running the following command:
```
flask run
```
The server should start running locally on http://localhost:5000/.
5. Open a web browser and visit http://localhost:5000/ to access the Password Manager.

## Usage
The Password Manager provides the following functionality:

Password Entry Form
* To save a new password, fill in the "App Name," "Username," and "Password" fields in the Password Entry form and click the "Save Password" button. The password will be stored in the database.
Search by App Name
* To search for passwords by the application name, enter the app name in the Search form and click the "Search" button. The table will display the matched passwords.
Password Display
* The table displays the stored passwords. It shows the "App Name," "Username," and "Password" columns. The passwords are dynamically added to the table when searching or saving new passwords.
Footer
* The footer section displays the "Password Manager" text and copyright information.

## API Endpoints
The Flask app provides the following API endpoints:

* **POST /passwords**: Stores a new password in the database. Requires the "appname," "username," and "password" fields in the request form data.

* **GET /passwords/search**: Searches for passwords by the application name. Requires the "appname" query parameter to specify the search query.

* **POST /authenticate**: Authenticates a password by the application name. Requires the "appname" and "password" fields in the request form data.


## Customization
You can customize the appearance of the application by modifying the **home.html** file. The HTML structure, CSS styles, and JavaScript code are defined in this file. Feel free to adjust the styles, layout, or add additional features as per your requirements.

## Deployment
To deploy the Flask app to a hosting platform like Heroku, you can follow the steps mentioned in the previous answer.

Make sure to configure the necessary environment variables, such as the database URL or other sensitive information, based on the hosting platform's requirements.

Remember to update the **requirements.txt** file if you add or remove any dependencies from your application.

## Conclusion
The Password Manager is a Flask web application that provides a simple interface for storing and searching passwords. It demonstrates the basic usage of Flask, SQLAlchemy for database management, and jQuery for making AJAX requests to the backend.

Feel free to explore and enhance the application according to your needs.


output samples
<img width="921" alt="1" src="https://github.com/AlisettyAkshitha/password-manager/assets/120576624/4c7a6c78-46cc-4ff2-8be9-fdcca2b00d13">
<img width="943" alt="Screenshot 2023-05-31 112750" src="https://github.com/AlisettyAkshitha/password-manager/assets/120576624/cb5e6166-14c7-4752-8c84-2c8fb8519bac">
<img width="960" alt="Screenshot 2023-05-31 113053" src="https://github.com/AlisettyAkshitha/password-manager/assets/120576624/9e7ec41c-ebf5-428b-b067-d12fabebf002">

