Here's a README for the **Stock Photo Generator** project with a **Spring Boot** and **Spring AI** backend and a **React** frontend. Following the README, there’s also a concise description for adding to your resume.

# Stock Photo Generator

This project is a **Stock Photo Generator** that uses **Spring Boot** and **Spring AI** to generate high-quality, AI-driven stock photos based on user prompts. The frontend, built with **React**, allows users to input text descriptions and view or download the generated images.

## Table of Contents

- [Project Structure](#project-structure)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Architecture Overview](#architecture-overview)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)

## Project Structure

```
StockPhotoGenerator/
├── backend/                    # Spring Boot + Spring AI backend
│   ├── src/
│   ├── pom.xml
│   └── Dockerfile
├── frontend/                   # React frontend
│   ├── src/
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

- **Backend**: Contains the Spring Boot application and Spring AI integration for image generation.
- **Frontend**: A React application that provides an interface for users to input prompts and view generated images.

## Features

- **Text-to-Image Generation**: Users input textual descriptions, and the app generates relevant stock images.
- **Responsive Frontend**: A React frontend that enables users to interact with the API for generating and displaying images.
- **RESTful API**: A backend API that handles image generation requests and serves images.
- **Caching**: Redis caching to optimize response times and reduce AI processing for repeated queries.
- **Dockerized Deployment**: Docker configuration for both frontend and backend to ensure smooth deployment and scalability.

## Technologies Used

- **Spring Boot**: Backend framework for RESTful API development.
- **Spring AI**: Converts text prompts into images.
- **React**: Frontend library for building a responsive and dynamic user interface.
- **Docker**: Containerization for consistent development and production environments.
- **Redis**: Caching layer for enhanced performance.
- **MySQL/PostgreSQL** (or any relational database): To store generated image metadata and user history.

## Architecture Overview

The project follows a client-server architecture:

- **Spring Boot API**: Processes requests from the frontend, integrates with Spring AI, and generates images based on text prompts.
- **React Frontend**: User-facing application for prompt submission and image display.
- **Redis Cache**: Caches frequently requested images to reduce processing time.
- **Database**: Stores image metadata, user history, and other persistent data.

## Setup and Installation

### Prerequisites

- Java 17+
- Node.js and npm (for React frontend)
- Docker and Docker Compose

### Clone the Repository

```bash
git clone git@github.com:ThePygmalion/Stock-Photo-Generator.git
cd stock-photo-generator
```

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Update `application.properties` with your database configuration.
3. Build and run the backend:
   ```bash
   ./mvnw clean install
   ./mvnw spring-boot:run
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the React application:
   ```bash
   npm start
   ```
   The frontend should now be accessible at `http://localhost:3000`.

### Running with Docker Compose

To run both the frontend and backend with Docker Compose:

```bash
docker-compose up -d
```

## Usage

1. Visit `http://localhost:3000` to access the React frontend.
2. Enter a text prompt to generate an image.
3. View, download, or save generated images through the UI.

## API Endpoints

| Endpoint           | Method | Description                                   |
|--------------------|--------|-----------------------------------------------|
| `/api/generate`    | POST   | Accepts a text prompt to generate an image    |
| `/api/images/{id}` | GET    | Retrieves a generated image by its ID         |
| `/api/history`     | GET    | Returns the user's history of generated images|

