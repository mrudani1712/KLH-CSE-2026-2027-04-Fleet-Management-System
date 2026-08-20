# AI-Based Smart Transport Fleet Management System

## Project Overview

The AI-Based Smart Transport Fleet Management System is a Service-Oriented Architecture (SOA)-based intelligent transportation solution designed to improve the efficiency, reliability, and utilization of vehicle fleets.

Traditional fleet management systems mainly focus on vehicle tracking, driver management, trip scheduling, fuel monitoring, and maintenance record management. However, they often rely on manual decision-making and respond to problems only after they occur.

The proposed system integrates Artificial Intelligence (AI), Machine Learning (ML), and independent SOA-based services to provide intelligent and predictive fleet management.

The system manages vehicles, drivers, trips, maintenance, and routes through separate services that communicate through APIs. Machine learning techniques are used for predictive maintenance, fuel-consumption prediction, vehicle allocation, and travel-time/route prediction.

Based on vehicle condition, availability, fuel efficiency, trip requirements, and predicted maintenance risks, the system recommends the most suitable vehicle and route for a particular trip.

The major advantage of the proposed system is that it goes beyond basic fleet monitoring by providing AI-assisted decision-making and predictive optimization. The modular SOA architecture allows individual services to be developed, deployed, and scaled independently.

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

Traditional fleet management systems primarily focus on monitoring vehicles, drivers, trips, fuel usage, and maintenance records. Vehicle allocation and operational decisions are often performed manually, while maintenance is frequently handled after a problem occurs.

This can lead to:

* Unexpected vehicle breakdowns
* Increased maintenance costs
* Poor vehicle utilization
* Unnecessary fuel consumption
* Inefficient vehicle allocation
* Increased operational downtime
* Manual and reactive decision-making

The proposed system addresses these limitations by combining SOA, AI/ML, predictive analytics, and route optimization to support proactive fleet management.

---

## Objectives

* To develop an AI-based smart fleet management system.
* To manage vehicles, drivers, trips, maintenance, and routes through independent services.
* To predict potential vehicle maintenance requirements before breakdowns occur.
* To predict fuel consumption for better vehicle and trip planning.
* To recommend the most suitable vehicle for a particular trip.
* To predict travel time and support route selection.
* To optimize routes using Dijkstra's Algorithm.
* To improve vehicle utilization and operational efficiency.
* To reduce fuel consumption and operational costs.
* To minimize unexpected breakdowns and vehicle downtime.
* To demonstrate SOA and microservices principles through API-based services.

---

## Key Features

### Vehicle Management

* Vehicle registration and management
* Vehicle availability tracking
* Vehicle condition monitoring
* Fuel-efficiency information
* Vehicle specifications
* Maintenance status

### Driver Management

* Driver registration and management
* Driver information
* Driver-vehicle assignment
* Driver-trip assignment

### Trip Management

* Create and manage trips
* Assign vehicles and drivers
* Store trip requirements
* Track trip information
* Estimate travel time

### Predictive Maintenance

The AI/ML component identifies vehicles that may require maintenance before a potential breakdown.

The prediction can consider factors such as:

* Vehicle usage
* Mileage
* Previous maintenance
* Vehicle condition
* Operational information
* Maintenance history

This supports proactive maintenance planning and can reduce unexpected downtime.

### Fuel Consumption Prediction

Machine learning is used to predict fuel consumption based on available vehicle and trip-related information.

This can help:

* Identify inefficient vehicles
* Improve vehicle selection
* Reduce unnecessary fuel consumption
* Control operational costs

### AI-Based Vehicle Allocation

The system recommends a suitable vehicle for a trip based on factors such as:

* Vehicle availability
* Vehicle condition
* Fuel efficiency
* Trip requirements
* Predicted maintenance risk
* Operational suitability

### Route Planning and Prediction

The system uses Dijkstra's Algorithm for route optimization and can use the Google Maps API for real-world geographical and route information.

The system considers route characteristics and predicted travel time when recommending a route.

### Fleet Analytics

The system can provide information about:

* Vehicle utilization
* Fuel consumption
* Maintenance requirements
* Trip performance
* Route efficiency
* Fleet operational performance

---

## System Architecture

The system follows a Service-Oriented Architecture (SOA) approach.

