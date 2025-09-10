Perfect 👍 Thanks for the details. I’ll draft a **README.md** for your first project (`project-01` in `DockerPractice`) — clear, short, but with **all the essential commands and explanations**.

Here’s the file:

````markdown
# Project 01 – Static Website with Apache HTTP Server

This project demonstrates how to containerize a simple static website (4–5 HTML pages) using **Apache HTTP Server** with Docker.

## Dockerfile
```dockerfile
FROM httpd:2.4.54-alpine
COPY . /usr/local/apache2/htdocs/
````

---

## Build the Docker Image

Use the following command to build the image.
Make sure to replace **your-dockerhub-username** with your actual DockerHub username.

```bash
docker build -t your-dockerhub-username/dockerpractice-project01:1.0 .
```

---

## Run the Container

Run the container by mapping any **external port** on your machine/VM to the **internal port 80** (Apache default).

Example (using port `8080` on the host):

```bash
docker run -d -p 8080:80 --name static-site your-dockerhub-username/dockerpractice-project01:1.0
```

* `8080:80` → Maps **host port 8080** to **container port 80**
* You can replace `8080` with any free port (e.g., 3000, 5000, 9000, etc.)

---

## Accessing the Website

* **On Local Machine:**
  Open browser → `http://localhost:8080`

* **On EC2 / VM:**
  Open browser → `http://<your-public-ip>:8080`
  (Make sure the security group / firewall allows inbound traffic on the chosen port)

---

## Push to DockerHub

After building and testing the image, push it to DockerHub:

```bash
docker login
docker push your-dockerhub-username/dockerpractice-project01:1.0
```

---

✅ You now have a Dockerized static website running with Apache.
You can repeat the same pattern for future projects with different ports and configurations.

```

---

Do you want me to also **add a section about stopping/removing containers** (for cleanup), or keep it focused only on build/run/push?
```

