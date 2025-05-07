# Beginner’s Guide to Building Your First Python Web App with Flask

## Introduction

Flask is a lightweight Python web framework that’s perfect for beginners who want to start building web apps. In this guide, we’ll walk you through building a simple "Hello, World!" app using Flask.

By the end of this tutorial, you’ll have a running web server and a basic understanding of how Flask routes and responses work.

---

## 1. What is Flask?

Flask is a micro web framework for Python. Unlike Django, it doesn’t come with built-in features like authentication or database abstraction, making it ideal for smaller or more flexible projects.

Key features:
- Lightweight and easy to learn
- Flexible architecture
- Tons of extensions available

---

## 2. Installing Flask

First, make sure Python and pip are installed. Then run:

```bash
pip install flask
```

You can now start building your app!

---

## 3. Building Your First Web App

Create a file called `app.py` and add the following code:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, World!"

if __name__ == "__main__":
    app.run(debug=True)
```

This app creates a basic web server that listens on `http://127.0.0.1:5000/`.

---

## 4. Running Your Flask App

Open a terminal and run:

```bash
python app.py
```

You should see output like:

```
* Running on http://127.0.0.1:5000/
```

Open that URL in your browser and you’ll see your app in action!

---

## 5. Next Steps

Once you're comfortable with this, you can:
- Add new routes (`@app.route("/about")`)
- Use HTML templates with Jinja2
- Connect to databases like SQLite or PostgreSQL
- Deploy to cloud platforms like Heroku or Render

---

## Final Thoughts

Flask is a powerful entry point into web development with Python. With just a few lines of code, you can launch fully functional apps and grow your skill set into backend development, APIs, and more.

Whether you're building a portfolio or starting a serious project, Flask is a fantastic place to begin.

---

*Written by Erik Irawan — aspiring full-stack developer and Python enthusiast.*
