```markdown
# Task Management Application

This project is a Task Management Application built using Flask, Flask-RESTful, and SQLAlchemy for the backend, and HTML, CSS, and JavaScript for the frontend.

## Project Structure

```
/task_management
  /static
    /css
      style.css
    /js
      script.js
  /templates
    index.html
  /application
    config.py
    database.py
    models.py
    notesControllerAPI.py
    notesController.py
    notesModel.py
  /db_directory
    database.sqlite3
  /__pycache__
  .gitignore
  local_run.sh
  local_setup.sh
  main.py
  README.md
  requirements.txt
```

## Getting Started

### Prerequisites

- Python 3.6+
- Virtualenv

### Setup

To set up the project locally, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/task_management.git
    cd task_management
    ```

2. Run the setup script to create a virtual environment and install dependencies:

    ```bash
    ./local_setup.sh
    ```

3. Run the application:

    ```bash
    ./local_run.sh
    ```

The application should now be running on `http://localhost:5000`.

### API Endpoints

#### Get All Tasks

- **URL:** `/tasks`
- **Method:** `GET`
- **Success Response:**
  - **Code:** 200
  - **Content:** `[{ id, name, title, description }]`

#### Create a New Task

- **URL:** `/tasks`
- **Method:** `POST`
- **Payload:**
  ```json
  {
    "name": "Task Name",
    "title": "Task Title",
    "description": "Task Description"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ id, name, title, description }`

#### Get a Single Task

- **URL:** `/tasks/<task_id>`
- **Method:** `GET`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ id, name, title, description }`

#### Update a Task

- **URL:** `/tasks/<task_id>`
- **Method:** `PUT`
- **Payload:**
  ```json
  {
    "name": "Updated Task Name",
    "title": "Updated Task Title",
    "description": "Updated Task Description"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ id, name, title, description }`

#### Delete a Task

- **URL:** `/tasks/<task_id>`
- **Method:** `DELETE`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Task deleted" }`

## Frontend

The frontend is built using HTML, CSS (Bootstrap), and JavaScript (Axios for API requests). It includes the following features:

- A landing page displaying a list of tasks.
- Ability for users to add new tasks with a name, title, and description.
- Ability for users to view detailed information about each task.
- Option to edit existing tasks.
- Option to delete tasks.
- Responsive design to ensure usability on both desktop and mobile devices.

## Running the Application

### local_setup.sh

This script creates a virtual environment and installs the necessary dependencies.

```bash
#!/bin/bash

# Create virtual environment
python3 -m venv venv

# Activate virtual environment
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### local_run.sh

This script activates the virtual environment and starts the Flask application.

```bash
#!/bin/bash

# Activate virtual environment
source venv/bin/activate

# Run the application
python main.py
```

### main.py

This is the entry point of the application.

```python
from application import create_app

app = create_app()

if __name__ == "__main__":
    app.run(debug=True)
```

### Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### License

This project is licensed under the MIT License.
```

### Explanation of Scripts

1. **local_setup.sh**:
   - Creates a virtual environment.
   - Installs the required dependencies from `requirements.txt`.

2. **local_run.sh**:
   - Activates the virtual environment.
   - Runs the Flask application.

Make sure the scripts have execute permissions:
```bash
chmod +x local_setup.sh
chmod +x local_run.sh
```

This README file provides a comprehensive overview of the project, including setup instructions, API endpoints, and scripts for running the application.