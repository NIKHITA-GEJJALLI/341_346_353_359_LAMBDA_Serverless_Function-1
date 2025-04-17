# 341_346_353_359_LAMBDA_Serverless_Function
# Serverless Function Execution Platform (UE22CS351B)

## Project Overview

The **Serverless Function Execution Platform** is designed to allow users to deploy and execute functions on-demand via HTTP requests, similar to AWS Lambda. The platform supports multiple programming languages (Python and JavaScript) and enforces execution constraints such as time limits and resource usage restrictions. It utilizes Docker containers and an additional virtualization technology for optimizing function execution. The system also includes a web-based monitoring dashboard to visualize key performance metrics.

## Project Objective

- **Primary Goal**: Design and implement a serverless function execution platform that supports Python and JavaScript.
- **Key Features**:
  - Function deployment via HTTP requests.
  - Support for multiple programming languages.
  - Integration of at least two virtualization technologies for improved performance (Docker + another technology).
  - Function execution metrics monitoring (response time, error rates, and resource utilization).
  - A web-based dashboard for real-time insights.

## Team Members

- **Naru Meghana** (PES2UG22CS341)
- **Neha Girish** (PES2UG22CS346)
- **Nida Fathima** (PES2UG22CS353)
- **Nikhita G** (PES2UG22CS359)

---

## Table of Contents

1. [Installation](#installation)
2. [Environment Setup](#environment-setup)
3. [Usage](#usage)
4. [Folder Structure](#folder-structure)
5. [Technologies Used](#technologies-used)
6. [Contributing](#contributing)

---

## Installation

Follow these steps to set up the environment locally:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/NIKHITA-GEJJALLI/341_346_353_359_Lambda_Serverless_function.git
    cd 341_346_353_359_Lambda_Serverless_function
    ```

2. **Set Up Backend (Python/FastAPI)**:
    - Install dependencies for Python:
    ```bash
    pip install -r requirements.txt
    ```

    **OR for JavaScript (Express)**:
    - Install dependencies for Node.js:
    ```bash
    npm install
    ```

3. **Set Up Docker**:
    - Ensure you have Docker installed. If not, you can download it from [here](https://www.docker.com/get-started).
    - Build the Docker containers for Python and JavaScript:
    ```bash
    docker build -t python-container ./container/Dockerfile-python
    docker build -t node-container ./container/Dockerfile-node
    ```

4. **Start the API Server**:
    - For Python (FastAPI):
    ```bash
    uvicorn backend.main:app --reload
    ```

    **OR for JavaScript (Express)**:
    ```bash
    node backend/app.js
    ```

---

## Environment Setup

1. **Install Required Tools**:
    - **Docker**: To containerize the functions.
    - **Python 3.x** or **Node.js**: Based on which backend you choose (FastAPI or Express).
    - **Git**: To clone the repository and manage version control.

2. **Database**:
    - We are using SQLite for the initial stage to store function metadata (name, language, route, timeout).
    - If you wish to use a different database (e.g., PostgreSQL), update the `database.py` file accordingly.

---

## Usage

Once the server is running:

- **Deploy a Function**: You can deploy functions via HTTP requests. For example, use `POST` to upload your Python or JavaScript code.
- **Execute a Function**: Send a request to trigger the function execution (either in Docker or other containers).
- **Monitor Function Execution**: Access the monitoring dashboard (to be implemented in later weeks) to track metrics like response time, error rates, and resource usage.

---

## Folder Structure

```
├── backend/               # Backend API server (FastAPI/Express)
│   ├── main.py            # FastAPI application
│   └── app.js             # Express application
│
├── frontend/              # Frontend application (Streamlit or React)
├── container/             # Dockerfiles for Python and JavaScript functions
│   ├── Dockerfile-python  # Python Dockerfile
│   └── Dockerfile-node    # Node.js Dockerfile
│
├── docs/                  # Documentation, including system design and API notes
│
├── tests/                 # Unit and integration tests
│
└── requirements.txt       # Python dependencies
└── package.json           # Node.js dependencies
```

---

## Technologies Used

- **Backend**:
  - Python: FastAPI (for API server)
  - JavaScript: Express (for API server)
  
- **Virtualization**:
  - Docker (for function execution isolation)
  - Second virtualization technology (Firecracker MicroVMs, Nanos Unikernel, or gVisor)

- **Frontend** (coming in later weeks):
  - Streamlit or React for the dashboard UI

- **Database**:
  - SQLite (for storing function metadata)

- **CI/CD**:
  - GitHub Actions (or any CI/CD tool you choose)

---

## Contributing

We welcome contributions to this project! Please follow these steps if you'd like to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push them to your fork.
4. Create a pull request to merge your changes into the main repository.
