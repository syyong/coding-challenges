# Task management panel 

This project consists of:
- a Django and FastAPI backend
- a React frontend

## To start the application locally
### The backend server
***Requirements***: Python 3.10+

First create a virtual environment and install the dependencies:

```shell
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
The application uses SQLite by default, please refer to `settings/base.py`. To populate the initial database tables using the migration command:

```shell
./manage.py migrate
```
Run the server locally using `uvicorn`:

```shell
gunicorn task_tracking.main:app -k uvicorn.workers.UvicornWorker
```

The [auto-generated docs](https://fastapi.tiangolo.com/features/#automatic-docs) proivded by FastAPI are available at http://localhost:8000/docs

The [model admin](https://docs.djangoproject.com/en/4.0/ref/contrib/admin/) provided by Django is availabe at http://localhost:8000/admin

### The frontend server
```shell
cd frontend 
npm install
npm start
```
***Note***: The `Upload file` button functionality is not implemented

## Create tasks
You can create tasks using 

http://localhost:8000/docs

or

using the Django admin panel.
The set up:
```
cd backend
# make a copy of .env.dist and named it .env
./manage.py createsuperuser #create a super user for the django admin
./manage.py runserver
```
Login to:

http://localhost:8000/admin

Click "+ Add" at the admin panel:
![Django admin panel](/django-admin-panel.png?raw=true "Django admin panel")