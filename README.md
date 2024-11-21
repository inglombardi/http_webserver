# http_webserver
This work helps you to design a HTTP server


# HTTP/1.1 Web Server with 130 Mimetypes 

## Overview

This project, initiated in January 2017 and completed by June 2017, involves the development of an HTTP/1.1 web server written in Python 2.8. The goal was to understand core concepts such as RESTful APIs, network principles, object-oriented programming (OOP), and Test-Driven Development (TDD). The server was developed during my school years and served as a valuable opportunity to explore these essential topics.

The implementation of this server heavily utilizes conditional constructs like `elif-else`. This decision was driven not by a lack of experience with the language but rather by the characteristics of Python 2.8 at the time, which was less advanced compared to the features available in Python 3.12. 

## Project Details

### Supported HTTP Methods

- **GET**
- **PUT**
- **POST**
- **HEAD**
- **OPTIONS**
- **CONNECT**
- **DELETE**
- **TRACE**

### Software Architecture

The server is implemented as a macro Python script that was successively rewritten in C with a Modular Approach. It runs from the Linux terminal and contains the complete implementation of the web server along with several classes, thereby demonstrating object-oriented principles since the server object is constructed and listens on a port number defined by the variable `PORT_NUMBER`. This variable's type is not explicitly defined, but Python recognizes it as an `Integer` type.

### Class Structure

- **Main Class**: The first class defined in the code is referred to as the `myHandler` class. This class was initially developed to handle client requests sequentially.
- **Threading Server**: This class was later added to manage client requests concurrently. It listens for client connections and dispatches them to the appropriate handler class.

### Implementation Notes

- **C Code Management**: The C server code handles all public and private pipes. Each error case is encapsulated within conditional constructs.
- **File Operations**: A list is used to manage file operations defined by the C language's `fopen` pointer.
- **Fork Error Handling**: For each `fork()` operation, error checking is performed to ensure there are no issues with the child process created for the user-specified Linux command. Appropriate error-handling code was implemented for each error case.
- **Python Server Connection**: The connection to the server is established by re-running the `serverFinal.py` script.
- **Server Configuration**: The server is configured with an unspecified IP address that defaults to `127.0.0.1` (visible within the LAN). The port number is also unspecified (e.g., `12000`), ensuring it is higher than the maximum well-known port number range.

### Client Access

Once the server is instantiated, as a local user (client), you can access it using `curl` from another terminal window to make HTTP requests.

## References

- **Python Version**: Developed using Python 2.8.
- **Port Number**: Chosen higher than the maximum well-known port number range.
- **IP Address**: 127.0.0.1 (visible within the local network environment)

This project was a hands-on experience in understanding network programming, OOP principles, and error-handling strategies in a low-level environment. It offered a unique perspective on building an HTTP server from the ground up using early language constructs and adapting to available resources at the time.