```text
                         USER
                           |
                           v
                    React Frontend
                           |
                           v
                     FastAPI/API Layer
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
   Vehicle Service   Driver Service    Trip Service
          |                |                |
          +----------------+----------------+
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
 Maintenance Service  Route Service   AI/ML Service
                                            |
                               +------------+------------+
                               |            |            |
                               v            v            v
                         Random Forest   XGBoost    Predictions
                               |            |            |
                               +------------+------------+
                                            |
                                            v
                                  Recommendation
                                            |
                                            v
                                      PostgreSQL
```

---

## SOA Services

### 1. Vehicle Service

Responsible for managing vehicle-related information.

Responsibilities:

* Vehicle registration
* Vehicle details
* Vehicle availability
* Vehicle status
* Vehicle condition
* Fuel-efficiency information

### 2. Driver Service

Responsible for driver-related information.

Responsibilities:

* Driver registration
* Driver details
* Driver assignment
* Driver availability
* Driver-trip allocation

### 3. Trip Service

Responsible for trip planning and management.

Responsibilities:

* Trip creation
* Trip requirements
* Vehicle assignment
* Driver assignment
* Trip records
* Travel information

### 4. Maintenance Service

Responsible for vehicle maintenance information.

Responsibilities:

* Maintenance records
* Service history
* Maintenance status
* Maintenance scheduling
* Predicted maintenance requirements

### 5. Route Service

Responsible for route processing and optimization.

Responsibilities:

* Source and destination processing
* Route generation
* Distance calculation
* Dijkstra's shortest-path algorithm
* Route information
* Travel-time information

### 6. AI/ML Service

An independent Python-based service responsible for intelligent predictions.

Responsibilities:

* Predictive maintenance
* Fuel-consumption prediction
* Vehicle suitability/selection
* Travel-time prediction
* AI-based recommendations

---

## AI/ML Component

The AI/ML component is the core intelligent part of the system.

Instead of only monitoring current fleet conditions, the system uses machine learning to support prediction and decision-making.

### Machine Learning Models

#### Random Forest

Random Forest can be used for tasks such as:

* Predictive maintenance classification
* Vehicle condition classification
* Vehicle suitability prediction

#### XGBoost

XGBoost can be used for tasks such as:

* Fuel-consumption prediction
* Travel-time prediction
* Maintenance-risk prediction
* Other regression or classification tasks

The final model for each task can be selected based on the available dataset and model performance.

---

## Predictive Maintenance Workflow

```text
Vehicle Data
     |
     v
Data Preprocessing
     |
     v
Feature Selection
     |
     v
Random Forest / XGBoost
     |
     v
Maintenance Risk Prediction
     |
     v
Maintenance Recommendation
     |
     v
Proactive Vehicle Maintenance
```

The system aims to identify vehicles that may require maintenance before a potential failure occurs.

---

## Fuel Consumption Prediction Workflow

```text
Vehicle + Trip Data
        |
        v
Data Preprocessing
        |
        v
Feature Engineering
        |
        v
XGBoost / ML Model
        |
        v
Predicted Fuel Consumption
        |
        v
Vehicle Selection / Planning
```

Fuel prediction can support better vehicle allocation and help reduce unnecessary fuel usage.

---

## AI-Based Vehicle Allocation

The system does not simply assign the first available vehicle.

Instead, it evaluates available vehicles using factors such as:

```text
Vehicle Availability
        +
Vehicle Condition
        +
Fuel Efficiency
        +
Trip Requirements
        +
Maintenance Risk
        +
Predicted Performance
        |
        v
AI-Based Vehicle Recommendation
```

For example, if one vehicle is available but has a high predicted maintenance risk and poor fuel efficiency, the system can recommend another suitable vehicle with lower risk and better efficiency.

---

## Route Optimization

The system uses Dijkstra's Algorithm for shortest-path calculation.

Google Maps API can be integrated to obtain real-world geographical and route information.

The route recommendation process can consider:

* Route distance
* Travel time
* Vehicle suitability
* Traffic-related information
* Route characteristics

### Example

```text
Route A
Distance: 5 km
Predicted Time: 35 minutes

Route B
Distance: 7 km
Predicted Time: 25 minutes
```

Although Route A is shorter, Route B may be recommended because its predicted travel time is lower.

---

