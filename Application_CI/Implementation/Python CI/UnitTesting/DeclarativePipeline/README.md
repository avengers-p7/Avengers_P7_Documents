# Python Declarative Pipeline Unit Testing POC
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 07-02-2024 | 10-02-2024   |         v1     |     Shantanu    |
***

# Table of Content

# Introduction
Testing individual units or components of a software program is a vital part of the software development process, ensuring that each part performs as intended. In this context, we utilize the pytest framework to create [unit tests,](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/UnitTesting.md) validating the functionality of specific components. This practice contributes to verifying the overall correctness and reliability of a software application. For detailed understanding on Jenkins Pipeline click [here](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md).
***

# Prerequisites

|  Tool  | Description  |
| ------ | ---------- |
| Jenkins | Jenkins will orchestrate the CI/CD pipeline and execute the dependency analysis stage. |
| Python | Python is a versatile, high-level programming language. |
| Pytest | It is a widely used testing framework for Python, streamlining the task of creating and running tests. |
***

# Pipeline Configuration

**Agent Configuration:** This specifies that the pipeline can run on any available agent (slave node).

```
agent any
```

**Stages:** This section defines multiple stages for the pipeline.

```
stages 
{
    // Stages go here
}
```
**Code Checkout:** This stage checks out the code from the specified GitHub repository OT-Attendance using the 'main' branch and the specified credentials (Attendance-creds).

As it is a private repo so here we are using credentials which is already stored in the Jenkin server
pipeline {
    agent any
```
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the code from the specified Git repository
                    git branch: 'main', credentialsId: 'snataak', url: 'https://github.com/OT-MICROSERVICES/attendance-api.git'
                }
            }
        }
```

**Create Virtual Environment:** This stage creates a virtual environment named 'myenv' using Python's venv module and activates it.
stage('Create Virtual ENV') 

**NOTE:** _Here virtual environment is created to isolate project dependencies, ensuring a clean and controlled environment. It helps manage and specify the exact versions of Python and third-party libraries needed for a specific project, preventing conflicts with other projects or the global Python environment._
```
{
    steps 
    {
        script 
        {
            sh 'python3 -m venv myenv'
            sh '. myenv/bin/activate'
        }
    }
}
```

**Install Dependencies:** This stage installs the Python dependencies listed in the 'requirements.txt' file using the pip package manager.

```
stage('Install Dependencies')
 {
    steps {
        script {
            sh 'python3 -m pip install -r requirements.txt'
        }
    }
}
```

**Unit Testing:**

* This stage is dedicated to running unit tests for the project.

* It activates the virtual environment (. myenv/bin/activate) and then runs pytest on a specific test file (router/tests/test_cache.py).

* This assumes that your unit tests are written using the pytest framework, and that the specified test file is part of your project's test suite.
```
pipeline {
    agent any

    stages 
    {
        stage('Code Checkout') 
        {
            steps 
            {
                git branch: 'main', credentialsId: 'Attendance-creds', url: 'https://github.com/OT-MyGurukulam/OT-Attendance'
            }
        }
        
        stage('Creat Virtual ENV') 
        {
            steps 
            {
                script 
                {
                  sh 'python3 -m venv myenv'
                  sh '. myenv/bin/activate'
                }
            }
        }

        stage('Install Dependencies') 
        {
            steps 
            {
                script 
                {
                  sh 'pip install -r requirements.txt'
                  sh 'pip install pytest pytest-html'
                }
            }
        }

        stage('Unit Test') 
        {
            steps 
            {
                script 
                {
                    sh '. myenv/bin/activate'
                    //sh 'pytest router/tests/test_c
                    sh 'pytest router/tests/test_cache.py'
                    //sh 'pytest /var/lib/jenkins/workspace/unit_test '
                    
                    
                }
            }
        }
    }
}
```
