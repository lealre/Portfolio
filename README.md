# Portfolio



# Rental Properties CRUD Catalog with SQLAlchemy, FastAPI, Streamlit and AWS Deploy

A web application for performing CRUD operations (Create, Read, Update and Delete) of rental properties stored in a PostgreSQL database.

<img src="media/crud_project/demo.gif" />

### Tools used

<div style="display: flex; justify-content: space-between;">
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

In each of the CRUD operations, the frontend sends a request to the API created using FastAPI. The API is responsible for communicating with the backend and sending a response back to the frontend to display the result of the CRUD operation. In the first layer, Pydantic is used to validate all the inputs, ensuring that the schema the user is trying to send matches the database table schema. If it doesn't match, an error message is displayed to the user.

After Pydantic validation is completed, SQLAlchemy is used to communicate with PostgreSQL and perform one of the CRUD operations in the database

<img src="media/crud_project/diag.png"/>

See the full project repository [here](https://github.com/lealre/crud-rental-properties).

---------------------------------------------------------------------------------------------------

# Orchestrating an ETL with Airflow - From Google Drive to PostgreSQL

An ETL orchestration using Airflow, extracting CSV files from a folder in Google Drive, transforming values, and storing them in a PostgreSQL database.

<img src="media/airflow_project/etl-diagram.png"/>

The data is handled in a pandas DataFrame format, and all the data validation is performed using the Pandera library, a Pydantic-based library to validate DataFrame schemas. By setting a specific data contract, validations occur in two phases: when extracted and when transformed.

The Airflow implementation was created using the Astro CLI, the command line interface for data orchestration from Astronomer.

### Tools used
<div style="display: flex; justify-content: space-between;">
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

---------------------------------------------------------------------------------------------------

# Excel Schema Validator with Pydantic and Streamlit

