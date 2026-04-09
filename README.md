# AGMS Centralized Configuration Repository 🌿⚙️

This repository serves as the centralized configuration store for the **Automated Greenhouse Management System (AGMS)** microservices architecture. It uses **Spring Cloud Config Server** to manage and distribute configuration properties across all services in the environment.

## 📌 Overview

Externalizing configuration allows for better management of service properties without the need to rebuild or restart services for every minor change. This repository holds service-specific settings for various environments.

## 📂 Configuration Structure

The repository contains YAML configuration files for the following services:

- **Infrastructure Services:**
  - `discovery-server.yml`: Eureka server settings.
  - `api-gateway.yml`: Routing and security filter configurations.
  - `identity-service.yml`: Authentication and JWT settings.
  
- **Domain Services:**
  - `crop-service.yml`: Crop management properties.
  - `zone-service.yml`: Greenhouse zone definitions.
  - `sensor-service.yml`: Telemetry data fetching and scheduling.
  - `automation-service.yml`: Rule engine and device control logic.

## 🛠️ How to Use

1. **Connect to Config Server:**
   The `config-server` must point to this repository's URI in its `application.yml`:
   ```yaml
   spring:
     cloud:
       config:
         server:
           git:
             uri: [https://github.com/Visun517/AGMS-config-repo.git](https://github.com/Visun517/AGMS-config-repo.git)
             clone-on-start: true
