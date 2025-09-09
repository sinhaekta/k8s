# BoardgameListingWebApp

## Description

**Board Game Database Full-Stack Web Application.**
This web application displays lists of board games and their reviews. While anyone can view the board game lists and reviews, they are required to log in to add/ edit the board games and their reviews. The 'users' have the authority to add board games to the list and add reviews, and the 'managers' have the authority to edit/ delete the reviews on top of the authorities of users.  

## Technologies

- Java
- Spring Boot
- Amazon Web Services(AWS) EC2
- Thymeleaf
- Thymeleaf Fragments
- HTML5
- CSS
- JavaScript
- Spring MVC
- JDBC
- H2 Database Engine (In-memory)
- JUnit test framework
- Spring Security
- Twitter Bootstrap
- Maven

## Features

- Full-Stack Application
- UI components created with Thymeleaf and styled with Twitter Bootstrap
- Authentication and authorization using Spring Security
  - Authentication by allowing the users to authenticate with a username and password
  - Authorization by granting different permissions based on the roles (non-members, users, and managers)
- Different roles (non-members, users, and managers) with varying levels of permissions
  - Non-members only can see the boardgame lists and reviews
  - Users can add board games and write reviews
  - Managers can edit and delete the reviews
- Deployed the application on AWS EC2
- JUnit test framework for unit testing
- Spring MVC best practices to segregate views, controllers, and database packages
- JDBC for database connectivity and interaction
- CRUD (Create, Read, Update, Delete) operations for managing data in the database
- Schema.sql file to customize the schema and input initial data
- Thymeleaf Fragments to reduce redundancy of repeating HTML elements (head, footer, navigation)

## Architecture

## Infrastructure:
- EKS Cluster with a node group (2 nodes).
- EC2 instances:
  One in a public subnet running Nexus Repository and SonarQube.
  One in a private subnet as a self-hosted runner for Azure DevOps.

## CI/CD Flow:
- SonarQube for static code analysis and code quality checks.
- Nexus for storing the built artifacts (JAR files).
- Azure Pipeline automates the process of building, scanning, and deploying the application.

## Application Deployment:
- Docker: The application is packaged as a JAR, built into a Docker image, and stored in AWS ECR.
- Kubernetes: Deployed via EKS using Kubernetes objects (Deployment, Service, Ingress).
- Ingress routes traffic to the application via an Application Load Balancer (ALB).

## Monitoring:
- Prometheus collects metrics and sends them to Grafana for visualization.
- Alerting configured in Grafana to notify on application anomalies.
