# Pixory – AI Private Photo Cloud

<p align="center">
  <img src="./docs/Docs/logo.png.png" alt="Pixory Logo" width="200">
</p>

Pixory is a sophisticated, AI-enhanced image management platform designed to automate the organization of personal media. By combining a modern, responsive frontend with a robust Spring Boot backend, Pixory automatically enriches every upload with descriptive metadata and searchable tags using the **Google Gemini AI** pipeline.

## 🚀 Key Features

- **Intelligence-First Gallery**: Automatically generates natural language descriptions and category tags for every image uploaded.
- **Asynchronous Processing**: High-performance backend architecture that processes heavy AI tasks in the background, keeping the user interface snappy.
- **Secure Cloud Storage**: Seamless integration with Cloudinary for global CDN delivery and secure binary storage.
- **Modern Authentication**: Full implementation of JWT (JSON Web Tokens) with a secure Refresh Token rotation flow.
- **Responsive UX**: Designed with Angular and Tailwind CSS for a fluid experience across desktop, tablet, and mobile devices.
- **Transactional Notifications**: Automated email workflows for user welcoming and secure password recovery.

---

## 🏗️ Architecture

Pixory is architected as a decoupled system to reflect industrial standards for scalability and maintainability.

```text
Pixory (Monorepo)
│
├── 📂 server/ ────────► [Spring Boot + Gemini AI Pipeline]
│
└── 📂 client/ ────────► [Angular + Tailwind CSS + Lucide]
```

### Core Components
1. **Frontend (Angular)**: The presentation layer, managing state and providing a "calm" user experience.
2. **REST API (Spring Boot)**: The orchestrator, handling security, business logic, and third-party integrations.
3. **AI Engine (Google Gemini)**: The "brain" that analyzes visual content into searchable data.
4. **Cloud Infrastructure (Cloudinary)**: Handles image transformations and high-availability storage.
5. **Data Persistence (MySQL)**: Stores relational data, user profiles, and AI-generated metadata.

---

## 🔧 Technical Stack

### **Backend**
- **Framework**: Spring Boot 3.2.2
- **Language**: Java 17
- **AI Engine**: Google Gemini (gemini-2.5-flash)
- **Security**: Spring Security + JWT (Short/Long lived tokens)
- **Cloud**: Cloudinary SDK
- **Database**: Hibernate / Spring Data JPA / MySQL
- **Email**: JavaMailSender (SMTP)
- **Utilities**: Lombok, Thumbnailator (Async image resizing)

### **Frontend**
- **Framework**: Angular 20+
- **Styling**: Tailwind CSS v4 (Modern JIT Engine)
- **State/Async**: RxJS & Angular Signals
- **Icons**: Lucide Angular
- **Animations**: Browser Animations Module

---

## 📂 Project Structure

| Folder | Description |
| :--- | :--- |
| **[/server](./server)** | The AI-powered Spring Boot API. |
| **[/client](./client)** | The sleek Angular gallery interface. |
| **[/docs](./docs)** | Architecture diagrams and project journey documentation. |

---

## 🎯 Why Pixory?

Pixory was built to demonstrate the convergence of traditional Full-Stack development and the modern AI landscape. It solves the "manual tagging" problem by shifting the cognitive load from the user to the machine, ensuring that a gallery of 1,000 images is just as searchable as a gallery of 10.

### Major Learning Outcomes:
- Implementing **Asynchronous Event-Driven AI Analysis**.
- Managing secure **JWT Refresh Token flows** in a cross-origin environment.
- Optimizing **Image Ingestion Pipelines** (Resize -> Upload -> Analyze -> Persist).
- Writing clean, maintainable, and decoupled codebases.

---

## 📄 License & Usage

This project is open for investigation and learning. It serves as a comprehensive portfolio piece demonstrating modern system design.

---
<p align="center">
  Made with ☕ and Code by Rohit Salve
</p>
