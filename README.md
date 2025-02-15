# Platform for pet lovers to share their furry friends

TailTales is a social network for sharing pet photos. Users have full management of their pet profiles: registration, uploading, editing, and browsing. The project consists of a Django backend and a React frontend, deployed on a server with full CI/CD automation.

## Features
- User authentication and registration
- Pet profile creation and editing
- Viewing other users' pet profiles
- File upload for pet images
- Secure API with authentication and permissions

## Tech Stack
- **Backend:** Django, Django REST Framework, Djoser, PostgreSQL
- **Frontend:** React
- **CI/CD:** GitHub Actions, Docker, Docker Compose
- **Deployment:** Nginx, Gunicorn
- **Testing:** PyTest

## Deployment Pipeline (CI/CD)
The project includes an automated CI/CD pipeline:
1. Run frontend and backend tests
2. Build and push images to Docker Hub
3. Deploy to the server
4. Send a success notification to Telegram

## Running Tests Locally
To run tests locally:
1. Create a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
   ```
2. Install dependencies:
   ```bash
   pip install -r backend/requirements.txt
   ```
3. Run tests:
   ```bash
   pytest
   ```

## Live Demo
[TailTales Live](https://kittygram-study.run.place)

## Author
[GitHub Profile](https://github.com/RockurDev)  
[Project Repository](https://github.com/RockurDev/tail_tales/)

