
````markdown
# Project 01 – Static Website with Apache HTTP Server

This project demonstrates how to containerize a simple static website (4–5 HTML pages) using **Apache HTTP Server** with Docker.

---

## Build the Docker Image

Use the following command to build the image.  
Make sure to replace **your-dockerhub-username** with your actual DockerHub username.

```bash
docker build -t your-dockerhub-username/dockerpractice-project01:1.0 .
````

---

## Run the Container

Run the container by mapping **any external port** on your machine/VM to the **internal port 80** (Apache default).

Example (using external port `8080`):

```bash
docker run -d -p 8080:80 --name static-site your-dockerhub-username/dockerpractice-project01:1.0
```

### Important Notes about Ports

* Internal port is always **80** (required by Apache/HTTPD inside container).
* External port can be **any free port** (e.g., 3000, 4000, 5000).
* Format: `external_port:80`

---

## Accessing the Website

* **On Local Machine:**
  Open browser → `http://localhost:8080`

* **On EC2 / VM:**
  Open browser → `http://<your-public-ip>:8080`
  ⚠️ Make sure your **security group / firewall inbound rule** allows the chosen external port (e.g., 8080).

---

## Push to DockerHub

After building and testing the image, push it to DockerHub:

```bash
docker login
docker push your-dockerhub-username/dockerpractice-project01:1.0
```

---

## Stop and Remove Container (Cleanup)

To stop the running container:

```bash
docker stop static-site
```

To remove it:

```bash
docker rm static-site
```

```

---

