# AI-Based Transport Route Planning System using Shortest Path Algorithms

## Project Overview

The AI-Based Transport Route Planning System is an intelligent route planning application that combines shortest path algorithms with machine learning-based travel time prediction.

Traditional route planning systems generally focus on finding the shortest distance between a source and destination. However, the shortest route may not always be the fastest route because travel time can be affected by traffic congestion, vehicle speed, road type, weather conditions, and other transportation factors.

This project addresses this problem by combining shortest path algorithms such as Dijkstra's Algorithm and A* Algorithm with a machine learning model that predicts estimated travel time. The system compares candidate routes and recommends a suitable route based on route characteristics and predicted travel time.

The application follows Service-Oriented Architecture (SOA) and a microservices-based approach, with separate services for authentication, route processing, AI prediction, and route recommendation.

---

## Team Members

| Name                     | University ID |
| ------------------------ | ------------- |
| P. Hasitha Sai Keerthana | 2420090107    |
| C. Suma Priya            | 2420030337    |
| L. Mrudani               | 2420030591    |

### Faculty Guide

K. Venkateswari

Department of Computer Science and Engineering
KLH Deemed to be University

---

## Problem Statement

Traditional shortest path systems mainly select routes based on distance. However, the shortest route may experience high traffic congestion or unfavorable road and weather conditions and therefore may not provide the minimum travel time.

The proposed system aims to provide adaptive route recommendations by combining:

* Shortest path algorithms
* Machine learning-based travel-time prediction
* Traffic and congestion information
* Route comparison
* SOA and microservices architecture

---

## Objectives

* Develop an AI-based transport route planning system.
* Implement Dijkstra's and A* shortest path algorithms.
* Predict estimated travel time using machine learning.
* Consider traffic congestion, vehicle speed, road type, weather, and route-related information.
* Compare multiple candidate routes.
* Recommend an efficient route based on predicted travel time.
* Provide estimated time of arrival (ETA).
* Implement SOA and microservices principles.
* Provide secure authentication using JWT.
* Implement service discovery using Eureka.
* Use Spring Cloud Gateway for API routing.
* Develop an independent AI service using Python and FastAPI.

---

## Key Features

* User registration and login
* JWT-based authentication
* Source and destination selection
* Shortest path calculation
* Dijkstra's Algorithm
* A* Algorithm
* AI-based travel-time prediction
* Traffic-aware route evaluation
* Route comparison
* Adaptive route recommendation
* ETA prediction
* Route history
* User dashboard
* Microservices-based backend
* Service discovery using Eureka
* API Gateway routing

---

## System Architecture

```text
                         USER
                           |
                           v
                    React.js Frontend
                           |
                           v
                Spring Cloud Gateway
                           |
                           v
                    Eureka Server
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v
 Authentication       Route Service      AI Prediction
    Service               Service            Service
        |                  |                  |
        |                  |             Python + FastAPI
        |                  |                  |
        |                  v                  v
        |             Dijkstra / A*      ML Prediction
        |                  |                  |
        |                  +--------+---------+
        |                           |
        |                           v
        |                  Recommendation
        |                     Service
        |                           |
        +---------------------------+
                                    |
                                    v
                           Recommended Route
                                    +
                                   ETA
                                    |
                                    v
                              React Frontend
```

---

## Microservices

### 1. Authentication Service

The Authentication Service manages user authentication and authorization.

Responsibilities:

* User registration
* User login
* JWT token generation
* Authentication
* Authorization
* User management

### 2. Route Service

The Route Service handles route-related operations.

Responsibilities:

* Source and destination processing
* Route generation
* Route information
* Shortest path calculation
* Dijkstra's Algorithm
* A* Algorithm
* Route history

### 3. AI Prediction Service

The AI Prediction Service is an independent Python-based microservice developed using FastAPI and Scikit-learn.

It receives transportation-related features and predicts the estimated travel time.

The ML model uses relevant features available in the selected dataset, including:

* Traffic volume
* Average speed
* Congestion level
* Road type
* Weather conditions

The output of the AI service is:

```text
Predicted Travel Time
```

### 4. Route Recommendation Service

The Route Recommendation Service combines the results from the Route Service and AI Prediction Service.

```text
Candidate Routes
       +
Predicted Travel Times
       |
       v
Route Comparison
       |
       v
Best Route Recommendation
       |
       v
ETA
```

---

## AI/ML Component

The machine learning component focuses on travel-time prediction.

The project uses the Kaggle dataset:

**Urban Traffic Congestion and Travel Time Analysis**

The dataset is a synthetic and anonymized urban traffic dataset containing more than 2,500 records. It is provided in CSV format and is designed for applications including travel-time prediction and traffic-congestion analysis.

### Dataset Features

The dataset contains transportation observations including:

* Traffic volume
* Average speed
* Congestion level
* Road type
* Weather conditions
* Estimated travel time

These factors represent transportation and environmental conditions that can influence travel time.

### ML Workflow

```text
Urban Traffic Dataset
          |
          v
    Data Preprocessing
          |
          v
     Feature Selection
          |
          v
      Train/Test Split
          |
          v
   Scikit-learn Model
          |
          v
    Model Evaluation
          |
          v
      Trained Model
          |
          v
        FastAPI
          |
          v
 Predicted Travel Time
```

The trained machine learning model is exposed through the FastAPI service. During route evaluation, the AI service receives the required route and traffic-related features and returns the predicted travel time.

---

## Dataset Source

The dataset used for the AI component is:

**Urban Traffic Congestion and Travel Time Analysis**

Dataset source:

