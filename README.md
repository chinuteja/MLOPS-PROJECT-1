
# 🚗 Vehicle Insurance MLOps Project  
### End-to-End Machine Learning Pipeline with AWS, Docker, CI/CD & MongoDB

---

## 📌 Project Objective

This project is a **complete production-grade MLOps system** designed to demonstrate how real-world ML systems are built, trained, versioned, deployed, and monitored.

It covers:
- Data ingestion from MongoDB
- Data validation & transformation
- Model training, evaluation & versioning
- Model registry using AWS S3
- CI/CD automation using GitHub Actions
- Dockerized deployment on AWS EC2
- REST API for prediction & training

This repository is structured to **attract recruiters and hiring managers** by showcasing industry-standard practices.

---

## 🧱 Step 1: Project Template Creation

Run the template file to generate the project structure:

```bash
python template.py
```

This ensures:
- Clean modular architecture
- Separation of concerns
- Scalable ML pipeline design

---

## 📦 Step 2: Local Package Configuration

To enable importing local modules:
- Configure `setup.py`
- Configure `pyproject.toml`

These files allow your project to behave like an installable Python package.

📄 Refer to `projectflow.txt` for a detailed explanation.

---

## 🐍 Step 3: Virtual Environment Setup

Create and activate a Conda environment:

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Verify installations:

```bash
pip list
```

---

## 🌐 Step 4: MongoDB Atlas Setup

1. Sign up on MongoDB Atlas
2. Create a new project
3. Create an **M0 free cluster**
4. Create a database user (username & password)
5. Add IP access:
   ```
   0.0.0.0/0
   ```
6. Get connection string:
   - Driver: Python
   - Version: 3.6+
7. Replace password and save the URL

---

## 📓 Step 5: MongoDB Notebook Demo

1. Create `notebook/` directory
2. Create `mongoDB_demo.ipynb`
3. Select kernel → `vehicle`
4. Load dataset into notebook
5. Push data to MongoDB Atlas
6. Verify via **Browse Collections**

---

## 🧾 Step 6: Logging & Exception Handling

- Custom logger module for traceability
- Centralized exception handling
- Tested using `demo.py`

This improves debugging and production monitoring.

---

## 🔄 Step 7: Data Ingestion Pipeline

Before implementation:
- Declare constants in `constants/__init__.py`
- Configure MongoDB connection logic
- Fetch data from MongoDB
- Convert key-value data to Pandas DataFrame

Files involved:
- `configuration/mongo_db_connections.py`
- `data_access/`
- `entity/config_entity.py`
- `entity/artifact_entity.py`
- `components/data_ingestion.py`
- Training pipeline

Run:
```bash
python demo.py
```

---

## 🔐 Step 8: MongoDB Environment Variable

### Bash
```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster"
```

### PowerShell
```powershell
$env:MONGODB_URL="mongodb+srv://<username>:<password>@cluster"
```

Add `artifact/` directory to `.gitignore`.

---

## ✅ Step 9: Data Validation

- Define dataset schema in `config/schema.yaml`
- Validate column names, types, missing values
- Generate validation artifacts

---

## 🔧 Step 10: Data Transformation

- Feature engineering
- Scaling & encoding
- Train-test split
- Estimator logic added to `entity/estimator.py`

---

## 🤖 Step 11: Model Training

- Train ML model
- Save trained artifacts
- Track performance metrics

---

## ☁️ Step 12: AWS Setup

Required services:
- IAM
- S3
- ECR
- EC2

Create IAM user with:
- AdministratorAccess
- Generate access keys

Set environment variables:

```bash
export AWS_ACCESS_KEY_ID="YOUR_KEY"
export AWS_SECRET_ACCESS_KEY="YOUR_SECRET"
export AWS_DEFAULT_REGION="us-east-1"
```

---

## 🗂️ Step 13: Model Registry (AWS S3)

Constants:
```python
MODEL_BUCKET_NAME = "my-model-mlopsproj"
MODEL_PUSHER_S3_KEY = "model-registry"
MODEL_EVALUATION_CHANGED_THRESHOLD_SCORE = 0.02
```

- Upload & retrieve models from S3
- Version control for models

---

## 🔍 Step 14: Model Evaluation & Pusher

- Compare new model vs existing model
- Push model only if performance improves
- Ensures safe production deployment

---

## 🔮 Step 15: Prediction Pipeline

- Flask-based API
- `/predict` → get predictions
- `/training` → trigger training pipeline

---

## 🐳 Step 16: Docker & CI/CD

- Dockerfile & .dockerignore setup
- GitHub Actions workflow
- Build → Push to ECR → Deploy to EC2

---

## 🖥️ Step 17: EC2 Deployment

- Launch Ubuntu EC2
- Install Docker
- Configure GitHub self-hosted runner
- Open port `5080`

Access app:
```
http://<EC2_PUBLIC_IP>:5080
```

---

## 🧪 Tech Stack

- Python 3.10
- Scikit-learn
- MongoDB Atlas
- AWS (S3, EC2, ECR)
- Docker
- GitHub Actions
- Flask

---

## 📈 Why Recruiters Love This Project

✔ Real-world MLOps pipeline  
✔ Cloud-native deployment  
✔ CI/CD automation  
✔ Clean architecture  
✔ Production-ready practices  

---

## 👤 Author

**Teja**  
AI Engineer | Data Scientist | MLOps Enthusiast
