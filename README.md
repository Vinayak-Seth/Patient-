🏥 ML Patient Risk Prediction System

A real-time simulated patient risk prediction system using Machine Learning to assist doctors in identifying high-risk ICU patients.

🌟 Features
ML-Powered Risk Prediction: Uses Random Forest algorithm trained on ICU-like synthetic patient data
Real-Time Simulated Dashboard: Live monitoring of simulated patient vitals and risk levels
Risk Classification: Automatic categorization into Low/Medium/High risk
Critical Alerts: Instant popup notifications for high-risk patients
Doctor Login: Demo-only authentication system for academic demonstration
Patient Details View: Comprehensive view of individual patient vitals and history
Color-Coded Interface: Easy visual identification of risk levels (Green/Yellow/Red)
📊 System Workflow
Patient Data → Data Preprocessing → ML Risk Prediction → Alert/Dashboard → Doctor Decision
🔧 Installation
Local Setup
Clone the repository
git clone <your-repo-url>
cd <repo-name>
Install dependencies
pip install -r requirements_streamlit.txt
Train the ML model
python train_model.py
This will: - Generate synthetic ICU-like patient data - Train a Random Forest classifier - Save the trained model as risk_model.pkl - Display model performance metrics

Run the Streamlit app
streamlit run streamlit_app.py
Access the application
Open your browser to http://localhost:8501
Login with demo credentials:
Username: doctor / Password: doctor123
Username: admin / Password: admin123
☁️ Deployment on Streamlit Cloud
Push project to GitHub\
Go to https://share.streamlit.io\
Select repository and main file: streamlit_app.py\
Click Deploy
📁 Project Structure
.
├── streamlit_app.py
├── train_model.py
├── requirements_streamlit.txt
├── README_STREAMLIT.md
├── risk_model.pkl
└── .gitignore
🎯 Input Features
Age
Heart Rate
Blood Pressure
Oxygen Saturation
Temperature
WBC Count
Glucose Level
📈 Output
Risk Score (0-100%)
Risk Level: Low / Medium / High
Alert for High-Risk Patients
🧪 Model Details
Algorithm: Random Forest Classifier
Dataset: Synthetic ICU-like patient data
Classes: Low, Medium, High Risk
Model achieves good predictive performance on synthetic validation data
🔍 Explainability
The system provides feature importance visualization to explain which vitals influence risk prediction decisions.

🔒 Security Note
This is a demo academic application. Not intended for real medical use.

📝 License
MIT License

Note: This project is for educational purposes only and should not be used for real medical diagnosis.
