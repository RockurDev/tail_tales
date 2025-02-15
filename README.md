# Platform for pet lovers to share their furry friends

Social network for sharing pet photos. Users have full management of their pet profiles: registration, uploading, editing, and browsing. The project consists of a Django backend and a React frontend, deployed on a server with full CI/CD automation.

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

## Docker Compose Configuration
```yaml
volumes:
  static:
  media:
  pg_data:

services:
  db:
    container_name: db
    env_file: .env
    image: postgres:13.10
    volumes:
      - pg_data:/var/lib/postgresql/data

  backend:
    env_file: .env
    image: rockur/kittygram_backend
    volumes:
      - static:/static
      - media:/app/media
    depends_on:
      - db

  frontend:
    env_file: .env
    image: rockur/kittygram_frontend
    command: cp -r /app/build/. /static/
    volumes:
      - static:/static

  gateway:
    env_file: .env
    image: rockur/kittygram_gateway
    volumes:
      - static:/static
      - media:/media
    ports:
      - 9000:80
    depends_on:
      - db
      - backend
```

## Automated Testing
To verify project functionality using automated tests:
1. In the project root, create a `tests.yml` file with the following content:
   ```yaml
   repo_owner: your_github_username
   kittygram_domain: https://kittygram-study.run.place
   taski_domain: https://your_taski_project_url
   dockerhub_username: your_dockerhub_username
   ```
2. Copy the contents of `.github/workflows/main.yml` to `kittygram_workflow.yml` in the root directory.

## Live Demo
[Kittygram Live](https://kittygram-study.run.place)

## Author
[GitHub Profile](https://github.com/RockurDev)  
[Project Repository](https://github.com/RockurDev/kittygram/)

