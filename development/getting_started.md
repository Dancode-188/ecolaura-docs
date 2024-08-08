# 🚀 Getting Started with Ecolaura Development



Welcome to the Ecolaura development team! We're thrilled to have you on board. This guide will help you set up your development environment and get you coding in no time. Let's build a greener future together! 🌿💻



## 📋 Prerequisites



Before we dive in, make sure you have the following installed:



- Git

- Docker and Docker Compose

- Node.js (v14 or later)

- Python (v3.8 or later)

- Your favorite code editor (we recommend VS Code with ESLint and Prettier extensions)



## 🛠️ Setting Up Your Development Environment



### 1. Clone the Repositories



```bash

git clone https://github.com/ecolaura/ecolaura-frontend.git

git clone https://github.com/ecolaura/ecolaura-backend.git

git clone https://github.com/ecolaura/ecolaura-services.git

```



### 2. Frontend Setup



```bash

cd ecolaura-frontend

npm install

cp .env.example .env

```



Edit the `.env` file with your local settings.



### 3. Backend Setup



```bash

cd ecolaura-backend

python -m venv venv

source venv/bin/activate   # On Windows use `venv\Scripts\activate`

pip install -r requirements.txt

cp .env.example .env

```



Edit the `.env` file with your local settings.



### 4. Services Setup



```bash

cd ecolaura-services

docker-compose up -d

```



This will start all the required services (PostgreSQL, Redis, Elasticsearch, etc.) in Docker containers.



## 🏃‍♂️ Running the Application



1. Start the backend:

```bash

  cd ecolaura-backend

  python manage.py runserver

```



2. In a new terminal, start the frontend:

```bash

  cd ecolaura-frontend

  npm start

```



3. Visit `http://localhost:3000` in your browser. You should see the Ecolaura homepage!



## 🧪 Running Tests



- Frontend: `npm test`

- Backend: `python manage.py test`



## 🌿 Ecolaura Development Workflow



1. **Pick a Task**: Choose an issue from our project board.

2. **Create a Branch**: `git checkout -b feature/your-feature-name`

3. **Code and Commit**: Make your changes and commit them with meaningful messages.

4. **Push and Create PR**: Push your branch and create a Pull Request for review.

5. **Code Review**: Address any feedback from the team.

6. **Merge**: Once approved, merge your PR and celebrate your contribution to sustainable e-commerce! 🎉



## 🐛 Troubleshooting



- **Issue**: Services won't start

 **Solution**: Ensure Docker is running and ports are not in use.



- **Issue**: NPM packages won't install

 **Solution**: Try deleting `node_modules` and running `npm install` again.



For more issues, check our [Common Issues](../troubleshooting/common_issues.md) page.



## 💡 Best Practices



- Follow our [Coding Standards](./coding_standards.md)

- Write tests for new features

- Keep the code DRY (Don't Repeat Yourself)

- Prioritize sustainability in your code - efficient algorithms save energy!



## 🤝 Getting Help



- Check our [API Documentation](../api/overview.md)

- Join our Slack channel #ecolaura-dev

- Don't hesitate to ask questions in our weekly dev meetings



## 🌟 Your First Task



Ready to dive in? Try this:

1. Add a "Plant a Tree" button to the user dashboard.

2. When clicked, it should call a mock API endpoint `/api/plant-tree/`.

3. Display a success message with a tree emoji 🌳.



This small feature will give you a taste of our frontend, backend, and API integration!



Remember, every line of code you write is a step towards a more sustainable future. Happy coding, and welcome to the Ecolaura family! 🌍👨‍💻👩‍💻