# 🚀 Portfolio Blog (Django)

A full-stack **Portfolio Blog Web Application** built using **Django**, where users can view posts, explore content, and manage blogs with a clean UI.

---

## 🌐 Live Demo

👉 Add your deployed link here (from Render)

---

## 🛠️ Tech Stack

* **Backend:** Django
* **Frontend:** HTML, CSS, Tailwind
* **Database:** PostgreSQL / SQLite
* **Server:** Gunicorn
* **Static Handling:** WhiteNoise
* **Deployment:** Render

---

## 📂 Project Structure

```
Portfolio_Blog/
├── manage.py
├── requirements.txt
├── Procfile
├── runtime.txt
├── portfolio_blog/   # Main Django project
├── core/             # App
├── templates/
├── static/
```

---

## ⚙️ Local Setup

### 1️⃣ Clone Repository

```
git clone https://github.com/Student-aditya123/Portfolio_Blog.git
cd Portfolio_Blog
```

### 2️⃣ Create Virtual Environment

```
python -m venv .venv
.venv\Scripts\activate   # Windows
```

### 3️⃣ Install Dependencies

```
pip install -r requirements.txt
```

### 4️⃣ Run Server

```
python manage.py runserver
```

---

## 🚀 Deployment on Render (Step-by-Step)

### 🔹 1. Push Code to GitHub

Make sure your project contains:

* `requirements.txt`
* `Procfile`
* `runtime.txt`

---

### 🔹 2. Create Web Service on Render

Go to **Render Dashboard** → New Web Service → Connect GitHub repo

---

### 🔹 3. Configure Settings

* **Build Command:**

```
pip install -r requirements.txt && python manage.py collectstatic --noinput
```

* **Start Command:**

```
gunicorn portfolio_blog.wsgi:application
```

* **Root Directory:**

```
(leave empty)
```

---

### 🔹 4. Add Environment Variables

In Render Dashboard → Environment:

```
DEBUG=False
SECRET_KEY=your-secret-key
ALLOWED_HOSTS=your-app.onrender.com
```

(If using PostgreSQL / Cloudinary, add their credentials here)

---

### 🔹 5. Static Files Setup

In `settings.py`:

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
```

Run:

```
python manage.py collectstatic
```

---

### 🔹 6. Use WhiteNoise

Install:

```
pip install whitenoise
```

Add in `settings.py`:

```python
MIDDLEWARE = [
    'whitenoise.middleware.WhiteNoiseMiddleware',
]
```

---

### 🔹 7. Deploy 🚀

Click:

```
Manual Deploy → Deploy latest commit
```

---

## 🖼️ Media Files (Images)

For production, use cloud storage like:

* Cloudinary (recommended)

---

## ❗ Common Errors & Fixes

| Error                    | Solution                                 |
| ------------------------ | ---------------------------------------- |
| requirements.txt missing | Run `pip freeze > requirements.txt`      |
| ModuleNotFoundError      | Install dependency + update requirements |
| Static not loading       | Run collectstatic + use WhiteNoise       |
| Gunicorn error           | Check correct project name               |

---

## 📌 Future Improvements

* User Authentication
* Blog CRUD functionality
* Comment System
* Cloudinary integration for images

---

## 👨‍💻 Author

**Aditya Singh**
B.Tech CSE | Aspiring Backend Developer

---

## ⭐ Show Your Support

If you like this project, give it a ⭐ on GitHub!
