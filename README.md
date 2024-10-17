# Secure CI/CD Pipeline with Jenkins, Docker, SonarQube, and OWASP Dependency-Check

## Overview

This project demonstrates a CI/CD pipeline integrating Jenkins, Docker, SonarQube for code quality, and OWASP Dependency-Check for security scanning.

## Tools & Technologies

- **Jenkins**: For CI/CD pipeline automation.
- **Docker**: To run services in isolated containers.
- **SonarQube**: For code quality analysis.
- **OWASP Dependency-Check**: To scan for vulnerabilities in dependencies.

## Setup

1. Clone the repository:
   git clone https://github.com/HMyounus80/secure-ci-cd-pipeline.git cd secure-ci-cd-pipeline

2. Install Docker on your system and use the following command to run all services:

docker-compose up -d

3. To run a SonarQube scan manually:
   sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.sources=./src

sonar-scanner -Dsonar.projectKey=your_project_key -Dsonar.sources=./src

4. To generate a security report using OWASP Dependency-Check:

docker run --rm -v $(pwd):/src owasp/dependency-check --scan /src --format HTML

5. Open the report in a browser:

open ./reports/dependency-check-report.html

## CI/CD Pipeline

1. **Checkout Code**: Pulls the latest code from the repository.
2. **Build**: Compiles the code using Maven.
3. **SonarQube Analysis**: Checks code quality.
4. **OWASP Dependency-Check**: Scans for vulnerabilities in project dependencies.
