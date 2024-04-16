# Transcendence

## Overview

Transcendence is a dynamic ping pong game website that leverages a robust microservices architecture. The backend is powered by Django, with a frontend composed of Node.js, Vanilla.js, and Bootstrap. PostgreSQL is used for data persistence, while the ELK stack is employed for comprehensive logging and monitoring.

### Technologies Used

- **Backend:** Django (Python)
- **Frontend:** Node.js, Vanilla.js, Bootstrap
- **Database:** PostgreSQL
- **Logging and Monitoring:** ELK Stack (Elasticsearch, Logstash, Kibana, Metricbeat)
- **Containerization:** Docker
- **Continuous Integration/Deployment:** GitLab CI/CD

## Architecture

The application is structured around multiple microservices, each responsible for handling different aspects of the game's functionality:

- **Auth Service:** Manages authentication and user session handling.
- **Friend Service:** Allows players to connect with friends within the game.
- **Player Service:** Handles player data and interactions.
- **Matchmaking Service:** Facilitates the matching of players for games.
- **Stats Service:** Collects and provides statistics and player rankings.
- **Reverse Proxy (rproxy):** Directs requests to the appropriate services.
- **Frontend Service:** Delivers and manages the frontend application.
- **PostgreSQL:** Stores all relational data for the services.
- **ELK Stack:** Comprises Elasticsearch, Logstash, Kibana, and Metricbeat for logging and monitoring the services.

## Problem Statement

Before integrating the GitLab CI/CD pipeline, changes in any service required extensive manual testing, which was both time-consuming and error-prone. Often, some test cases were overlooked, leading to undetected issues during development. This lack of automated testing and continuous integration led to significant delays and potential faults in the production environment.

## CI/CD Pipeline Solution

To address these challenges, we implemented a CI/CD pipeline in GitLab that automates the testing, building, and deployment processes:

### Pipeline Stages

1. **Test:** Each microservice undergoes automated tests. If any part of the test fails, the pipeline halts, preventing the propagation of errors.
2. **Build:** Docker images for each service are built only if the tests pass, ensuring that only verified code is containerized.
3. **Deploy:** Upon successful build, the Docker images are pushed to the Docker registry and then deployed to the production servers.

This automation significantly reduces manual testing efforts and increases the reliability and efficiency of the deployment process.

## Getting Started

To set up and run Transcendence locally, you can follow these steps:

1. **Clone the repository:**
   ```bash
   git clone ##The repo url##
   cd ##The repo name

   make

