# Django Sports Matchmaking & Team Management Web Application

A full-featured **Django web application** designed for team creation, real-time opponent searching, sports category selection, match challenges, chat messaging, and live notifications using **Django Channels (WebSockets)**.

This system allows users to:

* Create & manage teams
* Choose sports categories
* Search opponents based on **distance (Haversine formula)**
* Send/receive match challenges
* Chat with teams in real time
* Receive instant notifications via **WebSockets**
* View stats, history, streaks, and dashboard
* Manage team members and admins

---

## 🚀 Features

### **1. Team Management**

* Create or join teams
* Add/remove players
* Assign multiple admins
* Track played, won, and lost matches
* Update team logos and details

### **2. Sports Category Selection**

* Choose a category before playing (football, cricket, etc.)
* Category saved and synchronized via WebSockets

### **3. Opponent Search (Distance Based)**

* Uses **Haversine formula** to calculate nearby teams
* Filter by radius (e.g., 10km, 20km)
* Displays team logos, categories, and locations

### **4. Match Challenging System**

* Send match challenges to other teams
* Accept/reject challenges
* Match status updates in real time
* Stores match history with timestamps

### **5. Real-Time Notifications 🔔**

Powered by **Django Channels**:

* New message notifications
* Challenge updates
* Team member updates
* Category selection updates

### **6. Real-Time Chat System 💬**

* One-to-one chat rooms
* Auto-scrolling message area
* WebSocket-based delivery

### **7. Player Management**

* View players list
* Assign captain
* Invite players

### **8. Admin Panel Customization**

* Notification groups
* WebSocket routing
* Signal handling for notifications

---

## 🧩 Tech Stack

### **Backend**

* Django
* Django Channels
* Python WebSockets
* ASGI Server

### **Frontend**

* HTML, CSS, JS
* Bootstrap (if used)
* WebSocket JS API

### **Database**

* SQLite / PostgreSQL (depending on user setup)

### **Real-Time Layer**

* Channels
* Redis (optional if used for channel layer)

---

## 🗂 Project Structure (Simplified)

*(Based on provided files — may vary depending on full project)*

```
project_root/
│   manage.py
│   routing.py
│
├── app/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── signals.py
│   ├── utils.py
│   ├── consumers.py
│   ├── routing.py
│   ├── templates/
│   │   └── home.html
│   └── static/
└── ...
```

---

## ⚙️ Installation & Setup

### **1. Clone the Repository**

```
git clone <repo-url>
cd project_root
```

### **2. Create a Virtual Environment**

```
python -m venv env
source env/bin/activate  # Linux/Mac
env\Scripts\activate     # Windows
```

### **3. Install Dependencies**

Since requirements.txt wasn't available, install manually:

```
pip install django\pip install channels
pip install daphne
```

*(Add other packages as necessary)*

### **4. Run Migrations**

```
python manage.py migrate
```

### **5. Start Development Server**

```
python manage.py runserver
```

### **6. Start ASGI Server (if needed)**

```
daphne project_root.asgi:application
```

---

## 🔌 WebSocket Endpoints

### Team Notifications

```
ws://<host>/ws/notification/<team_id>/
```

### Chat

```
ws://<host>/ws/chat/<room_name>/
```

### Category Selection Updates

```
ws://<host>/ws/category/<team_id>/
```

---

## 📡 Signal Triggers

* On team creation → send notification
* On challenge sent → notify opponent
* On challenge accepted/rejected → broadcast update
* On message sent → push WebSocket event

---

## 📈 Future Improvements

* Push notifications (mobile/web)
* Team ranking algorithm
* Tournament mode
* Admin analytics dashboard
* Video highlights sharing

---

## 👨‍💻 Author

Developed during internship & employment period:

* **Internship:** July 07 – October 09
* **Job Position:** Data Analytics Intern → Data Analyst (Oct 11 – Present)

---

## ⭐ Support

If you like this project, please ⭐ the repo!
