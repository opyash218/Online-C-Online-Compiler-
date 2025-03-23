#Online c++ compiler 

Overview

This project provides an Online C++ Compiler built with Node.js. It enables users to write, compile, and execute C++ code in a secure environment, with error handling and input support.

Features

✅ Compile and Execute C++ Code in Real-Time✅ Secure Sandbox Environment✅ Supports User Input for C++ Programs✅ REST API-Based Execution✅ Error Handling & Compilation Logs

Deployment Workflow

User submits C++ code through the web interface or API.

Code is stored in a temporary file on the server.

The system compiles the code using g++ (GCC Compiler).

If compilation is successful, the program is executed.

Output or errors are returned as a response.

Prerequisites

Node.js installed

g++ compiler (GCC)

Basic knowledge of REST APIs

Installation & Setup

Clone the repository:

git clone https://github.com/your-repo/Online-Cpp-Compiler.git
cd Online-Cpp-Compiler

Install Dependencies:

npm install

Run the Server:

node src/server.js

The API will be available at http://localhost:3000.

API Usage

➤ Compile & Run C++ Code

Endpoint: POST /compile

Request Body:

{
  "code": "#include<iostream>\nusing namespace std;\nint main(){cout << \"Hello, World!\"; return 0;}",
  "input": ""
}

Response:

{
  "output": "Hello, World!\n",
  "error": ""
}

Security Measures

Restricted Execution: The code runs in a limited environment to prevent unauthorized access.

Timeout Management: Execution terminates if it exceeds the allowed time.

Sandboxing: Each code execution happens in an isolated process.

CI/CD Integration (Optional)

For automated deployment, GitHub Actions or Jenkins can be used:

name: Deploy Compiler

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Install Dependencies
        run: npm install

      - name: Start Server
        run: node src/server.js

Monitoring & Logs

Use console.log for debugging during local development.

Implement logging mechanisms like Winston for production-level tracking.

Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

