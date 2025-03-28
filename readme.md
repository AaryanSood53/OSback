# Banker's Algorithm API - BackendForDeadlock

This repository contains the backend API for the **Deadlock Simulation** web app, implementing the **Banker's Algorithm** for resource allocation and deadlock detection.

## 🔗 Live API  
The backend is deployed and accessible at:  
[https://backfordeadlock.vercel.app/api/bankers](https://backfordeadlock.vercel.app/api/bankers)  

## 📌 Features  
- Implements **Banker’s Algorithm** for deadlock detection.  
- Provides a **REST API** to check system safety and process execution sequence.  
- Handles invalid inputs and detects possible **deadlocks**.  
- Built with **Node.js** and **Express.js**.  

## 🚀 How to Use  

### **1️⃣ API Endpoint**  
#### `POST /api/bankers`  
This endpoint runs the Banker's Algorithm and returns whether the system is in a **safe state** along with execution steps.  

### **2️⃣ Request Body (JSON format)**
```json
{
  "allocation": [[0, 1, 0], [2, 0, 0], [3, 0, 2], [2, 1, 1], [0, 0, 2]],
  "maxMatrix": [[7, 5, 3], [3, 2, 2], [9, 0, 2], [2, 2, 2], [4, 3, 3]],
  "available": [3, 3, 2],
  "processCount": 5,
  "resourceCount": 3
}
```

### **3️⃣ Response**
#### ✅ Safe State Example  
```json
{
  "isSafe": true,
  "safeSequence": [1, 3, 4, 0, 2],
  "needMatrix": [[7, 4, 3], [1, 2, 2], [6, 0, 0], [0, 1, 1], [4, 3, 1]],
  "steps": ["Step-by-step execution details..."]
}
```

#### ❌ Deadlock Example  
```json
{
  "isSafe": false,
  "needMatrix": [[7, 4, 3], [1, 2, 2], [6, 0, 0], [0, 1, 1], [4, 3, 1]],
  "steps": ["Deadlock detected! No process can proceed."]
}
```

## 🛠️ Local Setup  

### 1️⃣ Clone the Repository  
```sh
git clone https://github.com/Akhand0ps/BackendForDeadlock.git
cd BackendForDeadlock
```

### 2️⃣ Install Dependencies  
```sh
npm install
```

### 3️⃣ Run Locally  
```sh
npm start
```
The server will start at `http://localhost:3000`.

## 📝 License  
This project is licensed under the **MIT License**.  

---

### 🌐 Related Repositories  
🔗 **Frontend** (Deadlock Simulation Web App):  
[https://github.com/Akhand0ps/DEADLOCK](https://github.com/Akhand0ps/DEADLOCK)  
Live Demo: [https://deadlock-mu.vercel.app/index.html](https://deadlock-mu.vercel.app/index.html)  

