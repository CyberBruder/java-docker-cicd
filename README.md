# ☕ Java Minimalist API + Docker & CI/CD Pipeline

Este é um projeto prático desenvolvido para demonstrar e consolidar conceitos fundamentais de **DevOps, Containerização (Docker) e Integração/Entrega Contínua (CI/CD)**. 

A aplicação consiste em um servidor web minimalista escrito em Java nativo que, ao receber um commit, aciona uma esteira automatizada no GitHub Actions para compilar, gerar uma imagem Docker e publicá-la automaticamente no Docker Hub.

<hr />

🇺🇸 [Read in English](README.md)

<hr />

## Tecnologias Utilizadas
* **Java 17 (Nativo):** Para a criação do servidor HTTP sem dependências externas.
* **Docker:** Para isolar e empacotar a aplicação garantindo portabilidade.
* **GitHub Actions:** Ferramenta de CI/CD para automação do fluxo de build e deploy.
* **Docker Hub:** Como registro público para armazenar a imagem prontas do container.
* **Linux Mint & VSCode:** Ambiente de desenvolvimento local.

## Estrutura do Repositório
```text
meu-app-docker/
├── .github/
│   └── workflows/
│       └── docker-publish.yml  # Configuração da esteira de CI/CD
├── src/
│   └── Main.java               # Código-fonte do servidor Java
└── Dockerfile                  # Receita de construção da imagem Docker
```

## Como Rodar o Projeto Localmente?
Se você quiser clonar este repositório e rodar o projeto na sua máquina:
1. Certifique-se de ter o Docker instalado no seu sistema.
2. Na raiz do projeto, construa a imagem Docker localmente:
     ```text docker build -t meu-app-java . ```
3. Inicie o container conectando as portas do sistema:
     ```text docker run -p 8080:8080 meu-app-java```
4. Abra o navegador e acesse: http://localhost:8080 

## O Pipeline de CI/CD (GitHub Actions)
A esteira de automação foi configurada para eliminar qualquer trabalho manual de deploy. O fluxo funciona da seguinte forma:
1. Gatilho: O desenvolvedor faz um git push na branch principal (main).
2. Ambiente: O GitHub Actions inicializa uma máquina virtual isolada com ubuntu-latest.
3. Autenticação: A esteira faz login no Docker Hub usando chaves seguras (Repository Secrets).
4. Build & Push: O Dockerfile é lido, o código Java é compilado dentro do container e a imagem final é enviada para o Docker Hub com duas tags:
- latest (para a versão mais recente).
- Uma tag com a SHA (identificador único) daquele commit específico para histórico.

## Executando a partir da Nuvem (Portabilidade)
Graças ao Docker Hub, você não precisa clonar este código para rodar a aplicação. Em qualquer servidor ou computador do mundo que tenha o Docker instalado, basta executar o comando: 
```text docker run -d -p 8080:8080 --name meu-servidor-java JustBruder/my-docker:latest ```
- Ver logs do app: docker logs meu-servidor-java
- Parar o app: docker stop meu-servidor-java

---

<div align="center">

### 💻 Contate-me / Let's Connect

<p align="center">
  <a href="https://www.linkedin.com/in/ingrid-bruder" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-C71585?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:ibruder83@gmail.com">
    <img src="https://img.shields.io/badge/Email-C71585?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>
</div>

<div align="center">
  <sub>Desenvolvido por JustBruder ✨</sub>
</div>
<div align="center">
  <sub>🌷 Security by Design </sub>
</div>
