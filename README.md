# 🚀 DevOps Intern Assignment: Nginx Reverse Proxy with Docker Compose

This project demonstrates how to set up two backend services — one written in Golang and the other in Python (Flask) — and expose them behind a single Nginx reverse proxy using Docker Compose.

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── nginx
│   ├── Dockerfile
│   └── nginx.conf
├── service_1
│   ├── main.go
│   └── Dockerfile
├── service_2
│   ├── app.py
│   ├── pyproject.toml
│   ├── uv.lock
│   └── Dockerfile
└── README.md
```

---

## ⚙️ Tech Stack

* 🐹 Golang (Service 1)
* 🐍 Python + Flask (Service 2)
* 🌐 Nginx (Reverse Proxy)
* 🐳 Docker & Docker Compose

---

## 🛠️ How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/Sumant08/DPDZero-Assignment.git
cd DPDZero-Assignment
```

### Step 2: Start All Services

```bash
docker-compose up --build
```

This will build and run the following containers:

* `service1` – Golang backend running on port 8001
* `service2` – Flask backend running on port 8002
* `nginx` – Reverse proxy routing all traffic

---

## 🌐 Service Endpoints (via Nginx)

Once containers are running, access the services through the Nginx proxy at:

* [http://localhost:8080/service1/hello](http://localhost:8080/service1/hello)
* [http://localhost:8080/service1/ping](http://localhost:8080/service1/ping)
* [http://localhost:8080/service2/hello](http://localhost:8080/service2/hello)
* [http://localhost:8080/service2/ping](http://localhost:8080/service2/ping)

### Example using `curl`:

```bash
curl http://localhost:8080/service1/hello
curl http://localhost:8080/service2/ping
```

---

## 🦪 Health Checks

Docker Compose includes health checks that ping:

* `service1` on `/ping` (port 8001)
* `service2` on `/ping` (port 8002)

---

## 📝 Notes

* ✅ Ensure Docker and Docker Compose are installed.
* 🌐 Nginx uses **path-based routing** to direct traffic to the correct service.
* 📄 Nginx logs all requests with timestamp and path.

---

## 👨‍💼 Author

**Sumant Dharmatti**
MCA Student, Gogte Institute of Technology
📧 [sumantdharmatti21@gmail.com](mailto:sumantdharmatti21@gmail.com)
