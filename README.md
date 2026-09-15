# 🚀 Alô Mundo Java + Docker

Projeto desenvolvido para demonstrar a criação, compilação e execução de uma aplicação Java utilizando Maven e Docker.

## 📋 Sobre o projeto

Este projeto consiste em uma aplicação Java simples que exibe uma mensagem no terminal.

O objetivo é praticar:

- Desenvolvimento de aplicações Java;
- Gerenciamento de projeto com Maven;
- Geração de arquivo `.jar`;
- Criação de uma imagem Docker;
- Execução de uma aplicação Java dentro de um container;
- Publicação da imagem no Docker Hub.

## 🛠️ Tecnologias utilizadas

- ☕ Java 8
- 📦 Maven 3.9+
- 🐳 Docker
- 💻 Apache NetBeans

## 📁 Estrutura do projeto

```text
alomundo_java_docker/
├── Dockerfile
├── pom.xml
├── src/
│   └── main/
│       └── java/
│           └── ...
└── target/
    └── aluno_java_docker-0.0.1.jar
```

## ⚙️ Pré-requisitos

É necessário ter instalado:

- Java JDK 8 ou compatível;
- Maven;
- Docker.

Para verificar:

```bash
java -version
mvn -version
docker -v
```

## 📦 Compilando o projeto

Entre no diretório do projeto:

```bash
cd ~/NetBeansProjects/alomundo_java_docker
```

Execute:

```bash
mvn clean package
```

O arquivo `.jar` será gerado na pasta `target/`:

```text
aluno_java_docker-0.0.1.jar
```

## ▶️ Executando com Java

```bash
java -jar target/aluno_java_docker-0.0.1.jar
```

## 🐳 Docker

O projeto utiliza o Docker para empacotar e executar a aplicação Java em um container.

### Dockerfile

```dockerfile
FROM eclipse-temurin:8-jre

WORKDIR /app

COPY ./target/aluno_java_docker-0.0.1.jar .

ENTRYPOINT ["java", "-jar", "aluno_java_docker-0.0.1.jar"]
```

## 🔨 Criando a imagem Docker

Primeiro, gere o `.jar`:

```bash
mvn clean package
```

Depois, crie a imagem:

```bash
docker build -t alomundo_java_docker .
```

Verifique a imagem:

```bash
docker images
```

## ▶️ Executando o container

```bash
docker run --rm alomundo_java_docker
```

## ☁️ Publicando no Docker Hub

Faça login:

```bash
docker login
```

Crie a tag:

```bash
docker tag alomundo_java_docker:latest hbentor/alomundo_java_docker:0.0.1
```

Publique a imagem:

```bash
docker push hbentor/alomundo_java_docker:0.0.1
```

Repositório Docker Hub:

**hbentor/alomundo_java_docker**

## 🖥️ Compatibilidade

O projeto foi desenvolvido e testado em um MacBook com processador Apple Silicon (M1).

A imagem base utilizada é:

```text
eclipse-temurin:8-jre
```

## 🎯 Fluxo do projeto

```text
Código Java
     ↓
   Maven
     ↓
Arquivo .jar
     ↓
 Dockerfile
     ↓
Imagem Docker
     ↓
Container
     ↓
Docker Hub
```

## 👨‍💻 Autor

**Bento Reis**

Projeto desenvolvido para fins acadêmicos.

---

⭐ Projeto desenvolvido como prática de Java, Maven e Docker.
