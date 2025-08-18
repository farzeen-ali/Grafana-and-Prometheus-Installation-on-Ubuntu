# 🚀 Grafana + Prometheus Installation & Setup on Ubuntu (Beginner-Friendly Guide)

Welcome to this **step-by-step beginner-friendly guide** on how to install and set up **Grafana + Prometheus** on **Ubuntu Linux**.  
If you are starting your journey in **DevOps, Monitoring, or Cloud Engineering**, then this guide is for you!  

With **Grafana** you can visualize metrics beautifully, and with **Prometheus** you can collect & store them efficiently. Together, they form the **ultimate monitoring stack**. 🎯

---

## 📌 Table of Contents
1. [What is Grafana?](#-what-is-grafana)
2. [What is Prometheus?](#-what-is-prometheus)
3. [Prerequisites](#-prerequisites)
4. [Install Grafana on Ubuntu](#-install-grafana-on-ubuntu)
5. [Install Prometheus on Ubuntu](#-install-prometheus-on-ubuntu)
6. [Verify Installation](#-verify-installation)
7. [Access Web Interfaces](#-access-web-interfaces)
8. [Next Steps](#-next-steps)

---

## 🌟 What is Grafana?
**Grafana** is an **open-source visualization tool** that helps you monitor and analyze metrics from different sources (like Prometheus, Loki, MySQL, and more).  
- Create **dashboards**  
- Add **alerts**  
- Visualize data in **real-time**

---

## 🌟 What is Prometheus?
**Prometheus** is an **open-source monitoring & alerting system**.  
It collects metrics, stores them in a **time-series database**, and provides a query language (**PromQL**) to analyze them.

---

## ✅ Prerequisites
- Ubuntu Linux (20.04 or later recommended) 🐧  
- A non-root user with **sudo privileges**  
- Internet connectivity 🌍  

---

## ⚡ Install Grafana on Ubuntu

### 1️⃣ Update system packages and install dependencies
```bash
sudo apt update
sudo apt install -y apt-transport-https software-properties-common wget
```

### 2️⃣ Add Grafana GPG key
```bash
sudo wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key
```

### 3️⃣ Add Grafana APT repository
```bash
echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

### 4️⃣ Update package lists and install Grafana
```bash
sudo apt update
sudo apt install grafana -y
```

### 5️⃣ Start and enable Grafana service
```bash
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

### 6️⃣ Verify Grafana status
```bash
sudo systemctl status grafana-server
```
✅ It should show **active (running)**

---

## ⚡ Install Prometheus on Ubuntu

### 1️⃣ Update system
```bash
sudo apt update
sudo apt upgrade -y
```

### 2️⃣ Install Prometheus and Node Exporter
```bash
sudo apt install prometheus prometheus-node-exporter -y
```

### 3️⃣ (Optional) Configure Prometheus
Edit the main config file `/etc/prometheus/prometheus.yml`

```bash
sudo nano /etc/prometheus/prometheus.yml
```
➡️ Here you can set scrape targets, alerting rules, jobs, etc.

### 4️⃣ Start and enable Prometheus services
```bash
sudo systemctl enable --now prometheus prometheus-node-exporter
```

---

## 🌐 Access Web Interfaces
- **Grafana**: 👉 [http://localhost:3000](http://localhost:3000)  
  Default username: `admin`  
  Default password: `admin` (you will be asked to change it)

- **Prometheus**: 👉 [http://localhost:9090](http://localhost:9090)  

---

## 🎯 Verify Installation

### Check if Grafana is running:
```bash
systemctl status grafana-server
```

### Check if Prometheus is running:
```bash
systemctl status prometheus
```

---

## 🚀 Next Steps
- Add **Prometheus as a Data Source** in Grafana  
- Create your **first dashboard** in Grafana  
- Set up **alerts & notifications**  

---

## 💡 Why Use Grafana + Prometheus?
- 📊 Real-time monitoring  
- ⚡ Lightweight and fast  
- 🔥 Perfect for DevOps Engineers, SREs, and Cloud Professionals  
- 🎯 Industry-standard monitoring stack  

---

## 🙌 Conclusion
You have successfully installed and set up **Grafana + Prometheus** on Ubuntu! 🎉  
Now you are ready to create beautiful dashboards, monitor systems, and become a **DevOps Monitoring Expert**. 🚀  

⭐ If you found this guide helpful, don’t forget to **star this repo** and share it with others!  
Happy Monitoring with Grafana + Prometheus! ❤️
