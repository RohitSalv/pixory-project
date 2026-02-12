# Pixory – AI Image Cloud Backend

> **Server-side orchestrator for the Pixory Ecosystem.**  
> Built with Spring Boot, Google Gemini AI, and Cloudinary.

Pixory is a sophisticated, AI-enhanced backend service designed to handle secure image ingestion, cloud storage orchestration, and natural language metadata analysis. It serves as the "brain" of the ecosystem, transforming binary image data into searchable intelligence.

---

## 🚀 Key Engineering Features

- **Asynchronous AI Pipeline**: Leverages Spring's `@Async` task execution to process Google Gemini AI analysis without blocking the user's upload request.
- **Intelligent Metadata Generation**: Automatically extracts context, descriptions, and tags from visual data using state-of-the-art LLMs.
- **Secure Auth Architecture**: Implements mandatory JWT-based security with short-lived access tokens and high-security refresh token rotation.
- **Cloud-Native Storage**: Distributed image management via Cloudinary CDN for global performance and optimized transformations.
- **Event-Driven Emails**: Transactional email workflows for account security and user engagement (Welcome/Recovery).

---

## 🏗️ Technical Architecture

The server is architected as a modular RESTful service following industry best practices:

1. **Presentation Layer**: Spring MVC Controllers managing REST endpoints and API documentation.
2. **Security Layer**: Custom JWT Filters and Spring Security 6 configurations.
3. **Service Layer**: Business logic for image processing, AI prompting, and transactional management.
4. **Data Layer**: Spring Data JPA with Hibernate for reliable relational persistence.
5. **Integration Layer**: Secure connectors for Google Gemini, Cloudinary, and SMTP providers.

---

## 🔧 Technology Stack

- **Framework**: Spring Boot 3.2.2
- **Language**: Java 17 (LTS)
- **AI Core**: Google Gemini API (gemini-2.5-flash)
- **Security**: Spring Security 6 / JJWT (0.12.5)
- **Persistence**: MySQL 8+ / Hibernate / JPA
- **Storage**: Cloudinary SDK
- **Mailing**: Spring Boot Starter Mail
- **Build Tool**: Apache Maven

---

## 🚀 Getting Started

This directory contains the backend service. To run it as part of the monorepo:

### Prerequisites
- **JDK 17** (Amazon Corretto or OpenJDK recommended)
- **Maven 3.8+**
- **MySQL Instance** (running on port 3306)

### Setup & Run
1.  **Configure Environment**:
    Inside this folder, create a `.env` file (refer to `env.example`):
    ```env
    DB_URL=jdbc:mysql://localhost:3306/GallaryV1?createDatabaseIfNotExist=true
    DB_USER=root
    DB_PASS=your_password
    GEMINI_API_KEY=your_google_ai_key
    CLOUDINARY_CLOUD_NAME=your_name
    CLOUDINARY_API_KEY=your_key
    CLOUDINARY_API_SECRET=your_secret
    JWT_SECRET=your_long_random_string
    ```
2.  **Build Project**:
    ```bash
    mvn clean install
    ```
3.  **Launch Application**:
    ```bash
    mvn spring-boot:run
    ```

---

## 🔑 Core API Endpoints

### **Authentication & Account**
- `POST /api/auth/register` - User registration + Welcome Email.
- `POST /api/auth/login` - Identity verification + Access/Refresh Token issuance.
- `POST /api/auth/refresh-token` - Secure token renewal flow.
- `POST /api/auth/forgot-password` - Trigger password recovery workflow.

### **Media & AI Operations**
- `POST /api/v1/files/upload` - Secure image upload + Async AI trigger.
- `GET /api/v1/files/me` - Retrieve protected gallery metadata.
- `GET /api/v1/files/search` - Query gallery using natural language tags.
- `DELETE /api/v1/files/{id}` - Synchronized deletion from DB and CDN.

---

## 🏗 Engineering Decisions

### **Why Asynchronous Analysis?**
AI analysis is a heavy operation (3-10s). By using `@Async`, we return an immediate response to the user with an "ANALYSIS_PENDING" status. This keeps the frontend responsive and allows the backend to scale AI tasks independently.

### **Why JWT Secret Management?**
We use HS256 signing for tokens. All secrets are managed via injected environment variables, ensuring that sensitive credentials never enter the source control history.

---

## 🔗 Related Documentation
👉 [View Main Project Hub](../README.md)  
👉 [View Frontend Client](../client/README.md)

---
<p align="center">
  Engineered for Intelligence, Stability, and Scale.
</p>
