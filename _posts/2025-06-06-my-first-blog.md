---
title: "MY First Blog"
date: 2025-06-06
---

When working with APIs in modern web development, you’ll eventually run into something called **CORS** — and it can be frustrating if you don’t understand what’s going on.

In this post, we’ll break down **what CORS is**, **why it exists**, and **how to handle it** in your projects.

---

## 🌐 What is CORS?

**CORS** stands for **Cross-Origin Resource Sharing**. It's a browser security feature that **restricts web pages from making requests to a different domain than the one that served the web page**.

In other words, if your site is running on `https://my-frontend.com` and it tries to fetch data from `https://my-backend.com`, the browser will **block the request by default** — unless the backend explicitly allows it using CORS headers.

---

## 🚫 Why CORS Exists

CORS is designed to **protect users from malicious websites** trying to interact with APIs they shouldn’t have access to — like your bank or email provider.

Before CORS, the **Same-Origin Policy (SOP)** was strict: browsers didn’t allow any cross-origin requests at all. CORS is a **relaxation of SOP**, but only under safe, controlled conditions.

---

## ✅ How CORS Works

When your frontend sends a request to another origin, the browser:

1. **Sends a preflight request** (for certain request types like `POST`, `PUT`, or requests with custom headers).
2. The server must respond with specific headers like:

```http
Access-Control-Allow-Origin: https://my-frontend.com
Access-Control-Allow-Methods: GET, POST
Access-Control-Allow-Headers: Content-Type
