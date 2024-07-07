Q1. What is Flask Framework? What are the advantages of Flask Framework?
Flask is a lightweight and flexible web framework written in Python. It is classified as a microframework because it does not require particular tools or libraries. It has no database abstraction layer, form validation, or other components where pre-existing third-party libraries provide common functions.

Advantages of Flask Framework:

Lightweight: Flask is minimalistic and lightweight, providing only the essential tools to build a web application.
Flexible: It gives developers the freedom to structure their application as they see fit, without imposing a specific way of doing things.
Extensible: Flask is highly extensible, allowing developers to integrate any number of third-party libraries and plugins as needed.
Easy to Learn: The framework is easy to set up and understand, making it a great choice for beginners and those looking to quickly prototype applications.
Documentation: Flask has excellent documentation and a large community, providing ample resources for troubleshooting and learning.
Integration: Easy to integrate with various tools and libraries, including SQLAlchemy for ORM, Jinja2 for templating, and others.
Q2. Create a simple Flask application to display ‘Hello World!!’. Attach the screenshot of the output in Jupyter Notebook.
Here's a simple Flask application:

python
Copy code
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello World!!'

if __name__ == '__main__':
    app.run()
To run this in a Jupyter Notebook, you would need to use a different approach as Flask's development server needs to run in a separate process. However, here's how you can set it up:

Save the above code in a file named app.py.
Run the file using a terminal or command prompt:
bash
Copy code
python app.py
Open your web browser and navigate to http://127.0.0.1:5000/ to see the output.
Q3. What is App routing in Flask? Why do we use app routes?
App routing in Flask is the mechanism to map URLs to specific functions that handle the logic for those URLs. It is achieved using the @app.route decorator.

Why use app routes:

URL Mapping: To create clean, readable, and SEO-friendly URLs for different pages of a web application.
Function Binding: To associate a URL with a specific function that will execute when that URL is accessed.
Organization: To organize the different endpoints of an application in a clear and manageable way.
Q4. Create a “/welcome” route to display the welcome message “Welcome to ABC Corporation” and a “/” route to show the following details:
python
Copy code
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return '''
    Company Name: ABC Corporation<br>
    Location: India<br>
    Contact Detail: 999-999-9999
    '''

@app.route('/welcome')
def welcome():
    return 'Welcome to ABC Corporation'

if __name__ == '__main__':
    app.run()
To display this in Jupyter Notebook, follow the same steps as in Q2:

Save the code in a file named app.py.
Run the file using a terminal or command prompt:
bash
Copy code
python app.py
Open your web browser and navigate to http://127.0.0.1:5000/ for the home route and http://127.0.0.1:5000/welcome for the welcome route.
Q5. What function is used in Flask for URL Building? Write a Python code to demonstrate the working of the url_for() function.
url_for() is a function in Flask that is used for URL building. It generates a URL to the given endpoint with the method's name and any arguments passed.

python
Copy code
from flask import Flask, url_for

app = Flask(__name__)

@app.route('/')
def home():
    return 'Home Page'

@app.route('/about')
def about():
    return 'About Page'

@app.route('/user/<username>')
def user_profile(username):
    return f'User: {username}'

@app.route('/generate_url')
def generate_url():
    home_url = url_for('home')
    about_url = url_for('about')
    user_url = url_for('user_profile', username='john_doe')
    return f'Home URL: {home_url}<br>About URL: {about_url}<br>User URL: {user_url}'

if __name__ == '__main__':
    app.run()
To see this in action:

Save the code in a file named app.py.
Run the file using a terminal or command prompt:
bash
Copy code
python app.py
