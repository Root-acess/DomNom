# DomNom
DomNom

DomNom is a Python package designed to facilitate routing and management for web applications. It provides a simple and efficient way to create and manage routes, handle requests, and serve content. This package is ideal for developers looking to build lightweight web servers or integrate routing into their applications.
Features

    Routing: Easily define and manage routes for different HTTP methods (GET, POST, etc.).
    Request Handling: Process incoming HTTP requests and generate appropriate responses.
    Server Management: Start and stop a simple HTTP server for local testing and development.

Installation

To install DomNom, you can use pip. Run the following command in your terminal:

bash

pip install DomNom

For development purposes, you can also install additional dependencies by using:

bash

pip install DomNom[dev]

Quick Start

Here is a quick guide to get you started with DomNom.
Basic Usage

    Create a Simple Web Server

    python

from DomNom.server import Server

# Initialize the server
server = Server()

# Define a route for the root URL
@server.router.route("/", methods=['GET'])
def home():
    return "HTTP/1.1 200 OK\n\nWelcome to the Home Page!"

# Start the server
server.start()

This example initializes a server, sets up a route for the root URL ("/"), and starts the server. The server will respond with a simple "Welcome to the Home Page!" message when accessed.

Handle Requests

You can handle different types of HTTP requests by defining corresponding routes. Here’s an example of handling a POST request:

python

@server.router.route("/submit", methods=['POST'])
def submit_form():
    return "HTTP/1.1 200 OK\n\nForm submitted successfully!"

Stop the Server

To stop the server, you can call the stop method:

python

    server.stop()

Advanced Usage

For more advanced use cases, you can extend DomNom's capabilities by customizing the server and request handling.

    Custom Request Handling

    You can parse and process the request data to handle more complex scenarios. For example, to handle form data:

    python

@server.router.route("/submit", methods=['POST'])
def submit_form(request):
    data = request.get('body', {})
    return f"HTTP/1.1 200 OK\n\nReceived data: {data}"

Server Configuration

You can configure the server’s behavior, such as setting the port or binding address:

python

    server = Server(host='0.0.0.0', port=8080)

Testing

To ensure everything is working correctly, you can run the tests provided in the tests directory. Use unittest to run the tests:

bash

python -m unittest discover

Contributing

Contributions to DomNom are welcome! If you would like to contribute, please follow these steps:

    Fork the Repository: Create a fork of the repository on GitHub.
    Create a Branch: Create a new branch for your feature or bug fix.
    Make Changes: Implement your changes and test them thoroughly.
    Submit a Pull Request: Submit a pull request with a clear description of your changes.

License

DomNom is licensed under the MIT License. See the LICENSE file for more information.
Contact

For any questions or support, please contact:

    Author: Hiralal Singh
    Email: hiralals221@gmail.com
    GitHub: https://github.com/Root-acess/DomNom/