## Overall Intelligent Workflow

```text
User
 |
 v
React Frontend
 |
 v
API Layer
 |
 +--------------------+
 |                    |
 v                    v
Fleet Services      Route Service
 |                    |
 |                    v
 |             Dijkstra Algorithm
 |                    |
 +----------+---------+
            |
            v
        AI/ML Service
            |
      +-----+-----+
      |     |     |
      v     v     v
   Fuel   Travel  Maintenance
 Prediction Time   Risk
      |     |     |
      +-----+-----+
            |
            v
    Vehicle + Route Recommendation
            |
            v
       React Dashboard
```

---

## Database

PostgreSQL is used for persistent data storage.

The database can store:

* Vehicle details
* Driver details
* Trip information
* Maintenance records
* Fuel-related information
* Route information
* Prediction-related information
* Application data

The SOA design allows services to manage their respective data independently where appropriate.

---

## Technology Stack

| Technology           | Purpose                                  |
| -------------------- | ---------------------------------------- |
| React                | Frontend                                 |
| Python               | Backend and AI/ML development            |
| FastAPI              | API and independent AI/ML services       |
| Machine Learning     | Prediction and decision support          |
| Random Forest        | Classification/prediction                |
| XGBoost              | Regression/classification and prediction |
| Dijkstra's Algorithm | Shortest-path route optimization         |
| Google Maps API      | Maps and real-world route information    |
| PostgreSQL           | Database                                 |
| REST APIs            | Service communication                    |
| SOA                  | System architecture                      |

---

---

## Security

The system can implement:

* Authentication
* Authorization
* Secure API communication
* Input validation
* Role-based access where required

Security controls can be implemented at the API/service layer.

---

## Project Flow

```text
1. User logs into the system
            |
            v
2. User enters trip requirements
            |
            v
3. System checks available vehicles
            |
            v
4. Vehicle and trip information is processed
            |
            v
5. AI/ML models predict:
      - Maintenance risk
      - Fuel consumption
      - Travel time
      - Vehicle suitability
            |
            v
6. Route Service calculates suitable routes
            |
            v
7. Dijkstra's Algorithm finds shortest paths
            |
            v
8. AI predictions are combined with route information
            |
            v
9. System recommends suitable vehicle + route
            |
            v
10. Recommendation is displayed on React dashboard
```

---

## Advantages

### Traditional Fleet Management

* Mainly monitoring-based
* Manual vehicle allocation
* Reactive maintenance
* Limited predictive capability
* Separate manual processes
* Problems are often addressed after occurrence

### Proposed System

* AI-assisted fleet management
* Predictive maintenance
* Fuel-consumption prediction
* Intelligent vehicle allocation
* Travel-time prediction
* Route optimization
* API-based independent services
* Modular SOA architecture
* Data-driven decision-making
* Better fleet utilization

---

## Expected Outcomes

The proposed system aims to:

* Reduce fuel consumption
* Reduce unexpected vehicle breakdowns
* Reduce vehicle downtime
* Improve vehicle utilization
* Improve vehicle allocation
* Optimize transportation routes
* Reduce operational costs
* Improve maintenance planning
* Improve fleet reliability
* Support intelligent transportation decisions

---

## Future Enhancements

* Real-time GPS tracking
* Real-time traffic data integration
* IoT sensor integration
* Live vehicle monitoring
* Real-time weather API
* Dynamic route updates
* Driver behavior analysis
* Accident-risk prediction
* Automated maintenance scheduling
* Cloud deployment and scaling
* Mobile application
* Advanced deep-learning models
* Real-time fleet analytics

---

## Conclusion

The AI-Based Smart Transport Fleet Management System combines Service-Oriented Architecture, Artificial Intelligence, Machine Learning, and route optimization to create an intelligent fleet management platform.

Unlike conventional fleet management systems that mainly monitor vehicles and maintain records, the proposed system focuses on prediction, proactive maintenance, intelligent vehicle allocation, fuel optimization, and route decision support.

By using Random Forest, XGBoost, Dijkstra's Algorithm, Google Maps API, Python, FastAPI, React, and PostgreSQL, the system provides a modular and intelligent platform for managing transport fleets.

The overall goal is to create a smarter, more efficient, predictive, reliable, and cost-effective fleet management system.
