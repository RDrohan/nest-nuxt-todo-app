# Nest-Nuxt-Todo-App

This todo application has a Nest.js backend with SQLite data providing RESTful APIs for managing todos, while Nuxt 3 is used for the user interface to interact with the backend APIs.

## Backend APIs

- `GET /todos`: Get all todos.
- `GET /todos/:id`: Get a single todo by ID.
- `POST /todos`: Create a new todo.
- `PUT /todos/:id`: Update a todo by ID.
- `DELETE /todos/:id`: Delete a todo by ID.

## Installation

1. Clone this repository:

```bash
git clone https://github.com/RDrohan/nest-nuxt-todo-app.git
```

2. `cd` into the 'nest-nuxt-todo-app':

```bash
cd ./nest-nuxt-todo-app
```

3. Run the following command to install the dependencies on the backend

```bash
npm run install-backend
```

4. Run the following command to install the dependencies on the frontend

```bash
npm run install-frontend
```

5. Run the following command to run the server on the computer. The API should be running from [http://localhost:3000/](http://localhost:3000/)

```bash
npm run start-server
```

6. Open a second terminal and then run the following command to run the frontend application on your computer. The application should be running from [http://localhost:8000/](http://localhost:8000/)

```bash
npm run start-app
```

7. Open your browser and navigate to [http://localhost:8000/](http://localhost:8000/) to access the application.