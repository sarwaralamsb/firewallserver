# Basic HTTP Firewall Server with Malicious Header Detection

This project implements a simple HTTP server that acts as a firewall to block requests containing specific malicious headers. It can be used to prevent potential attacks by filtering requests based on suspicious header patterns.

## Features

- **Malicious Header Detection**: Blocks requests containing predefined malicious headers.
- **Path-Based Filtering**: Specifically checks requests to `/tomcatwar.jsp`.
- **Customizable**: Easily add new malicious headers or modify filtering rules.

## How It Works

- The server listens for both **GET** and **POST** requests.
- If a request is made to `/tomcatwar.jsp` and it contains any of the predefined malicious headers, the server blocks the request and returns a **403 Forbidden** response.
- If the request does not match the malicious header conditions, the server responds with a **200 OK** and a JSON payload indicating success.

## Installation

1. Clone the repository:
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2. Ensure Python 3.x is installed on your system. You can check the version by running:
    ```bash
    python --version
    ```

3. Run the server:
    ```bash
    python firewall_server.py
    ```

    The server will start and listen on `localhost:8000`.

## Example Requests

### GET Request Example:
```bash
curl -X GET http://localhost:8000/tomcatwar.jsp -H "DNT: 1" -H "Content-Type: application/x-www-form-urlencoded"
