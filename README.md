# 📁 File Share Project

A secure file sharing platform built using Django and Django REST Framework. This project allows users to upload and download files through signed URLs with role-based access.

## 🚀 Features

- ✅ RESTful API for file upload and download
- 🔐 Secure file download using Django's `Signer` to prevent unauthorized access
- 🧑‍🤝‍🧑 Role-based access control (`OPS`, `CLIENT`, etc.)
- 🗂️ File storage using Django's default file system
- 🧪 Simple test setup using Django's test framework

## 🛠️ Tech Stack

- **Backend:** Django, Django REST Framework
- **Database:** SQLite (default Django DB)
- **Security:** Django Signer
- **API Client:** Postman or similar

## 📂 Project Structure

```
file_share_project/
├── core/
│   ├── models.py          # File model
│   ├── serializers.py     # DRF serializers
│   ├── views.py           # API views (upload/download)
│   ├── urls.py            # App URLs
│   └── migrations/
├── file_share_project/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py / asgi.py
├── db.sqlite3
└── manage.py
```

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/file-share-project.git
cd file-share-project

# Create virtual environment
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py migrate

# Run the server
python manage.py runserver
```

> ⚠️ If `requirements.txt` is not present, create it using:
> `pip freeze > requirements.txt`

## 🧪 API Endpoints

### 🔼 Upload File
**POST** `/api/upload/`

| Field       | Type   | Description            |
|-------------|--------|------------------------|
| file        | File   | File to upload         |
| user_role   | String | Role like `OPS`, `CLIENT` |

---

### 📥 Download File
**GET** `/api/download/<signed_id>/`

- Replace `<signed_id>` with the signed ID received after upload.
- Only users with the correct role can access the file.

## 🧑‍💻 Developer Notes

- Signed URLs are used via Django’s `Signer` for secure file access.
- Authentication and role validation logic can be extended as needed.

## 📃 License

This project is open-source and available under the MIT License.

---

## 🙋‍♂️ Author

Developed by Anmol Chauhan
