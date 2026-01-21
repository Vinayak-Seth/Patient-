# 🏥 ML Patient Risk Prediction System

A real-time patient risk prediction system using Machine Learning to assist doctors in identifying high-risk ICU patients.

## 🌟 Features

- **ML-Powered Risk Prediction**: Uses Random Forest algorithm trained on ICU patient data
- **Real-Time Dashboard**: Live monitoring of patient vitals and risk levels
- **Risk Classification**: Automatic categorization into Low/Medium/High risk
- **Critical Alerts**: Instant popup notifications for high-risk patients
- **Doctor Login**: Simple authentication system for medical staff
- **Patient Details View**: Comprehensive view of individual patient vitals and history
- **Color-Coded Interface**: Easy visual identification of risk levels (Green/Yellow/Red)

## 📊 System Workflow

```
Patient Data → Data Preprocessing → ML Risk Prediction → Alert/Dashboard → Doctor Decision
```

## 🔧 Installation

### Local Setup

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd <repo-name>
```

2. **Install dependencies**
```bash
pip install -r requirements_streamlit.txt
```

3. **Train the ML model**
```bash
python train_model.py
```
This will:
- Generate synthetic ICU patient data (1000 samples)
- Train a Random Forest classifier
- Save the trained model as `risk_model.pkl`
- Display model accuracy and performance metrics

4. **Run the Streamlit app**
```bash
streamlit run streamlit_app.py
```

5. **Access the application**
- Open your browser to `http://localhost:8501`
- Login with demo credentials:
  - Username: `doctor` / Password: `doctor123`
  - Username: `admin` / Password: `admin123`

## ☁️ Deployment on Streamlit Cloud

### Step 1: Push to GitHub

1. Initialize git repository (if not already done):
```bash
git init
git add .
git commit -m "Initial commit: ML Patient Risk Prediction System"
```

2. Create a new repository on GitHub

3. Push your code:
```bash
git remote add origin <your-github-repo-url>
git push -u origin main
```

### Step 2: Deploy on Streamlit Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io)

2. Sign in with your GitHub account

3. Click **"New app"**

4. Fill in the deployment settings:
   - **Repository**: Select your GitHub repository
   - **Branch**: `main` (or your default branch)
   - **Main file path**: `streamlit_app.py`

5. Click **"Advanced settings"** (optional):
   - Set Python version: `3.9` or higher

6. Click **"Deploy!"**

7. Wait for the deployment to complete (usually 2-5 minutes)

8. Your app will be live at: `https://share.streamlit.io/[username]/[repo-name]/main/streamlit_app.py`

### Important Notes for Streamlit Cloud:

- The model will be **trained automatically on first run** if `risk_model.pkl` doesn't exist
- Make sure `risk_model.pkl` is **NOT** in `.gitignore` if you want to include the pre-trained model
- Alternatively, you can train the model locally and push it to GitHub

## 📁 Project Structure

```
.
├── streamlit_app.py              # Main Streamlit application
├── train_model.py                # ML model training script
├── requirements_streamlit.txt    # Python dependencies
├── README_STREAMLIT.md          # This file
├── risk_model.pkl               # Trained ML model (generated)
└── .gitignore                   # Git ignore file
```

## 🎯 Input Features

The system monitors the following patient vitals:

- **Age**: Patient age in years
- **Heart Rate**: Beats per minute (bpm)
- **Blood Pressure**: Systolic/Diastolic (mmHg)
- **Oxygen Saturation**: O₂ levels (%)
- **Temperature**: Body temperature (°C)
- **WBC Count**: White Blood Cell count (K/μL)
- **Glucose**: Blood glucose level (mg/dL)

## 📈 Output

- **Risk Score**: Probability score (0-100%)
- **Risk Level**: Low / Medium / High
- **Alert**: Critical popup for high-risk patients

## 🔐 Demo Credentials

| Username | Password   | Role |
|----------|------------|------|
| doctor   | doctor123  | Doctor |
| admin    | admin123   | Admin |

## 🧪 Model Details

- **Algorithm**: Random Forest Classifier
- **Training Data**: 1000 synthetic ICU patient records
- **Features**: 8 clinical parameters
- **Classes**: 3 risk levels (Low, Medium, High)
- **Performance**: ~85-90% accuracy (on synthetic data)

## 🎨 Dashboard Features

### Main Dashboard
- Patient statistics overview
- Real-time risk distribution
- Critical alert notifications
- Comprehensive patient vitals table
- Color-coded risk indicators

### Patient Details View
- Individual patient vitals
- Historical data
- Detailed risk assessment
- Actionable recommendations

### Auto-Refresh Mode
- Simulates real-time data updates
- Configurable refresh interval (5-60 seconds)
- Live monitoring capability

## 🛠️ Customization

### Using Real ICU Data

To use real patient data instead of synthetic data:

1. Modify the `generate_synthetic_patients()` function in `streamlit_app.py`
2. Load your dataset (CSV, database, API)
3. Ensure column names match the expected format
4. Retrain the model with your data using `train_model.py`

### Adjusting Risk Thresholds

Modify the risk scoring logic in `train_model.py`:
- Line 50-90: Adjust threshold values for each vital sign
- Line 92-98: Modify risk level boundaries

## 📊 Model Training

The `train_model.py` script:
- Generates synthetic ICU patient data
- Trains a Random Forest classifier
- Evaluates model performance
- Saves the model as `risk_model.pkl`

To retrain with different parameters:
```python
model = RandomForestClassifier(
    n_estimators=100,      # Number of trees
    max_depth=10,          # Maximum tree depth
    random_state=42,
    class_weight='balanced' # Handle imbalanced classes
)
```

## 🔒 Security Note

This is a **demo application** with simple authentication. For production use:
- Implement proper user authentication (OAuth, JWT)
- Use encrypted database connections
- Add HIPAA compliance measures
- Implement audit logging
- Use HTTPS for all communications

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Built with Streamlit
- ML powered by scikit-learn
- Inspired by real-world ICU monitoring systems

## 📧 Support

For issues, questions, or suggestions, please open an issue on GitHub.

---

**Note**: This system is designed for educational and demonstration purposes. It should not be used for actual medical diagnosis without proper validation, regulatory approval, and clinical testing.
