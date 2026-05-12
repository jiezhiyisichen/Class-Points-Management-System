# Class Points Management System

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/Flask-3.0.0-green)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

> A web-based class points management system designed for primary/secondary school teachers, supporting multi‑user isolation, visual rankings, a level system based on accumulated positive points, data import/export, and full operation logs.

👉 [中文版本](README-zh.md)

## ✨ Features

### 👥 User System
- User registration & login – each teacher manages their own class data.
- Role system: ordinary users and administrators (admin panel for user management).

### 🧑‍🎓 Student Management
- Add, edit, delete students (name, student ID, positive/negative points).
- Comments per student – add or delete notes freely.
- Data import/export (JSON format, keeps all comments).

### 🎯 Points & Level System
- **Points adjustment**: increase positive or negative points, pay (deduct positive points).
- **Level system** – based on `accrued_exp` (total positive points ever earned).
  - Gains 1 level per 10 positive points (remaining after reset operations).
  - Reset (clear points) does not affect the accumulated experience or level.

### 📊 Ranking & Visualization
- Multi‑dimension rankings: total points, positive points, negative points, and by student ID.
- Medal icons for top 3 students in total points.
- Points distribution bar chart (scrollable, shows 5 students at a time).
- Class statistics: student count, number with positive/negative points, average total points.

### 📢 Announcements
- **Global announcement** (admin‑editable Markdown, displayed via a floating button).
- **Class announcement** (Markdown support, editable per class).

### 📝 Logging & Safety
- Full operation log – records all point changes and student modifications.
- Export / clear logs.
- Lock/unlock mechanism to prevent accidental operations.

### 🎲 Extras
- Random student picker.
- Responsive design – adapts to 4K monitors as well as mobile devices.

## 🛠️ Tech Stack

| Backend | Frontend | Data Storage |
|---------|----------|---------------|
| Python 3.8+<br>Flask 3.0.0 | HTML5 / CSS3 / JavaScript<br>Tailwind CSS<br>Chart.js<br>Font Awesome | JSON files (no database required) |

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Steps
1. **Clone the repository**  
   ```bash
   git clone https://github.com/yourusername/class-points-system.git
   cd class-points-system
   ```
2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

   *Sample `requirements.txt`:*
   ```
   Flask==3.0.0
   ```

3. **Run the application**  
   ```bash
   python app.py
   ```

4. **Access the system**  
   Open your browser and go to `http://localhost:5000`

### (Optional) Intranet Penetration
Use tools like `ngrok` or `frp` to expose your local server:
```bash
ngrok http 5000
```

## 🚀 Usage Guide

### First Time?
- Register a new account – the first registered user is an **ordinary user**.
- To obtain administrator rights, please refer to the code (admin rights can be granted via the admin panel by an existing admin).  
  A default super administrator `ysc` exists in the system (password: `admin123` – **change it after first login**).

### Core Operations
| Action | Description |
|--------|-------------|
| **Add Student** | Fill in name, ID, initial points |
| **Adjust Points** | Increase positive/negative points or pay (deduct positive) – automatically updates level |
| **Rankings** | Click tabs to view total, positive, negative, or ID‑sorted lists |
| **Comments** | Click the comment icon next to a student to add/delete notes |
| **Announcements** | Use the floating button (bottom right) to view the global announcement; class announcement is edited in the settings panel |
| **Import/Export** | Export all students + comments as JSON, or import a previously exported file |
| **Logs** | View, export, or clear operation logs in the Logs panel |
| **Lock/Unlock** | Prevent accidental modifications when the system is displayed on a public screen |

## 📁 Data Storage
- All data is stored in the `data/` folder as JSON files:
  - `students.json` – student list and points
  - `users.json` – user credentials and roles
  - `logs.json` – operation logs
  - `config.json` – system settings (announcements, lock state, etc.)
- Back up the entire `data/` folder to preserve all information.

## 🔧 Configuration
- Default server port: `5000` – change in `app.py`
- Operation passwords are **no longer needed** – authentication is handled by login sessions
- The level system threshold (10 positive points per level) can be adjusted in the source code


## 🗺️ Roadmap / Future plans
- [ ] CSV import/export
- [ ] Customizable level formulas
- [ ] Student self‑service portal (view own points)
- [ ] Docker support

## 🤝 Contributing
Issues and pull requests are welcome!  
For major changes, please open an issue first to discuss what you would like to change.

## 📄 License
[MIT](LICENSE) © Class Points Team

## 🙏 Acknowledgements
- [Flask](https://flask.palletsprojects.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Chart.js](https://www.chartjs.org/)
- [Font Awesome](https://fontawesome.com/)
- [Marked.js](https://marked.js.org/)

---

**Enjoy managing your class points!** ⭐
```

