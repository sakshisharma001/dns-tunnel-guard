# DNS Tunnel Guard 🛡️
### Autonomous DNS Tunneling & Exfiltration Prevention Console

DNS-Shield ML is a light-weight, high-performance cybersecurity application that detects and blocks DNS tunneling and data exfiltration in real-time. Built with a modern **Vite React** frontend and a robust **FastAPI** backend, it utilizes a custom-trained **Decision Tree Machine Learning Model** to analyze the Shannon Entropy, digit ratio, and string characteristics of active DNS queries to stop unauthorized data egress instantly.

---

## 🛠️ Tech Stack
- **Frontend**: React (Vite), Vanilla CSS (Apple Minimal Light Aesthetic)
- **Backend**: FastAPI, Server-Sent Events (SSE), Scapy (optional live packet capture)
- **Machine Learning**: Scikit-Learn (Decision Tree Classifier), Pandas, NumPy

---

## 🚀 Features
- **Real-Time Traffic Monitor**: Streams incoming DNS query requests and displays classification (PASS vs BLOCKED) instantly.
- **Interactive Leak Simulator**: Lets you inject sensitive payloads (keys, tokens, credentials) to verify machine learning blocking logic in real-time.
- **Explainable AI (XAI)**: Breaks down the decision-making rules, Shannon entropy levels, and features for any selected query.
- **Traffic Ratio Analytics**: Provides clean visual distribution stats on standard versus exfiltration traffic.

---

## 📂 Project Structure
```text
├── backend/
│   ├── app.py                  # FastAPI Application (SSE stream, injection endpoints)
│   ├── train.py                # Model training, feature extraction, entropy math
│   ├── dataset_generator.py    # Mock dataset generator for offline model training
│   ├── dns_dataset.csv         # Standard and malicious training samples
│   └── dns_model.pkl           # Saved Decision Tree classifier weights
├── src/
│   ├── App.jsx                 # Main React component & state integration
│   ├── App.css                 # Clean macOS Segmented/Minimal styles
│   └── index.css               # Core styling tokens & light mode setup
├── requirements.txt            # Python backend dependencies
├── package.json                # Frontend package dependencies
└── README.md                   # Setup & documentation
```

---

## ⚡ Setup & Local Running

### 1. Backend Server (FastAPI)
Navigate to the root directory, configure your virtual environment, and launch FastAPI:

```bash
# 1. Install Python dependencies
pip install -r requirements.txt

# 2. Run the server (default port 8000)
python backend/app.py
```
*Note: If Scapy or WinPcap/Npcap is missing, the backend will gracefully fall back to high-fidelity live simulation mode.*

### 2. Frontend Application (React)
Open a new terminal window in the root directory and run:

```bash
# 1. Install Node dependencies
npm install

# 2. Start the Vite server
npm run dev
```
Open **[http://localhost:5174/](http://localhost:5174/)** (or whichever port Vite displays) in your browser.

---

