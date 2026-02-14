# 🚀 Task Smash 2.0  
### A Minimal Flask To-Do App with SQLite & SCSS Styling

<p align="center">
  <img src="https://img.shields.io/badge/Flask-2.x-black?style=for-the-badge&logo=flask" />
  <img src="https://img.shields.io/badge/SQLite-Database-blue?style=for-the-badge&logo=sqlite" />
  <img src="https://img.shields.io/badge/SQLAlchemy-ORM-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/SCSS-Styled-pink?style=for-the-badge&logo=sass" />
</p>

---

## 📌 Overview

**Task Smash 2.0** is a clean and minimal To-Do application built using:

- 🐍 **Flask**
- 🗄️ **SQLite**
- 🧠 **SQLAlchemy ORM**
- 🎨 **SCSS (Sass) Styling**
- 🧩 **Jinja2 Templating**

It allows users to:

- ➕ Add tasks  
- 📋 View all tasks  
- ✏️ Edit tasks  
- ❌ Delete tasks  
- 📅 Track creation date  

---

## 🏗️ Tech Stack

| Layer    | Technology Used |
|----------|----------------|
| Backend  | Flask |
| Database | SQLite |
| ORM      | SQLAlchemy |
| Frontend | HTML + Jinja2 |
| Styling  | SCSS (compiled to CSS) |

TaskSmash/
│
├── app.py
├── database.db
│
├── templates/
│ ├── base.html
│ ├── index.html
│ └── edit.html
│
└── static/
└── scss/
├── styles.scss
└── styles.css


---

## 🧠 Application Architecture

### 1️⃣ Database Model

```python
class MyTask(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    content = db.Column(db.String(100), nullable=False)
    complete = db.Column(db.Integer, default=0)
    created = db.Column(db.DateTime, default=datetime.utcnow)
```

Each task stores:

Unique ID

Task content

Completion status (default: 0)

Creation timestamp

## 2️⃣ Routes Overview

| Route | Method | Description |
|-------|--------|------------|
| `/` | GET | Display all tasks |
| `/` | POST | Add new task |
| `/delete/<id>` | GET | Delete a task |
| `/edit/<id>` | GET | Show edit page |
| `/edit/<id>` | POST | Update task |


🔄 Workflow

```
flowchart TD
A[User Opens App] --> B[View Tasks]
B --> C[Add Task]
B --> D[Edit Task]
B --> E[Delete Task]
C --> F[Database Updated]
D --> F
E --> F
F --> B
```

🎨 UI & Styling

The app uses SCSS variables for clean theme control:

```
$primary_color: #007bff;
$success-color: #28a745;
$bg_color: wheat;
```

Features

- Rounded cards
- Shadowed content box
- Styled action buttons
- Clean table layout

Responsive centered container

⚙️ Installation & Setup
1️⃣ Clone the Repository

```
git clone https://github.com/your-username/task-smash.git
cd task-smash
```

2️⃣ Create Virtual Environment

``` python
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
```

3️⃣ Install Dependencies

```
pip install flask flask_sqlalchemy
```

4️⃣ Run the App
```
python app.py
```


Server will start at:

```
http://127.0.0.1:5001
```

🗄️ Database

Uses SQLite

Auto-creates database.db

Tables created using:

``` python
with app.app_context():
    db.create_all()
```

## 🧩 Key Concepts Demonstrated

- Flask routing  
- Form handling with `POST`  
- URL parameters  
- SQLAlchemy ORM usage  
- Template inheritance (`base.html`)  
- Jinja loops & conditionals  
- SCSS compilation workflow  
- CRUD operations  
- MVC-like structure  


