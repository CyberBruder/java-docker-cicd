# ☕ Java Minimalist API + Docker & CI/CD Pipeline

This is a practical project developed to demonstrate and consolidate core concepts of **DevOps, Containerization (Docker), and Continuous Integration/Continuous Delivery (CI/CD)**. 

The application consists of a minimalist web server written in native Java that, upon receiving a commit, triggers an automated pipeline in GitHub Actions to compile, build a Docker image, and publish it automatically to Docker Hub.

<hr />

🇧🇷 [Leia em Português](README.pt.md)

<hr />

## Technologies Used
- **Java 17 (Native):** To create the HTTP server without external dependencies.

- **Docker:** To isolate and package the application, ensuring portability.

- **GitHub Actions:** CI/CD tool for automating the build and deploy workflow.

- **Docker Hub:** As a public registry to store ready-to-use container images.

- **Linux Mint & VSCode:** Local development environment.


## Repository Structure
```text
meu-app-docker/
├── .github/
│   └── workflows/
│       └── docker-publish.yml  # CI/CD pipeline configuration
├── src/
│   └── Main.java               # Java server source code
└── Dockerfile                  # Docker image build recipe
