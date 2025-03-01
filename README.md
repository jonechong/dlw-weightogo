# Weigh To Go

**Weigh To Go** is a **full-stack application** that provides a **personalized food tracking and recommendation system**, designed specifically for the **Singaporean market**. It consists of:

- **Frontend**: A **React-based web application** where users can **record food intake, track nutrition, and receive tailored meal recommendations**.
- **Backend**: A **FastAPI-based backend** that **analyzes food images, provides nutritional information, and generates personalized recommendations** using **GPT‑4o**.

This repository contains both the **frontend and backend as submodules**, ensuring seamless integration in a single repository.

📹 **Video Demo:** [Watch here](https://drive.google.com/file/d/1C6J6vIS4rPu9XCqIrpM7_eMn7zwEUzUc/view?usp=sharing)

---

## **Key Features**

### **Singapore-Focused Food Tracking**
- **Recognizes local Singaporean dishes** for accurate nutritional tracking.
- Fetches **real-time nutritional information** using GPT‑4o.
- Provides recommendations tailored to **Singaporean dietary habits and food availability**.

### **Personalized Meal Recommendations**
- Takes into account **user profile information**, including:
  - **Height, age, weight, and activity level**.
  - **Automatic BMR calculation and daily energy expenditure estimation**.
  - **Target calorie deficit selection** (0.25 to 1 kg per week, constrained for safe weight loss).
  - **Medical conditions** (e.g., **high cholesterol, dietary restrictions**).
- Provides **meal suggestions based on eating patterns**.

### **Behavioral Analytics (Incomplete)**
- Designed to **analyze eating patterns** (e.g., overeating trends on certain days).
- Helps users **modify their habits** by suggesting **lighter meals or portion adjustments**.
- **Currently incomplete** due to time constraints.

---

## **Project Structure**

```bash
Weigh-To-Go/
├── backend/   # FastAPI backend (submodule)
│   ├── app/
│   ├── requirements.txt
│   ├── main.py
│   ├── get_food_info.py
│   ├── get_personalized_recommendations.py
├── frontend/  # React frontend (submodule)
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── App.js
│   ├── index.js
├── .gitmodules  # Submodule configuration
├── README.md  # This documentation file
```

---

## **Setup & Installation**

### **1. Clone the Repository with Submodules**
Since the frontend and backend are **submodules**, ensure you clone them correctly:

```bash
git clone --recurse-submodules https://github.com/your-username/weigh-to-go.git
cd weigh-to-go
```

If you already cloned it without submodules, initialize them manually:

```bash
git submodule update --init --recursive
```

### **2. Backend Setup (FastAPI)**
Navigate to the backend directory and install dependencies:

```bash
cd backend
pip install -r requirements.txt
```

Create a `.env` file with your **OpenAI API key**:

```ini
OPENAI_API_KEY=your_openai_api_key_here
```

Start the FastAPI backend:

```bash
uvicorn app.main:app --reload
```

The backend will be running at **http://127.0.0.1:8000**.

### **3. Frontend Setup (React)**
Navigate to the frontend directory and install dependencies:

```bash
cd ../frontend
npm install
```

Start the React application:

```bash
npm start
```

The frontend will be available at **http://localhost:3000**.

---

## **Usage**
- Open **http://localhost:3000** in your browser to access the application.
- The frontend interacts with the backend running on **http://127.0.0.1:8000**.
- Users can **upload food images** or **manually input meals** to track intake.
- The backend will **analyze the food and provide nutritional details**.
- The system **suggests personalized meal recommendations** based on user goals and eating habits.

---

## **Updating the Submodules**
If changes are made to the frontend or backend repositories, update them:

```bash
git submodule update --remote --merge
```

Then commit and push the changes:

```bash
git commit -m "Updated frontend and backend submodules"
git push origin main
```

---

## **Notes**
- **Ensure the FastAPI backend is running on port 8000** before starting the frontend.
- **Material-UI** is used for frontend styling.
- The **analytics page is incomplete** due to time constraints.
- The app is designed for the **Singaporean market**, offering **localized meal tracking and recommendations**.

---

This documentation provides all necessary information to set up, run, and contribute to the **Weigh To Go** project. Let us know if you have any questions!

