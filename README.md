# 🗳️ Online Voting System

<div align="center">

![Django](https://img.shields.io/badge/Django-3.1.7-092E20?style=for-the-badge&logo=django&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**A secure, user-friendly online voting system built with Django**

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 About

The **Online Voting System** is a comprehensive web-based application designed to facilitate secure and transparent electronic voting. Built with Django, this system provides a complete solution for managing elections, candidates, voters, and voting processes.

### Key Highlights

- ✅ **Secure Authentication** - Custom user model with email-based authentication
- ✅ **OTP Verification** - Phone number verification for voter registration
- ✅ **Admin Dashboard** - Comprehensive admin panel for managing elections
- ✅ **Real-time Results** - Live voting results and statistics
- ✅ **Responsive Design** - Modern UI built with Bootstrap and AdminLTE
- ✅ **Multiple Positions** - Support for multiple election positions with different voting rules

---

## ✨ Features

### For Administrators

- 🏠 **Dashboard** - Overview of election statistics and activities
- 👥 **Voter Management** - Register, view, and manage voters
- 🎯 **Position Management** - Create and manage election positions
- 👤 **Candidate Management** - Add candidates with photos and bios
- 📊 **Vote Tracking** - Monitor voting progress in real-time
- 📄 **Results & Reports** - Generate and print election results
- 🔐 **Access Control** - Secure admin authentication

### For Voters

- 📝 **Registration** - Easy voter registration with email and phone
- ✅ **OTP Verification** - Secure phone number verification
- 🗳️ **Voting Interface** - Intuitive ballot interface
- 📋 **Candidate Profiles** - View candidate information and platforms
- ✅ **Vote Confirmation** - Verify your vote after submission
- 📊 **Results Viewing** - View election results after voting

### Security Features

- 🔒 **One Vote Per Voter** - Prevents duplicate voting
- 🔐 **OTP Verification** - Two-factor authentication for voters
- 🛡️ **Session Management** - Secure session handling
- 🔑 **Custom Authentication** - Email-based authentication backend

---

## 🛠️ Technology Stack

### Backend
- **Django 3.1.7** - High-level Python web framework
- **Python 3.8+** - Programming language
- **SQLite** - Default database (MySQL supported)

### Frontend
- **Bootstrap** - CSS framework
- **AdminLTE** - Admin dashboard template
- **jQuery** - JavaScript library
- **Chart.js** - Data visualization
- **Font Awesome** - Icons

### Additional Libraries
- **Pillow** - Image processing
- **django-renderpdf** - PDF generation
- **mysql-connector** - MySQL database connector

---

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/Tiwari-123/Online-voting-system.git
cd Online-voting-system
```

### Step 2: Create Virtual Environment

```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 5: Create Superuser

```bash
python manage.py createsuperuser
```

### Step 6: Run Development Server

```bash
python manage.py runserver
```

The application will be available at `http://127.0.0.1:8000/`

---

## ⚙️ Configuration

### Database Configuration

By default, the system uses SQLite. To switch to MySQL, update `e_voting/settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'e_voting',
        'HOST': '127.0.0.1',
        'USER': 'root',
        'PASSWORD': 'your_password'
    }
}
```

### OTP Configuration

In `e_voting/settings.py`, you can enable/disable OTP sending:

```python
SEND_OTP = True  # Set to False to use '0000' as default OTP for testing
```

### Static Files

Static files are configured in `settings.py`. For production, run:

```bash
python manage.py collectstatic
```

### Media Files

Media files (candidate photos) are stored in the `media/` directory. Ensure proper permissions are set.

---

## 🚀 Usage

### Admin Access

1. Navigate to `http://127.0.0.1:8000/admin/`
2. Login with your superuser credentials
3. Access the admin dashboard for:
   - Managing voters
   - Creating positions
   - Adding candidates
   - Viewing results

### Voter Registration

1. Go to the registration page
2. Fill in your details (email, name, phone)
3. Verify your phone number with OTP
4. Complete registration

### Voting Process

1. Login with your voter credentials
2. View the ballot with all positions and candidates
3. Select your preferred candidates
4. Review your selections
5. Submit your vote
6. View confirmation

---

## 📁 Project Structure

```
OnlineVoting-Django/
│
├── account/                 # User authentication app
│   ├── models.py           # Custom user model
│   ├── views.py            # Authentication views
│   └── middleware.py       # Account middleware
│
├── administrator/           # Admin dashboard app
│   ├── templates/          # Admin templates
│   ├── views.py            # Admin views
│   └── models.py           # Admin models
│
├── voting/                  # Voting functionality app
│   ├── models.py           # Voter, Position, Candidate, Votes models
│   ├── views.py            # Voting views
│   ├── forms.py            # Voting forms
│   └── templates/          # Voting templates
│
├── e_voting/                # Main project settings
│   ├── settings.py         # Django settings
│   ├── urls.py             # Main URL configuration
│   └── wsgi.py             # WSGI configuration
│
├── static/                  # Static files (CSS, JS, images)
│   ├── css/                # Stylesheets
│   ├── js/                 # JavaScript files
│   └── bower_components/   # Third-party libraries
│
├── media/                   # User-uploaded files
│   └── candidates/         # Candidate photos
│
├── src/                     # React/TypeScript source (if applicable)
│
├── manage.py                # Django management script
├── requirements.txt         # Python dependencies
└── README.md               # This file
```

---

## 📸 Screenshots

### Admin Dashboard
![Admin Dashboard](https://via.placeholder.com/800x400?text=Admin+Dashboard)

### Voting Interface
![Voting Interface](https://via.placeholder.com/800x400?text=Voting+Interface)

### Results Page
![Results](https://via.placeholder.com/800x400?text=Election+Results)

> **Note:** Add your actual screenshots to the repository and update these placeholders.

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Contribution Guidelines

- Follow PEP 8 style guidelines for Python code
- Write clear commit messages
- Add comments to complex code sections
- Update documentation as needed
- Test your changes thoroughly

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Tiwari-123**

- GitHub: [@Tiwari-123](https://github.com/Tiwari-123)
- Repository: [Online-voting-system](https://github.com/Tiwari-123/Online-voting-system)

---

## 🙏 Acknowledgments

- Django community for the excellent framework
- AdminLTE for the beautiful admin template
- All contributors and users of this project

---

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/Tiwari-123/Online-voting-system/issues) page
2. Create a new issue with detailed information
3. Provide steps to reproduce the problem

---

<div align="center">

**⭐ If you find this project helpful, please consider giving it a star! ⭐**

Made with ❤️ using Django

</div>

