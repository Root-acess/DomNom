
# DomNom
DomNom

DomNom is a Python package designed to facilitate routing and management for web applications. It provides a simple and efficient way to create and manage routes, handle requests, and serve content. This package is ideal for developers looking to build lightweight web servers or integrate routing into their applications.
Features

    Routing: Easily define and manage routes for different HTTP methods (GET, POST, etc.).
    Request Handling: Process incoming HTTP requests and generate appropriate responses.
    Server Management: Start and stop a simple HTTP server for local testing and development.

    

### Installation

To install DomNom, use pip:

```sh
pip install DomNom
```



## Quick Start

Here is a quick guide to get you started with DomNom.
Basic Usage


## Initialize the server
```sh
server = Server()

```

## Define a route for the root URL:


```sh @server.router.route("/", methods=['GET'])
def home():
    return "HTTP/1.1 200 OK\n\nWelcome to the Home Page!"

```

## Start the server
```
server.start()
```

 > This example initializes a server, sets up a route for the root URL ("/"), and starts the server. The server will respond with a simple "Welcome to the Home Page!" message when accessed.

## Handle Requests

  You can handle different types of HTTP requests by defining corresponding routes. Here’s an example of handling a POST request:
```sh

@server.router.route("/submit", methods=['POST'])
def submit_form():
    return "HTTP/1.1 200 OK\n\nForm submitted successfully!"

```

## Stop the Server

To stop the server, you can call the stop method:

python
```
    server.stop()
```

Advanced Usage

For more advanced use cases, you can extend DomNom's capabilities by customizing the server and request handling.

   -[]  Custom Request Handling

   -[] You can parse and process the request data to handle more complex scenarios. For example, to handle form data:

 ```sh

@server.router.route("/submit", methods=['POST'])
def submit_form(request):
    data = request.get('body', {})
    return f"HTTP/1.1 200 OK\n\nReceived data: {data}"

```

## Server Configuration

You can configure the server’s behavior, such as setting the port or binding address:

python

```sh
    server = Server(host='0.0.0.0', port=8080)
```

## Usage
Basic Usage
Here’s a basic example of how to use DomNom:

```sh
# Import the Server class from DomNom
from DomNom import Server

# Create an instance of the Server class
server = Server()

# Define a route for the home page
@server.router.route("/", methods=['GET'])
def home():
    return "HTTP/1.1 200 OK\n\nWelcome to the Home Page!"

# Start the server
server.start()
```


## Handle a request (example)
```sh
request = "GET / HTTP/1.1\r\nHost: localhost\r\n\r\n"
response = server.handle_request(request)
print(response)
```
Complete Example with Server Class
Here’s a more complete example based on a simple server setup:

# Import the necessary classes from DomNom
```sh
from DomNom.server import Server

def main():
    # Create a Server instance
    server = Server(host='localhost', port=8080)

    # Define a route for the home page
    @server.router.route("/", methods=['GET'])
    def home():
        return "HTTP/1.1 200 OK\n\nWelcome to the Home Page!"

    # Start the server
    print("Starting server on http://localhost:8080")
    server.start()

if __name__ == "__main__":
    main()
```




### Documentation
 >Ensure that your README.md file or other documentation provides details on:

- [x] How to install and use the package.
- [x] Any configuration or setup required.
- [x] Example code and API details.
- [x] API Reference
- [x] Server
- [x] Server(host: str, port: int): Initializes the server with the specified host and port.
- [x] start(): Starts the server.
- [x] handle_request(request: str): Handles an HTTP request and returns a response.


License
This project is licensed under the MIT License - see the LICENSE file for details.


## Contributing

Contributions to DomNom are welcome! If you would like to contribute, please follow these steps:

    Fork the Repository: Create a fork of the repository on GitHub.
    Create a Branch: Create a new branch for your feature or bug fix.
    Make Changes: Implement your changes and test them thoroughly.
    Submit a Pull Request: Submit a pull request with a clear description of your changes.



For any questions or support, please contact:

    Email: hiralals221@gmail.com
    GitHub: https://github.com/Root-acess/DomNom/
