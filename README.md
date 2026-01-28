# express-session-secure-page

A Node.js + Express application demonstrating **secure page access using `express-session`**, middleware-based authentication, and MVC architecture with EJS templating.

This project restricts access to protected views (`secure-page.ejs`) so that **only authenticated users** can access them, using session-based authentication.

---

## 🚀 Features

* Session-based authentication using **express-session**
* Middleware-based route protection (`auth.js`)
* MVC folder structure
* Secure page access control
* EJS templating engine
* Layout system for reusability
* Clean separation of concerns (Controller, Model, Middleware, Views)

---

## 📁 Project Structure

```
ASSIGN32MVC12/
│
├── src/
│   ├── controllers/
│   │   └── user.controller.js
│   ├── middleware/
│   │   └── auth.js
│   ├── models/
│   │   └── user.model.js
│   └── views/
│       ├── layout.ejs
│       ├── msgPage.ejs
│       ├── secure-page.ejs
│       ├── user-login.ejs
│       └── user-register.ejs
│
├── .gitignore
├── index.js
├── server.js
├── upload_project.js
├── package.json
└── package-lock.json
```

---

## 🔐 Authentication Flow

1. User registers via `user-register.ejs`
2. User logs in via `POST /login`
3. Session is created using `express-session`
4. User session is stored on login
5. `auth` middleware checks session status
6. Protected route `/` loads `secure-page.ejs` only if user is authenticated
7. Unauthorized users are redirected to `msgPage.ejs`

---

## 🧠 Middleware Logic (`auth.js`)

* Checks if `req.session.user` exists
* If authenticated → `next()`
* If not authenticated → render `msgPage.ejs` with error message

---

## 🔁 Protected Route Example

```js
app.get('/', auth, (req, res) => {
  res.render('secure-page');
});
```

---

## 📦 Installation

```bash
git clone https://github.com/Mrutunjaya-Panda/express-session-secure-page
cd express-session-secure-page
npm install
```

---

## ▶️ Run the Project

```bash
npm start
```

or

```bash
node server.js
```

---

## 🔑 Routes

| Method | Route     | Description             |
| ------ | --------- | ----------------------- |
| GET    | /         | Secure page (Protected) |
| POST   | /login    | User login              |
| GET    | /login    | Login page              |
| GET    | /register | Register page           |

---

## 🛡️ Security Behavior

* Non-logged-in users **cannot access** `secure-page.ejs`
* Session validation handled via middleware
* Unauthorized access redirects to `msgPage.ejs`

---

## 🧩 Tech Stack

* Node.js
* Express.js
* express-session
* EJS
* MVC Architecture

---

## 🎯 Learning Objectives

* Implement session authentication
* Use middleware for route protection
* Secure EJS views
* Apply MVC structure in Express
* Understand session lifecycle

---

## 👤 Author

**Mrutunjaya Panda**
GitHub: [https://github.com/Mrutunjaya-Panda](https://github.com/Mrutunjaya-Panda)

---

## ⭐ If you like this project
Give it a ⭐ and use it for learning authentication & session handling in Node.js!
