# CareConnect360: VirtualCare Telemedicine

A full-stack telemedicine demo built with Python, Flask, SQLAlchemy and SQLite, with a Jinja2 and Bootstrap 5 front end.

## Features

- Landing page, patient and doctor registration, login and logout with hashed passwords
- Role-based dashboards for patients and doctors
- Searchable doctor directory with specialization and availability filters
- Appointment booking with time-slot checks, cancellation and doctor status updates
- Virtual consultation room (simulated: no real video or audio connection is made)
- Digital prescriptions with browser printing
- Medical records with document upload
- Billing with simulated payments and printable invoices in INR
- JSON REST endpoints under `/api`

## Setup

Requires Python 3.10 or newer.

```bash
pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:5000 in your browser.

The SQLite database `careconnect360.db` and its tables are created automatically on first start, together with sample doctors, patients, appointments, prescriptions and invoices.

Optional: set the `CARECONNECT_SECRET_KEY` environment variable to replace the development session key.

## Demo accounts

| Role    | Email                              | Password    |
|---------|------------------------------------|-------------|
| Patient | patient@careconnect360.com         | Patient@123 |
| Patient | meera@careconnect360.com           | Patient@123 |
| Doctor  | ananya.sharma@careconnect360.com   | Doctor@123  |
| Doctor  | rahul.verma@careconnect360.com     | Doctor@123  |
| Doctor  | priya.mehta@careconnect360.com     | Doctor@123  |
| Doctor  | arjun.kapoor@careconnect360.com    | Doctor@123  |
| Doctor  | neha.gupta@careconnect360.com      | Doctor@123  |

These accounts exist for demonstration only. The login page also has "Use account" buttons that fill them in.

## Project structure

- `app.py` application factory, error handling and startup
- `config.py` settings and shared constants
- `models.py` SQLAlchemy models (User, Doctor, Appointment, Prescription, MedicalRecord, Invoice)
- `routes.py` HTML pages and form handling
- `api.py` JSON REST endpoints
- `helpers.py` authentication, CSRF, slot and invoice helpers
- `validators.py` input validation
- `seed.py` sample data
- `templates/` Jinja2 pages
- `static/css/style.css`, `static/js/main.js`, `static/images/` front-end assets

## Notes

- Payments, video consultations and chat are simulations for demonstration. No real payment gateway or video service is connected.
- Uploaded documents are stored in `static/uploads/` and are visible only to the patient who uploaded them.
