# 🥗 Web-Based Diet Recommendation System
📸 [Click to Watch Demo](https://drive.google.com/file/d/1P4kzcwt4dDlZtJPnXiDaV1euIU9yhDUf/view?usp=sharing)

## 📖 Overview
A Flask-based web application that generates personalized diet recommendations based on user input. It calculates BMR and TDEE, fetches matching meals from MongoDB, and generates a downloadable PDF diet chart using pdfkit.

## 📌 Project Idea
The goal of this project is to provide customized dietary recommendations by combining nutritional science with automation.  
The system calculates BMR (Basal Metabolic Rate) and TDEE (Total Daily Energy Expenditure) using user inputs, filters food items according to health conditions, and creates meal-wise recommendations that can be downloaded as a PDF.

## 📋 Prerequisites
- Python 3.8+  
- MongoDB (Local or Atlas)  
- wkhtmltopdf (Installed & added to PATH)

## ⚙ Installation & Setup
**Clone the Repository**
```bash
git clone https://github.com/VidweshK182/Smart-Diet
cd Diet-Recommendation System
```

**Create Virtual Environment & Install Dependencies**
```bash
python -m venv venv
venv\Scripts\activate  # On Windows
source venv/bin/activate  # On Mac/Linux
pip install -r requirements.txt
```

**Set Environment Variables**
```bash
set MONGO_URI=your_mongo_connection_string  # Windows
export MONGO_URI=your_mongo_connection_string  # Mac/Linux
```

**Run the Application**
```bash
python app.py
```

---

## ✨ Features
- **Personalized Diet Plans** — Tailored to user’s age, gender, weight, height, activity level, and health conditions.  
- **Health Condition Filtering** — Automatically excludes or recommends foods based on medical conditions.  
- **BMR & TDEE Calculation** — Scientifically calculates daily calorie requirements.  
- **Meal-wise Categorization** — Breakfast, lunch, snacks, and dinner recommendations.  
- **PDF Export** — Generates a downloadable, neatly formatted PDF diet chart.  
- **Database-Driven** — Stores and retrieves food and disease data from MongoDB.  
- **Responsive Web UI** — Accessible on mobile, tablet, and desktop devices.  

---

## 📈 How It Works

1. **User Input**:  
   - User registers and logs in.  
   - Enters weight, height, age, gender, diseases, activity level, and meal preference.  

2. **BMR & Calorie Calculation**:  
   - BMR is calculated using the **Mifflin-St Jeor Equation**.  
   - Total daily energy expenditure is adjusted using the **Physical Activity Level (PAL)** factor.  

3. **Disease Nutrient Filtering**:  
   - Nutrient restrictions for selected diseases are loaded from `final_diseases.csv`.  
   - Food items from `final_food_items.csv` are filtered based on these nutrients.  

4. **Meal Categorization**:  
   - Remaining items are classified into meals (breakfast, lunch, snacks, dinner).  
   - Vegetarian/Non-Vegetarian preferences are respected.  

5. **Diet Plan Output**:  
   - HTML page displays the categorized food items.  
   - Option to download a structured PDF report of the diet plan.  

6. **PDF Generation**:  
   - HTML is converted into PDF using `pdfkit` + `wkhtmltopdf`.  
   - PDF is stored in `/pdfs` and path is stored in MongoDB.  

---

## 📂 Project Structure
```csharp
Diet-Recommendation/
├── static/                     # CSS, images, fonts, SVGs
├── templates/                  # HTML templates (Jinja2)
├── data/                       # Dataset files (CSV)
│   ├── final_food_items.csv     # Food database
│   ├── final_diseases.csv       # Disease-wise nutrient requirements
│   ├── Calorie_value.csv        # Food categories & calorie info
├── pdfs/                        # Generated PDF diet charts
├── app.py                       # Main Flask application
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation
```

---

## 🛠 Technologies Used

| Category    | Tools / Frameworks |
|-------------|--------------------|
| Backend     | Python, Flask      |
| Frontend    | HTML5, CSS3, Jinja2|
| Database    | MongoDB (pymongo)  |
| PDF Generator | pdfkit, wkhtmltopdf |
| Data Handling | pandas           |
| Server      | Gunicorn (Production WSGI) |

---

## 📚 References
- [Flask Documentation](https://flask.palletsprojects.com/)  
- [MongoDB Documentation](https://www.mongodb.com/docs/)  
- [pdfkit Documentation](https://pypi.org/project/pdfkit/)  
- [Jinja2 Documentation](https://jinja.palletsprojects.com/)  
