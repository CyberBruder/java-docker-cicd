# ☕ Java Minimalist API + Docker & CI/CD Pipeline

<div align="right">
  <a href="README.md">🇧🇷 Leia em Português</a>
</div>

<br>

This is a practical project developed to demonstrate and consolidate core concepts of **DevOps, Containerization (Docker), and Continuous Integration/Continuous Delivery (CI/CD)**. 

The application consists of a minimalist web server written in native Java that, upon receiving a commit, triggers an automated pipeline in GitHub Actions to compile, build a Docker image, and publish it automatically to Docker Hub.

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
```

## How to Run the Project Locally

If you want to clone this repository and run the project on your machine:

1. Make sure Docker is installed on your system.

2. From the project root, build the Docker image locally:

   ```bash
   docker build -t meu-app-java .
   ```

3. Start the container, mapping the ports:

   ```bash
   docker run -p 8080:8080 meu-app-java
   ```

4. Open your browser and go to: http://localhost:8080

## The CI/CD Pipeline (GitHub Actions)

The automation pipeline was set up to eliminate any manual deployment work. It works like this:

1. **Trigger:** The developer runs `git push` on the main branch (`main`).
2. **Environment:** GitHub Actions starts an isolated virtual machine with `ubuntu-latest`.
3. **Authentication:** The pipeline logs in to Docker Hub using secure credentials (Repository Secrets).
4. **Build & Push:** The Dockerfile is read, the Java code is compiled inside the container, and the final image is pushed to Docker Hub with two tags:

   * `latest` (for the most recent version).
   * A tag with the SHA (unique identifier) of that specific commit, for history.

## Running from the Cloud (Portability)

Thanks to Docker Hub, you don't need to clone this code to run the application. On any server or computer in the world that has Docker installed, just run:

```bash
docker run -d -p 8080:8080 --name meu-servidor-java JustBruder/my-docker:latest
```

* View the app logs:

  ```bash
  docker logs meu-servidor-java
  ```

* Stop the app:

  ```bash
  docker stop meu-servidor-java
  ```

---

### 💻 Contate-me / Let's Connect

<p align="center">
  <a href="https://www.linkedin.com/in/ingrid-bruder" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-C71585?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:ibruder83@gmail.com">
    <img src="https://img.shields.io/badge/Email-C71585?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.instagram.com/Cyber.Bruder" target="_blank">
    <img src="https://img.shields.io/badge/Instagram-C71585?style=for-the-badge&logo=instagram&logoColor=white" />
  </a>
  <a href="https://www.tiktok.com/@Cyber.Bruder" target="_blank">
    <img src="https://img.shields.io/badge/TikTok-C71585?style=for-the-badge&logo=tiktok&logoColor=white" />
  </a>
</p>

<div align="center">
  <sub>Developed by Bruder ✨</sub>
</div>
<div align="center">
  <sub>🌷🐱 Clean code and MEOW </sub>
</div>
