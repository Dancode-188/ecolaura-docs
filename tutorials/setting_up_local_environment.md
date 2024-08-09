# 🌱 Setting Up Your Ecolaura Local Environment



Welcome, eco-warrior developer! This guide will help you set up your local environment for Ecolaura development. Just as we carefully prepare soil for planting, we'll prepare your machine for cultivating sustainable code. Let's get your digital garden ready! 🌿💻



## 🧰 Prerequisites



Before we begin, ensure you have the following tools installed:



- Git (v2.30 or later)

- Docker (v20.10 or later)

- Docker Compose (v1.29 or later)

- Node.js (v14 or later)

- Python (v3.8 or later)

- Visual Studio Code (recommended IDE)



## 🌳 Clone the Repository



1. Open your terminal and navigate to your preferred project directory.

2. Clone the Ecolaura repository:



```bash

git clone https://github.com/ecolaura/ecolaura.git

cd ecolaura

```



## 🌊 Setting Up Docker Services



We use Docker to ensure consistent development environments across the team.



1. Build and start the Docker containers:



```bash

docker-compose up -d

```



This command will set up containers for:

- PostgreSQL database

- Redis cache

- Elasticsearch

- RabbitMQ



2. Verify that all containers are running:



```bash

docker-compose ps

```



## 🌿 Backend Setup



1. Create a Python virtual environment:



```bash

python -m venv venv

source venv/bin/activate # On Windows, use `venv\Scripts\activate`

```



2. Install backend dependencies:



```bash

cd backend

pip install -r requirements.txt

```



3. Set up environment variables:



```bash

cp .env.example .env

```



Edit the `.env` file with your local settings.



4. Run database migrations:



```bash

python manage.py migrate

```



5. Create a superuser:



```bash

python manage.py createsuperuser

```



6. Start the Django development server:



```bash

python manage.py runserver

```



The backend should now be running at `http://localhost:8000`.



## 🌻 Frontend Setup



1. Navigate to the frontend directory:



```bash

cd ../frontend

```



2. Install frontend dependencies:



```bash

npm install

```



3. Set up environment variables:



```bash

cp .env.example .env.local

```



Edit the `.env.local` file with your local settings.



4. Start the frontend development server:



```bash

npm run dev

```



The frontend should now be accessible at `http://localhost:3000`.



## 🔧 Development Tools Setup



### Linters and Formatters



1. Install pre-commit hooks:



```bash

pip install pre-commit

pre-commit install

```



2. Install ESLint and Prettier extensions in VS Code.



3. Configure VS Code to use the project's ESLint and Prettier configurations:



```json

// .vscode/settings.json

{

 "editor.formatOnSave": true,

 "editor.codeActionsOnSave": {

  "source.fixAll.eslint": true

 },

 "python.linting.pylintEnabled": true,

 "python.linting.enabled": true

}

```



### Database Tools



1. Install the PostgreSQL extension in VS Code for easy database management.



2. Connect to the database using the credentials in your `.env` file.



## 🧪 Running Tests



### Backend Tests



```bash

cd backend

python manage.py test

```



### Frontend Tests



```bash

cd frontend

npm run test

```



## 🌡️ Health Checks



Ensure all services are running correctly:



1. Backend API: `http://localhost:8000/api/health-check`

2. Frontend: `http://localhost:3000`

3. Database: `docker-compose exec db psql -U ecolaura -c "SELECT 1;"`

4. Redis: `docker-compose exec redis redis-cli ping`

5. Elasticsearch: `curl http://localhost:9200`

6. RabbitMQ: `http://localhost:15672` (use guest/guest for credentials)



## 🐛 Troubleshooting Common Issues



1. **Port conflicts**: Ensure no other services are using the required ports.

  Solution: Stop conflicting services or change ports in `docker-compose.yml`.



2. **Database connection issues**: Verify database credentials in `.env`.

  Solution: Double-check the `DATABASE_URL` in your `.env` file.



3. **Node module issues**: Clear npm cache and reinstall.

  Solution:

```bash

  npm cache clean --force

  rm -rf node_modules

  npm install

```



4. **Docker container fails to start**: Check Docker logs.

  Solution: `docker-compose logs [service_name]`



## 🌱 Best Practices



1. Regularly pull the latest changes from the main branch.

2. Update your dependencies frequently:

```bash

  pip install -r requirements.txt

  npm update

```

3. Keep your Docker images up to date:

```bash

  docker-compose pull

  docker-compose up -d --build

```

4. Use virtual environments for Python to isolate dependencies.

5. Follow the Git workflow outlined in our documentation.



## 🚀 Next Steps



Congratulations! Your local Ecolaura environment is now set up. Here are some next steps:



1. Familiarize yourself with our [coding standards](../development/coding_standards.md).

2. Review our [Git workflow](../development/git_workflow.md).

3. Check out the [API documentation](../api/overview.md).

4. Join our developer chat on Slack for any questions or discussions.



Remember, a well-maintained local environment is the foundation for growing robust, sustainable code. Happy coding, eco-warrior! 🌿💻🌍



## 🤝 Contributing to This Guide



If you encounter any issues or have suggestions for improving this setup guide, please:



1. Open an issue in our GitHub repository.

2. Propose changes via a pull request.

3. Discuss improvements in our developer forum.



Together, we can make the onboarding process as smooth as a leafy sea dragon gliding through a kelp forest! 🐉🌊