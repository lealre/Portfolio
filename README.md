# Hello! I'm Renan :wave:

Welcome to my portfolio repository!

Here, I showcase all my public projects. Feel free to explore and get in touch if you have any questions.

You can reach out to me using the links below:

<a href="mailto:renaanvp@gmail.com" target="_blank">
    <img src="https://img.shields.io/badge/-renaanvp@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail Badge" />
</a>
<a href="https://www.linkedin.com/in/renanheckert/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Linkedin Badge" />
</a>

## Table of contents

- [Web App for a Digital Book Collection Using FastAPI for Backend and React for Frontend](#web-app-for-a-digital-book-collection-using-fastapi-for-backend-and-react-for-frontend)
- [Backend API for a Digital Book Collection with JWT Authentication Using FastAPI](#backend-api-for-a-digital-book-collection-with-jwt-authentication-using-fastapi)
- [A Basic To-Do App Built with the Django Framework](#a-basic-to-do-app-built-with-the-django-framework)
- [Orchestrating an ETL with Airflow - From Google Drive to PostgreSQL](#orchestrating-an-etl-with-airflow---from-google-drive-to-postgresql)
- [Rental Properties CRUD Catalog with SQLAlchemy, FastAPI, Streamlit, and AWS Deploy](#rental-properties-crud-catalog-with-sqlalchemy-fastapi-streamlit-and-aws-deploy)
- [Property Sales Dashboard Using Real Data Crawled from Real Estate Website - HTTPX, MongoDB, and Dash-Plotly](#property-sales-dashboard-using-real-data-crawled-from-real-estate-website---httpx-mongodb-and-dash-plotly)
- [Analytic Report with SQL - Northwind Database](#analytic-report-with-sql---northwind-database)
- [Automating Northwind Database Operations Using PL/pgSQL - Stored Procedures and Triggers](#automating-northwind-database-operations-using-plpgsql---stored-procedures-and-triggers)

---

## Web App for a Digital Book Collection using FastAPI for Backend and React for Frontend

This project consists of a web application for a simplified version of a digital book collection.

- 💻 **Backend**
  - [FastAPI](https://fastapi.tiangolo.com/) for the Python backend API, with asynchronous routes.
  - [SQLAlchemy](https://www.sqlalchemy.org/) for Python SQL database interactions (ORM).
  - [Pydantic](https://docs.pydantic.dev/latest/), used by FastAPI, for data validation and settings management.
  - PostgreSQL as the SQL database, using the [Asyncpg](https://magicstack.github.io/asyncpg/current/) driver.
  - Tests with [Pytest](https://docs.pytest.org/en/stable/) and [Testcontainers](https://testcontainers-python.readthedocs.io/en/latest/).
  - [Pre-commit](https://pre-commit.com/) with [Ruff](https://docs.astral.sh/ruff/) for linting.
  - CI (Continuous Integration) based on GitHub Actions.
- 🌐 **Frontend**

  - [React](https://react.dev/) using TypeScript and Vite.
  - [Chakra UI](https://www.chakra-ui.com/) for frontend components.
  - [Axios](https://axios-http.com/docs/intro) to handle the backend API requests.
  - [React Hook Form](https://react-hook-form.com/) to handle the submission of data in forms.

- 🔒 Secure password hashing by default.
- 🔑 JWT (JSON Web Token) authentication.
- 🐋 Docker Compose for running all services together, including the PostgreSQL database.

<img src = 'media/madr_full/madr-full-demo.gif' />

### Tools used

<div style="display: flex; gap: 40px;">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original-wordmark.svg" height=100>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original-wordmark.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" height=100/>
    <img src="media/pydantic.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlalchemy/sqlalchemy-original-wordmark.svg" height=100/> 
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytest/pytest-plain-wordmark.svg" height=100 /> 
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>      
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/axios/axios-plain-wordmark.svg"  height=100/>
          
</div>

### How it works

It is an extension of [this repo](https://github.com/lealre/madr-fastapi).

The app serves as a simple catalog of authors and books, where you can only register a book if an author is already registered. The dashboard area allows users to switch between author and book tabs, select records to delete in batch, add new records by opening a modal, and search for specific records. The search functionality enables searching by book or author name, based on the currently active tab.

On the frontend, the JWT is stored in local storage. The dashboard area is a protected page requiring authentication, where users must log in to manage the collection records.

See the full project repository [here](https://github.com/lealre/madr-fullstack).

---

## Backend API for a Digital Book Collection with JWT Authentication Using FastAPI

This project consists of a backend API developed using [FastAPI](https://fastapi.tiangolo.com/) for a simplified version of a digital book collection.

<img src = 'media/madr/madr.gif' />

It's called MADR (Mader), a Portuguese acronym for "Meu Acervo Digital de Romances" (My Digital Collection of Romances), and it allows user registration and all CRUD operations for both authors and books.

It is built using the FastAPI framework, with [Pydantic](https://docs.pydantic.dev/latest/) responsible for data validation. It uses a PostgreSQL database, and [SQLAlchemy](https://www.sqlalchemy.org/) is used for ORM, with [Alembic](https://alembic.sqlalchemy.org/en/latest/) handling database migrations during the development process.

JWT (JSON Web Token) is used as a Bearer token for authorization and authentication in API operations, such as creating, updating, and deleting records. The JWT is included in the Authorization header of HTTP requests as a Bearer token.

The tests have 100% coverage in the `src` folder using [pytest](https://docs.pytest.org/en/stable/) and [pytest-cov](https://pytest-cov.readthedocs.io/en/latest/). It also uses [factory-boy](https://factoryboy.readthedocs.io/en/stable/) to handle massive creation of models, [freezegun](https://github.com/spulec/freezegun) to test token expiration, and [testcontainers](https://testcontainers.com/guides/getting-started-with-testcontainers-for-python/) to build a PostgreSQL instance during tests.

It is possible to run it locally using Docker Compose, which creates all the tables in PostgreSQL. A CI routine was also implemented using GitHub Actions.

### Tools used

<div style="display: flex; gap: 40px;">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original-wordmark.svg" height=100>
    <img src="media/pydantic.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlalchemy/sqlalchemy-original-wordmark.svg" height=100/> 
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytest/pytest-plain-wordmark.svg" height=100 /> 
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>      
          
</div>

### How it works

The API has 4 main routes:

The `/auth` route is used for user login and generates the access token responsible for authorizing and authenticating some of the CRUD operations. It is also possible to refresh the token, which is set to last 60 minutes by default.

The `/user` route is used to create a user and manage the account.

The `/book` route is responsible for the CRUD operations related to books.

The `/author` route is responsible for the CRUD operations related to authors.

See the full project repository [here](https://github.com/lealre/madr-fastapi).

---

## A Basic To-Do App Built with the Django Framework

A basic to-do app built with the Django framework. It features a simple interface to add, edit, and delete to-dos. In the trash area, you can either restore a to-do or permanently delete it.

Below is a quick demonstration of the app in action.

<img src = 'media/django_todo/demo.gif' />

It uses function-based views and includes some JavaScript to enable frontend interactions.

Although it does not test every aspect of the application, it achieves 100% coverage using [pytest-cov](https://pytest-cov.readthedocs.io/en/latest/). The tests also utilize [pytest](https://docs.pytest.org/en/stable/).

It’s possible to run this app using Docker Compose, which automatically creates a superuser and uses a local PostgreSQL database. The PostgreSQL database is also set up within Docker Compose.

### Tools used

<div style="display: flex; gap: 40px;">
    <img src="media/django.svg" height=100>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-plain-wordmark.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-plain-wordmark.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytest/pytest-plain-wordmark.svg" height=100 /> 
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>            
</div>

<br></br>

See the full project repository [here](https://github.com/lealre/todo-django).

---

## Orchestrating an ETL with Airflow - From Google Drive to PostgreSQL

An ETL orchestration using Airflow, extracting CSV files from a folder in Google Drive, transforming values, and storing them in a PostgreSQL database.

<img src="media/airflow_project/etl-diagram.png"/>

The data is handled in a pandas DataFrame format, and all the data validation is performed using the Pandera library, a Pydantic-based library to validate DataFrame schemas. By setting a specific data contract, validations occur in two phases: when extracted and when transformed.

The Airflow implementation was created using the Astro CLI, the command line interface for data orchestration from Astronomer.

### Tools used

<div style="display: flex; gap: 40px;">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlalchemy/sqlalchemy-original-wordmark.svg" height=100/>     
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original-wordmark.svg" height=100/>
    <img src="media/pandera.svg" height=40/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytest/pytest-plain-wordmark.svg" height=100 />      
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/apacheairflow/apacheairflow-original-wordmark.svg" height=150/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>      
          
</div>

### How it works

Task 01: Connect with Google Drive API and extract CSV files

Task 02: Validate extracted data

Task 03: Transform data and validate it

Task 04: Load data in database

See the full project repository [here](https://github.com/lealre/etl-airflow?tab=readme-ov-file).

---

## Rental Properties CRUD Catalog with SQLAlchemy, FastAPI, Streamlit, and AWS Deploy

Web application for performing asynchronous CRUD operations on a PostgreSQL database using FastAPI, SQLAlchemy, Pydantic, Streamlit, and Docker.

<img src="media/crud_project/demo.gif" />

### Tools used

<div style="display: flex; gap: 40px;">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/streamlit/streamlit-original-wordmark.svg" height=100 />          
    <img src="media/pydantic.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlalchemy/sqlalchemy-original-wordmark.svg" height=100/>     
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original-wordmark.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original-wordmark.svg" height=100>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>      
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" height=100/>
</div>
          
### How it works

The project was built in a way where three services communicate with each other separately: database, backend, and frontend. Docker Compose was used to orchestrate the containers, allowing the frontend to communicate with the backend through the API once each one is running in independent containers.

In each of these operations, the frontend sends a request to the API created using FastAPI. The API is responsible for communicating with the backend and sending a response back to the frontend to display the result of the CRUD operation. In the first layer, Pydantic is used to validate all the inputs, ensuring that the schema the user is trying to send matches the database table schema. If it doesn't match, an error message is displayed to the user.

After [Pydantic](https://docs.pydantic.dev/latest/) validation is completed, [SQLAlchemy](https://www.sqlalchemy.org/) is used to communicate with PostgreSQL and perform one of the CRUD operations in the database.

[Alembic](https://alembic.sqlalchemy.org/en/latest/) was also used to perform database migrations, and [Pytest](https://docs.pytest.org/en/stable/) was used to perform some basic tests on asynchronous backend routes.

<img src="media/crud_project/diag.png"/>

See the full project repository [here](https://github.com/lealre/crud-rental-properties).

---

## Property Sales Dashboard Using Real Data Crawled from Real Estate Website - HTTPX, MongoDB, and Dash-Plotly

This repository consists of an implementation of a dashboard containing data scraped from a real estate website: [Imovirtual](https://www.imovirtual.com/), a Portuguese real estate website offering homes, apartments, and other properties for sale and rent.

Using MongoDB as the database, it crawls raw data, cleans it, and makes it ready to be used in the dashboard.

<img src="media/web_crawler/demo.gif" />

### Tools used

<div style="display: flex; gap: 40px;">   
    <img src="media/requests.svg" height=100/> 
    <img src="media/bs4.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg"  height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/plotly/plotly-original-wordmark.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-plain-wordmark.svg" height=100/>
</div>
          
### How it works

The project is divided into two blocks that can work separately:

- **Data Ingestion**

Responsible for crawling the data, consolidating it in the database while avoiding duplicates, and preparing the data for use in the dashboard.

The raw collection, which comes from the crawler, can store data in MongoDB, an AWS S3 bucket as a JSON file, or locally as a JSON file, depending on the settings in the .env file.

For the data used in the dashboard, a new collection is created. This pipeline extracts data from one of the previous collections (raw or consolidated), filters and transforms it so that it is ready for use in the dashboard.

For this specific website, it was possible to use asynchronous requests.

- **Dashboard**

Uses the cleaned and filtered data from the database.

<img src="media/web_crawler/diagram.png" style="width: 100%;"/>

See the full project repository [here](https://github.com/lealre/crawler-to-dash).

---

## Analytic Report with SQL - Northwind Database

This project aims to generate an analytical business report from a database that contains sales data from a company called Northwind Traders, which imports and exports specialty foods from around the world.

It focus primarily on extracting insights from revenue, product, and customer data using SQL operations in a PostgreSQL database.

<img src="media/northwind_sql/demo.gif" />

It is possible to run this project using only Docker, as it builds both the PostgreSQL database and the client pgAdmin. All instructions are provided in How to run this project section.

See the full project repository [here](https://github.com/lealre/northwind-analytics-sql).

---

## Automating Northwind Database Operations Using PL/pgSQL - Stored Procedures and Triggers

This project aims to use stored procedures and triggers in SQL to automate operations in a database.

By using the PL/pgSQL language on a PostgreSQL database server, two automations were implemented: the first to automatically register changes in an employee's title in a secondary table for future audits; the second to check if there is sufficient stock to fulfill a new order when it is added, as well as updating the stock quantity after the order is stored.

<img src="media/northwind_plpgsql/demo.gif" />

It is possible to run this project using only Docker, as it builds both the PostgreSQL database and the client pgAdmin. All instructions are provided in How to run this project section.

See the full project repository [here](https://github.com/lealre/northwind-PLpgSQL).
