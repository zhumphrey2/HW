# Restaurant Dashboard - Streamlit App

A web-based dashboard for exploring restaurant data in London, built with Streamlit and MySQL.

## 📋 Prerequisites

- Python 3.8 or higher
- MySQL database with the `restaurant.business_location` table
- Database credentials

## 🚀 Setup Instructions

### Step 1: Install UV (Python Package Manager)

UV is a fast Python package installer and resolver written in Rust.

#### Windows:
Open PowerShell as Administrator and run:
```powershell
# Using PowerShell
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

#### Mac/Linux:
Open Terminal and run:
```bash
# Using curl
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation, restart your terminal/PowerShell to ensure UV is in your PATH.

---

### Step 2: Navigate to Project Directory

#### Windows (PowerShell):
```powershell
cd path\to\HW2-london
```

#### Mac/Linux:
```bash
cd path/to/HW2-london
```

---

### Step 3: Create Virtual Environment

#### Windows (PowerShell):
```powershell
# Create virtual environment
uv venv

# You should see a .venv folder created
```

#### Mac/Linux:
```bash
# Create virtual environment
uv venv

# You should see a .venv folder created
```

---

### Step 4: Activate Virtual Environment

#### Windows (PowerShell):
```powershell
# Activate virtual environment
.\.venv\Scripts\activate

# You should see (.venv) appear at the beginning of your prompt
```

#### Mac/Linux:
```bash
# Activate virtual environment
source .venv/bin/activate

# You should see (.venv) appear at the beginning of your prompt
```

---

### Step 5: Install Required Packages

#### Both Windows and Mac/Linux (after activation):
```bash
# Install all required packages
uv pip install -r requirements.txt

# This will install:
# - streamlit
# - pandas
# - mysql-connector-python
# - folium
# - streamlit-folium
```

---

### Step 6: Configure Database Connection

Edit the `app.py` file and update the database credentials in Block 4:

```python
connection = mysql.connector.connect(
    host='localhost',           # Update with your MySQL host
    user='restaurant_readonly',  # Update with your MySQL username
    port=25060,                  # Update with you MySQL port
    password='SecurePassword123!', # Update with your MySQL password
    database='restaurant'        # Keep as 'restaurant' if using provided schema
)
```

---

### Step 7: Run the Streamlit App

#### Both Windows and Mac/Linux (with virtual environment activated):
```bash
streamlit run app.py
```

The app will automatically open in your default web browser at `http://localhost:8501`

---

## 📱 Using the Application

### Navigation
Use the sidebar to navigate between three pages:

1. **HW Summary**: Overview of the implementation and customizations
2. **Q1-DB Query**: Search restaurants by name pattern and vote range
3. **Q2-Maps**: Interactive map showing restaurant locations

### Features

#### Q1-DB Query Page:
- Enter a pattern to search restaurant names (leave blank for all)
- Use the slider to filter by vote range
- Click "Get results" to view matching restaurants

#### Q2-Maps Page:
- Click "Display map!" to show restaurants on an interactive map
- Click on markers to see restaurant names
- Map uses custom CartoDB Positron tiles

---

## 🛑 Stopping the Application

1. In the terminal, press `Ctrl+C` to stop the Streamlit server
2. Deactivate the virtual environment:

#### Both Windows and Mac/Linux:
```bash
deactivate
```

---

## 🔧 Troubleshooting

### Common Issues:

#### 1. UV command not found
- **Solution**: Restart your terminal after installation
- **Alternative**: Add UV to your PATH manually

#### 2. MySQL connection error
- **Solution**: Verify your database credentials in `app.py`
- **Check**: Ensure MySQL server is running
- **Check**: Ensure the `restaurant` database exists

#### 3. Port already in use
- **Solution**: Kill existing process or use different port:
```bash
streamlit run app.py --server.port 8502
```

#### 4. Package installation fails
- **Solution**: Try updating pip first:
```bash
uv pip install --upgrade pip
```

#### 5. Virtual environment activation fails
- **Windows**: Ensure you're using PowerShell (not Command Prompt)
- **Windows**: May need to enable script execution:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

## 📂 Project Structure

```
HW2-london/
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
├── README.md          # This file
├── database_setup.sql # SQL script to create database (already run)
└── .venv/            # Virtual environment (created by uv)
```

---

## 🎨 Customizations Made

1. **Color Scheme**: Professional dark blue sidebar with light gray background
2. **Layout**: Wide layout with responsive columns and info boxes
3. **Map Style**: CartoDB Positron tiles instead of default OpenStreetMap
4. **Interactive Elements**: Custom styled buttons with hover effects

---

## 📚 Technologies Used

- **Frontend Framework**: Streamlit
- **Database**: MySQL
- **Data Processing**: Pandas
- **Mapping**: Folium with Streamlit-Folium
- **Package Management**: UV

---

## 📝 Notes

- The app uses read-only database access for security
- Session state is used to maintain button states between reruns
- Map markers show restaurant names on click
- Results are sorted by votes in descending order

---

## 👤 Author

ITOM6265 Student - Database Management Course

---

## 📄 License

This project is for educational purposes as part of ITOM6265 coursework.