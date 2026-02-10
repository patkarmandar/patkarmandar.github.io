+++
title = "Child Immunization Chart Generator and Tracking System"
date = 2022-02-20
description = "Child Immunization Chart Generator and Tracker System in Core PHP."
github = "https://github.com/patkarmandar/Child-Immunization-System" # Optional
demo = "" # Optional
tags = ["php", "application"]
categories = ["web"]
featured = false
+++

The Child Immunization Chart Generator and Tracking System is a web-based healthcare management system built using Core PHP. It helps parents, hospitals, and clinics digitally manage child vaccination schedules, track immunization history, and receive automated reminders via email and SMS.

This application is designed to reduce missed vaccinations, improve record management, and streamline communication between parents and healthcare providers.

### Technology Stack & Integrations
- Backend: Core PHP
- Local Development Stack: XAMPP (Apache, MySQL, PHP)
- Task Scheduler: Cron Jobs
- Email Service: PHPMailer (SMTP-based email notifications)
- SMS Service: ITEXMO SEND SMS API
- Environment Management: phpdotenv (for secure configuration and secrets handling)

### Key Highlights
- Automated vaccination reminders using Cron Jobs
- Email notifications via PHPMailer
- SMS alerts via ITEXMO SEND SMS API
- Secure configuration using phpdotenv
- Role-based access for parents, hospitals, and doctors

### Features
- Immunization Chart Management
    - Digital vaccination records with vaccine name, administered date, and next due date.
- Automated Reminders
    - Email notifications via PHPMailer.
    - SMS alerts via ITEXMO SEND SMS API.
    - Cron-based scheduling for automated execution.
- Parent & Child Management
    - Parents can manage multiple child profiles.
    - Individual immunization history per child.
- Hospital / Doctor Management
    - Hospitals and clinics can add and manage doctor profiles.
- Nutrition Guidance
    - Age-based nutrition recommendations for children.

### Prerequisites
- XAMPP (PHP 7.4+)
- Composer
- MySQL

### Installation
1. Clone and setup project
    ```
    git clone https://github.com/patkarmandar/Child-Immunization-System.git
    cd Child-Immunization-System
    composer install
    ```
2. Move the project to: `C:\xampp\htdocs\`
3. Start Apache and MySQL from XAMPP.
4. Create a MySQL database and import the provided SQL file.
5. Configure environment variables using .env.
6. (Optional) Set up a cron job for reminder automation.

Access the application at: `http://localhost/child-immunization-tracker`
