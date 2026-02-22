# 💻 Laptop Price Predictor - Flask Web Application

A beautiful and responsive machine learning web application built with Flask to predict laptop prices based on specifications.

## 🌟 Features

- **Single Prediction**: Interactive form with dropdowns for categorical features
- **Batch Prediction**: Upload CSV files for bulk predictions
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Modern UI**: Beautiful gradient design with smooth animations
- **Real-time Validation**: Form validation with helpful error messages
- **Download Results**: Export batch predictions as CSV

## 🚀 Tech Stack

- **Backend**: Flask (Python)
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **ML**: scikit-learn, pandas, joblib
- **Deployment**: Render (or any cloud platform)

## 📁 Project Structure

```
laptop-price-predictor/
├── flask_app.py              # Main Flask application
├── templates/
│   └── index.html            # HTML template
├── static/
│   ├── css/
│   │   └── style.css         # Stylesheet
│   └── js/
│       └── script.js         # JavaScript functionality
├── artifacts/
│   └── transformed/
│       ├── preprocessor.joblib
│       ├── feature_list.json
│       └── train.csv
├── prediction/
│   └── models/
│       └── models/
│           └── current_model.joblib
├── requirements.txt          # Python dependencies
├── Procfile                  # Render deployment config
├── runtime.txt              # Python version
└── README.md                # This file
```

## 🛠️ Local Setup

### Prerequisites
- Python 3.11 or higher
- pip (Python package manager)

### Installation

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd laptop-price-predictor
```

2. **Create virtual environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Ensure your ML artifacts are in place**
Make sure you have:
- `artifacts/transformed/preprocessor.joblib`
- `artifacts/transformed/feature_list.json`
- `artifacts/transformed/train.csv`
- `prediction/models/models/current_model.joblib`

5. **Run the application**
```bash
python flask_app.py
```

6. **Open your browser**
Navigate to: `http://localhost:5000`

## 🌐 Deployment on Render

### Step 1: Prepare Your Repository

1. Initialize git (if not already done):
```bash
git init
git add .
git commit -m "Initial commit"
```

2. Push to GitHub:
```bash
git remote add origin <your-github-repo-url>
git branch -M main
git push -u origin main
```

### Step 2: Deploy on Render

1. **Sign up/Login** to [Render](https://render.com)

2. **Create New Web Service**
   - Click "New +" → "Web Service"
   - Connect your GitHub repository

3. **Configure Settings**
   - **Name**: `laptop-price-predictor` (or your choice)
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn flask_app:app`
   - **Instance Type**: Free (or paid for better performance)

4. **Environment Variables** (if needed)
   - Add any environment-specific variables

5. **Deploy**
   - Click "Create Web Service"
   - Wait for deployment (3-5 minutes)

6. **Access Your App**
   - Your app will be available at: `https://your-app-name.onrender.com`

### Important Notes for Render

- Make sure all artifact files are committed to git
- The free tier may have cold starts (app sleeps after inactivity)
- For production, consider using a paid plan for better performance
- File paths are absolute, so they'll work on Render without changes

## 📊 Using the Application

### Single Prediction

1. Navigate to "Single Prediction" section
2. Fill in all laptop specifications:
   - **Numeric fields**: RAM, Storage, Screen Size, etc.
   - **Categorical fields**: Brand, Processor, GPU, etc.
3. Click "Predict Price"
4. View the predicted price and input summary

### Batch Prediction

1. Navigate to "Batch Prediction" section
2. Prepare a CSV file with laptop specifications (without Price_INR column)
3. Upload the CSV file
4. Click "Run Batch Prediction"
5. Download the results CSV with predictions

### Sample CSV Format

```csv
Brand,Processor,RAM,Storage,Screen_Size,GPU,OS
Dell,Intel Core i5,8,256,15.6,Integrated,Windows
HP,AMD Ryzen 7,16,512,14,NVIDIA GTX,Windows
Lenovo,Intel Core i7,16,1024,15.6,NVIDIA RTX,Linux
```

## 🎨 Customization

### Changing Colors
Edit `static/css/style.css` and modify CSS variables:
```css
:root {
    --primary-color: #4f46e5;
    --secondary-color: #10b981;
    /* Add your custom colors */
}
```

### Adding Features
1. Update the ML model and artifacts
2. Modify `feature_list.json`
3. The UI will automatically adapt to new features

## 🐛 Troubleshooting

### Model/Artifacts Not Found
- Ensure all artifact paths in `flask_app.py` are correct
- Check that files exist in the specified directories
- Verify file permissions

### Port Already in Use
```bash
# Change port in flask_app.py
app.run(debug=True, host='0.0.0.0', port=5001)
```

### CSV Upload Issues
- Ensure CSV has same columns as training data
- Check for missing or extra columns
- Verify data types match expected format

## 📝 API Endpoints

### GET `/`
- Returns the main HTML page

### POST `/predict`
- Single prediction endpoint
- **Body**: Form data with all features
- **Response**: JSON with prediction and input data

### POST `/batch_predict`
- Batch prediction endpoint
- **Body**: Multipart form data with CSV file
- **Response**: CSV file with predictions

### GET `/health`
- Health check endpoint
- **Response**: JSON with system status

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

Your Name - [Your GitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- scikit-learn for ML capabilities
- Flask for the web framework
- Font Awesome for icons
- Render for hosting

---

echo "# CI/CD Test" 
