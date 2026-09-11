# Patient Management API

A simple **Patient Management REST API** built with **FastAPI** and **Pydantic** while learning and practicing FastAPI concepts.

This project demonstrates how to build APIs with FastAPI, validate request data using Pydantic, perform CRUD operations, work with path and query parameters, and implement computed fields such as BMI and health verdict.

---

## 🚀 Features

* ✅ Create a new patient
* ✅ Retrieve all patients
* ✅ Retrieve a patient by ID
* ✅ Update patient information
* ✅ Delete a patient
* ✅ Sort patients by height, weight, or BMI
* ✅ Automatic BMI calculation
* ✅ Automatic health verdict based on BMI
* ✅ Request validation using Pydantic
* ✅ Interactive API documentation with Swagger UI
* ✅ JSON-based data storage

---

## 🛠️ Tech Stack

* **Python**
* **FastAPI**
* **Pydantic**
* **Uvicorn**
* **JSON**

---

## 📂 Project Structure

```text
patient-management-api/
│
├── main.py              # FastAPI application and API endpoints
├── patients.json        # Patient data
├── requirements.txt     # Python dependencies
├── .gitignore           # Files ignored by Git
└── README.md            # Project documentation
```

> `myvenv/` is intentionally excluded from the repository using `.gitignore`.

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/patient-management-api.git
```

### 2. Navigate to the project directory

```bash
cd patient-management-api
```

### 3. Create a virtual environment

```bash
python -m venv myvenv
```

### 4. Activate the virtual environment

**Windows:**

```bash
myvenv\Scripts\activate
```

**Linux / macOS:**

```bash
source myvenv/bin/activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application

Start the FastAPI development server:

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

---

## 📚 API Documentation

FastAPI automatically provides interactive API documentation.

### Swagger UI

Open:

```text
http://127.0.0.1:8000/docs
```

### ReDoc

Open:

```text
http://127.0.0.1:8000/redoc
```

You can use Swagger UI to test the API endpoints directly from your browser.

---

# 🔗 API Endpoints

| Method   | Endpoint                | Description                |
| -------- | ----------------------- | -------------------------- |
| `GET`    | `/`                     | Welcome message            |
| `GET`    | `/about`                | Information about the API  |
| `GET`    | `/view`                 | View all patients          |
| `GET`    | `/patient/{patient_id}` | Get a patient by ID        |
| `GET`    | `/sort`                 | Sort patients              |
| `POST`   | `/create`               | Create a new patient       |
| `PUT`    | `/edit/{patient_id}`    | Update patient information |
| `DELETE` | `/delete/{patient_id}`  | Delete a patient           |

---

## 🧮 BMI Calculation

The API automatically calculates BMI using:

```text
BMI = Weight (kg) / Height² (m)
```

For example:

```text
Weight = 70 kg
Height = 1.75 m

BMI = 70 / (1.75²)
    = 22.86
```

The API also generates a health verdict based on the BMI value.

### BMI Categories

| BMI           | Category    |
| ------------- | ----------- |
| `< 18.5`      | Underweight |
| `18.5 – 24.9` | Normal      |
| `25 – 29.9`   | Overweight  |
| `≥ 30`        | Obese       |

---

# 📝 Example API Requests

## Create Patient

### Request

```http
POST /create
```

### Example JSON

```json
{
    "id": "P010",
    "name": "Rahul Kumar",
    "city": "Jaipur",
    "age": 25,
    "gender": "male",
    "height": 1.75,
    "weight": 70
}
```

### Example Response

```json
{
    "id": "P010",
    "name": "Rahul Kumar",
    "city": "Jaipur",
    "age": 25,
    "gender": "male",
    "height": 1.75,
    "weight": 70,
    "bmi": 22.86,
    "verdict": "Normal"
}
```

---

## Get Patient by ID

```http
GET /patient/P001
```

Example:

```text
http://127.0.0.1:8000/patient/P001
```

---

## Sort Patients

The API supports sorting patients using query parameters.

Example:

```http
GET /sort?sort_by=bmi&order=asc
```

Available sorting fields:

```text
height
weight
bmi
```

Available sorting orders:

```text
asc
desc
```

---

## 🔍 Data Validation

Pydantic models are used to validate incoming patient data.

For example:

* Patient ID must be provided
* Name must be provided
* Age must be within the defined range
* Gender must match the allowed values
* Height and weight must be valid numeric values

Invalid data results in an appropriate validation error from FastAPI/Pydantic.

---

## 💾 Data Storage

For this learning project, patient information is stored in:

```text
patients.json
```

The JSON file acts as a simple data store.

> This approach is suitable for learning and experimentation. For a production application, a proper database such as PostgreSQL, MySQL, or SQLite would be more appropriate.

---

## 🎯 Learning Objectives

I built this project while learning **FastAPI** and used it to practice:

* FastAPI application setup
* API routing
* HTTP methods
* Path parameters
* Query parameters
* Pydantic models
* Field validation
* `Annotated`
* `Literal`
* Optional fields
* Computed fields
* HTTP exceptions
* JSON responses
* CRUD operations
* Data manipulation
* API documentation with Swagger and ReDoc
---
## 👨‍💻 Author

**Priyanshu Raj**

B.Tech — Computer Science & Engineering

Interested in:

* Artificial Intelligence
* Machine Learning
* Generative AI
* Python
* FastAPI
* Backend Development

---

## ⭐ Acknowledgement

This project was developed as a **learning project while studying FastAPI** and experimenting with REST API development.

If you find this project useful, feel free to ⭐ the repository.
