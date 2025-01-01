# MLOps Project: A Comprehensive Guide and Workflow

Welcome to this MLOps project, designed to demonstrate a robust pipeline for managing vehicle insurance data. This repository offers a hands-on demonstration of an industry-standard MLOps pipeline, showcasing the entire lifecycle of a Machine Learning project—from data ingestion and validation to deployment and CI/CD integration. 
---

## ✨ **Features**

### 🔧 **End-to-End Pipeline**
- Automates the entire machine learning workflow.
- Modular components for flexibility and reusability.

### 🛠️ **Robust Tooling**
- MongoDB Atlas for efficient database management.
- Python-based feature engineering and data transformation.
- Seamless integration with AWS services for cloud storage and deployment.

### 🌍 **Cloud-Ready Design**
- Integrated with AWS S3 for artifact management.
- Deployed on EC2 instances with Docker for scalability.

### 🔄 **CI/CD Pipeline**
- Automated workflows using GitHub Actions.
- Self-hosted runners for continuous integration and deployment.

### 🌐 **Interactive Application**
- Web interface for real-time data insights and model predictions.

---

## 📚 **Project Structure**

```plaintext
├── notebook
│   ├── mongoDB_demo.ipynb        # MongoDB integration demo
│   ├── eda_feature_engineering.ipynb  # Exploratory Data Analysis & Feature Engineering
├── src
│   ├── configuration
│   │   ├── mongo_db_connections.py  # MongoDB connection utilities
│   │   ├── aws_connection.py        # AWS configuration scripts
│   ├── entity
│   │   ├── config_entity.py         # Configuration entities
│   │   ├── artifact_entity.py       # Artifact structure definitions
│   │   ├── estimator.py             # Model training and evaluation utilities
│   ├── data_access
│   │   ├── proj1_data.py            # Data fetching & transformations
│   ├── components
│   │   ├── data_ingestion.py        # Data ingestion scripts
│   │   ├── data_validation.py       # Data validation scripts
│   │   ├── data_transformation.py   # Data transformation scripts
│   │   ├── model_trainer.py         # Model training scripts
│   ├── aws_storage
│   │   ├── s3_estimator.py          # AWS S3 interaction utilities
├── app.py                          # Main application entry point
├── requirements.txt                # Dependency list
├── setup.py                        # Local package setup
├── pyproject.toml                  # Build system configuration
├── Dockerfile                      # Docker configuration
├── .dockerignore                   # Ignored files during Docker build
├── .github
│   ├── workflows
│   │   ├── aws.yaml                # CI/CD pipeline configuration
```

---

## ⚙️ **Installation and Setup**

### **Step 1: Create and Activate a Virtual Environment**

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

### **Step 2: Install Dependencies**

Ensure all required packages are listed in `requirements.txt`, then run:

```bash
pip install -r requirements.txt
```

### **Step 3: Verify Installation**

```bash
pip list
```

---

## 🗄️ **MongoDB Setup**

### **Step 1: Cluster Creation**
- Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas).
- Create a new cluster with default settings.

### **Step 2: Access Configuration**
- Add IP Address `0.0.0.0/0` to allow universal access.
- Set up a database user with credentials.

### **Step 3: Connection String**
- Navigate to *Database > Connect > Drivers*.
- Copy and modify the connection string to include your credentials.

### **Step 4: Data Upload**
- Use `mongoDB_demo.ipynb` to upload datasets to MongoDB.

### **Step 5: Verify Data**
- Browse uploaded data via MongoDB Atlas.

---

## 📈 **Data Pipeline Workflow**

### **1. Data Ingestion**
- Fetch and structure data from MongoDB.
- **Key Scripts**:
  - `data_access/proj1_data.py`
  - `components/data_ingestion.py`

### **2. Data Validation**
- Validate data against a schema (`config.schema.yaml`).
- **Key Scripts**:
  - `components/data_validation.py`

### **3. Data Transformation**
- Preprocess and transform data for model training.
- **Key Scripts**:
  - `components/data_transformation.py`

### **4. Model Training**
- Train machine learning models and save artifacts to AWS S3.
- **Key Scripts**:
  - `components/model_trainer.py`

---

## 🌐 **AWS Integration**

### **1. IAM Setup**
- Create an IAM user with `AdministratorAccess` policy.

### **2. S3 Bucket**
- Configure an S3 bucket named `my-model-mlopsproj`.

### **3. EC2 Instance**
- Deploy the app on an Ubuntu EC2 instance.
- Install Docker and required tools.

### **4. Environment Variables**
- Set AWS credentials in `constants/__init__.py`.

---

## 🔄 **CI/CD Integration**

### **Step 1: GitHub Actions**
- Configure workflows in `.github/workflows/aws.yaml`.
- Add secrets for AWS credentials and repository configurations.

### **Step 2: Self-Hosted Runner**
- Set up a GitHub self-hosted runner on EC2 for automated deployments.

---

## 📋 **Usage Instructions**

### **Run the Application**

```bash
python app.py
```

### **Access the Application**
- Visit `http://<EC2_PUBLIC_IP>:5080`.
- Trigger training via `/training` route.

---

## 🌟 **Highlights**

### **Complete MLOps Workflow**
- End-to-end pipeline from raw data ingestion to cloud deployment.

### **Cloud-Native Architecture**
- Leverages AWS for storage, deployment, and scalability.

### **Continuous Integration**
- Streamlined updates with GitHub Actions and Docker.

### **User-Friendly Interface**
- Simplifies operations for both technical and non-technical users.

---

## 🙌 **Acknowledgments**

Special thanks to:

- **MongoDB Atlas** for database solutions.
- **AWS** for cloud infrastructure support.
- **Python Community** for essential libraries and tools.

---

## 🔗 **Get in Touch**

We welcome contributions, suggestions, and feedback! Please feel free to open an issue or submit a pull request on this repository.

---

Thank you for exploring this project! We hope it inspires you to build scalable and efficient MLOps solutions. 🚀


