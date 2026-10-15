# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.


## Dynamic Portfolio Footer

The portfolio footer displays the version, current date, and author.

Example footer:

Pravin Mishra Portfolio v1.1 - Deployed on 15 Oct 2026 - By Gatadi Nagajyothi

### How the Date Works

The footer contains a `<span id="deployDate"></span>` element.
JavaScript generates the current date using the browser's Date
object and formats it as DD Mon YYYY using Intl.DateTimeFormat.
The Asia/Kolkata time zone is used for consistent display in India.

The date updates automatically whenever the page is loaded.
This implementation displays the current date rather than storing
the exact date of the last deployment.

### Code Snippet

```html
<span id="deployDate"></span>

<script>
  const today = new Date();
  document.getElementById("deployDate").textContent =
    new Intl.DateTimeFormat("en-GB", {
      day: "2-digit",
      month: "short",
      year: "numeric",
      timeZone: "Asia/Kolkata"
    }).format(today);
</script>
```