[Kaggle Dataset](https://www.kaggle.com/datasets/jayjoshi37/urban-traffic-congestion-and-travel-time-analysis?utm_source=chatgpt.com)

### Dataset Information

| Property        | Details                                           |
| --------------- | ------------------------------------------------- |
| Dataset         | Urban Traffic Congestion and Travel Time Analysis |
| Source          | Kaggle                                            |
| Format          | CSV                                               |
| Records         | 2,500+                                            |
| Type            | Synthetic and anonymized                          |
| Primary ML Task | Travel-time prediction                            |
| Additional Task | Traffic congestion analysis                       |
| License         | CC0: Public Domain                                |

The Kaggle dataset description identifies travel-time prediction as one of its intended use cases.

---

## Shortest Path Algorithms

### Dijkstra's Algorithm

Dijkstra's Algorithm is used to find the shortest path between nodes in a weighted graph.

In this project, it can be used to determine the shortest route between the source and destination based on the assigned route weights.

### A* Algorithm

A* is a heuristic-based shortest path algorithm that uses the cost already travelled along with an estimated cost to the destination.

It can efficiently search for a suitable path when geographical information is available.

---

## Adaptive Route Recommendation

The system does not rely only on the shortest distance.

For example:

```text
Route A
Distance: 5 km
Traffic: High
Predicted Time: 35 minutes

Route B
Distance: 7 km
Traffic: Low
Predicted Time: 25 minutes
```

Although Route A is shorter in distance, Route B can be recommended because its predicted travel time is lower.

The overall process is:

```text
Shortest Path Algorithms
          +
AI Travel-Time Prediction
          |
          v
Route Comparison
          |
          v
Adaptive Route Recommendation
```

---

## SOA and Microservices Concepts

The project demonstrates the following SOA and microservices concepts:

* Service-oriented architecture
* Independent services
* REST APIs
* Service contracts and endpoints
* API Gateway
* Service discovery
* Eureka Server
* Microservice communication
* JWT authentication
* Spring Security
* CORS
* Database-per-service concept
* Spring Data JPA
* Unit testing
* Integration testing

---

## Security

Security is implemented using:

* Spring Security
* JWT authentication
* Authorization
* CORS configuration

JWT tokens are used to authenticate users and protect restricted API endpoints.

TLS/SSL can be configured for secure communication where required.

---

## Database

PostgreSQL is used for persistent data storage.

The database stores information such as:

* User details
* Route information
* Travel history
* Prediction-related information
* Application data

Spring Data JPA is used for database interaction in the Spring Boot services.

The project follows the database-per-service concept where appropriate, allowing individual services to manage their own related data.

---

## Technology Stack

| Technology           | Purpose              |
| -------------------- | -------------------- |
| React.js             | Frontend             |
| Java                 | Backend development  |
| Spring Boot          | Microservices        |
| Spring Cloud Gateway | API Gateway          |
| Spring Cloud Eureka  | Service Discovery    |
| Spring Security      | Security             |
| JWT                  | Authentication       |
| PostgreSQL           | Database             |
| Spring Data JPA      | Database interaction |
| Python               | AI/ML development    |
| FastAPI              | AI prediction API    |
| Scikit-learn         | Machine Learning     |
| Dijkstra             | Shortest path        |
| A*                   | Shortest path        |
| GitHub               | Version control      |

---

## Project Flow

```text
1. User enters source and destination
                 |
                 v
2. React sends request to API Gateway
                 |
                 v
3. Gateway identifies the required service
                 |
                 v
4. Eureka discovers the required service
                 |
                 v
5. Route Service generates candidate routes
                 |
                 v
6. Dijkstra / A* calculates shortest paths
                 |
                 v
7. Route and traffic-related features are sent
   to the AI Prediction Service
                 |
                 v
8. ML model predicts travel time
                 |
                 v
9. Recommendation Service compares routes
                 |
                 v
10. Best route and ETA are returned
                 |
                 v
11. React displays the recommendation
```

---

## AI Prediction Flow

```text
Traffic Data
     |
     +---- Traffic Volume
     +---- Average Speed
     +---- Congestion Level
     +---- Road Type
     +---- Weather
     |
     v
Data Preprocessing
     |
     v
Feature Selection
     |
     v
Scikit-learn Model
     |
     v
Predicted Travel Time
     |
     v
Route Recommendation Service
```

---


---

## Expected Outcome

The completed system will provide an intelligent route planning platform that:

* Finds candidate routes using shortest path algorithms.
* Predicts travel time using machine learning.
* Considers traffic, congestion, road type, weather, and speed-related factors.
* Compares alternative routes.
* Recommends a suitable route.
* Provides estimated travel time and ETA.
* Provides secure user authentication.
* Uses independent microservices for modularity and maintainability.
* Demonstrates SOA and microservices concepts in a practical transportation application.

---

## Future Enhancements

* Real-time traffic data integration
* Live map integration
* Real-time weather API
* Dynamic route updates
* Public transportation integration
* Mobile application
* Advanced machine learning models
* Real-time traffic-aware route prediction
* Support for additional transportation modes

---

## Conclusion

The AI-Based Transport Route Planning System combines shortest path algorithms and artificial intelligence to provide adaptive transportation recommendations.

By integrating Dijkstra and A* algorithms with machine learning-based travel-time prediction, the system goes beyond traditional distance-based route selection.

The SOA and microservices architecture separates authentication, route processing, AI prediction, and route recommendation into independent services. This provides a modular and maintainable architecture while demonstrating important SOA concepts such as REST services, service discovery, API Gateway, security, service communication, and database management.

The selected Kaggle dataset provides a practical foundation for developing the travel-time prediction component, with traffic, speed, congestion, road, and weather information available for machine learning applications.
