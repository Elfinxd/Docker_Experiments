# 🚀 Docker Network Experiment

This repository demonstrates how to create and test a custom Docker network (net-bridge) with multiple containers for seamless inter-container communication. The experiment showcases how containers can communicate within a user-defined bridge network.

---

## 🛠 Experiment Overview
Docker provides powerful networking capabilities, allowing containers to communicate securely. This experiment involves:
1. *Creating a custom bridge network* for isolated communication.
2. *Running multiple containers* within the network.
3. *Inspecting and verifying connectivity* between containers.
4. *Testing inter-container communication* using ping and name resolution.

---

## 🔧 Experiment Setup


## 1️⃣ Create a Custom Docker Network
```sh
docker network create --driver bridge --subnet 172.20.0.0/16 --ip-range 172.20.240.0/20 net-bridge
```

## 2️⃣ Run Containers and Attach to the Network

### 🗄 Run Database Container
```sh
docker run -itd --net=net-bridge --name=cont_database redis
```

### 🖥 Run Server Container
```sh
docker run -dit --name server-A --network net-bridge busybox
```

## 3️⃣ Inspect Network and Containers

### 🔍 Check Network Details
```sh
docker network inspect net-bridge
```

### 🔎 Check Container Details
```sh
docker inspect cont_database
```

### 🌐 Get Container IP Address
```sh
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' cont_database
```

## 4️⃣ Testing Connectivity

### 🖥 Access Container Shell
```sh
docker exec -it server-A sh
```

### 🔗 Ping Another Container by IP
```sh
ping 172.20.240.1  # Replace with actual container IP
```

### 🔗 Ping Another Container by Name
```sh
ping cont_database
```

---

## 📌 Observations
✅ The custom bridge network allows direct communication between containers.

✅ Containers can communicate using assigned IP addresses.

✅ Name resolution may not always work with BusyBox due to its minimal nature.

✅ Using `docker inspect` helps retrieve network details and assigned IPs.

---

## 🏁 Conclusion
This experiment highlights Docker's networking capabilities, demonstrating inter-container communication via a custom bridge network. Understanding Docker networking is crucial for deploying microservices and containerized applications efficiently.

## 📸 Docker Network Connectivity Test
Here is a screenshot of the experiment in action:

![Docker Ping Test]![Image](https://github.com/user-attachments/assets/24a3d341-554e-4ac8-839b-53ad3d58a758)


✅ The above image shows successful container communication via ping.
---

## 📢 Author
👤 [Shivansh Dixit](https://github.com/Elfinxd)
