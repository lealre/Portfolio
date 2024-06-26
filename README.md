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

<!-- <p>
  <a href="https://github.com/lealre/plant_watering">
    <img width="50%" align="right" alt="Lealre's github stats" src="https://github-readme-stats.vercel.app/api?username=lealre&show_icons=true&hide_border=true" />
  </a>
</p> -->

## Table of contents

### Python

1. [Rental Properties CRUD Catalog with SQLAlchemy, FastAPI, Streamlit and AWS Deploy](#rental-properties-crud-catalog-with-sqlalchemy-fastapi-streamlit-and-aws-deploy) 
2. [Orchestrating an ETL with Airflow - From Google Drive to PostgreSQL](#orchestrating-an-etl-with-airflow---from-google-drive-to-postgresql)
3. [Web crawler to extract data from property websites using noSQL databases - Redis and MongoDB](#web-crawler-to-extract-data-from-property-websites-using-nosql-databases---redis-and-mongodb)
4. [Excel Schema Validator with Pydantic and Streamlit](#excel-schema-validator-with-pydantic-and-streamlit)

## SQL
1. [Analytic Report with SQL - Northwind database](#analytic-report-with-sql---northwind-database)
2. [Automating Northwind database operations using PL/pgSQL - Stored Procedures and Triggers](#automating-northwind-database-operations-using-plpgsql---stored-procedures-and-triggers)

-------------------------------------------------------------------------------

## Rental Properties CRUD Catalog with SQLAlchemy, FastAPI, Streamlit and AWS Deploy

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

## Orchestrating an ETL with Airflow - From Google Drive to PostgreSQL

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

-------------------------------------------------------------------------------

## Web crawler to extract data from property websites using noSQL databases - Redis and MongoDB

A versatile web crawler for extracting data from property websites, utilizing NoSQL databases such as Redis and MongoDB.

The crawler retrieves specific tasks or inputs from Redis, allowing data extraction processes across multiple sites using a single script. In this project two portuguese sites were scraped: [CASASAPO](https://casa.sapo.pt/) and [Imovirtual](https://www.imovirtual.com/).

<img src="media/web_crawler/demo.gif" />

### Tools used

<div style="display: flex; justify-content: space-between;">   
    <img src="media/requests.svg" height=100/> 
    <img src="media/bs4.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-plain-wordmark.svg"  height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-plain-wordmark.svg" height=100/>
</div>
          
### How it works

After receiving a specific website key identification, the script retrieves all the inputs from the Redis database in a JSON format. These inputs are responsible for the URL requests and capturing the HTML structure of the target site for extraction. It also receives a query specifying the location in Portugal from which to search for properties.

The extraction process utilizes the BeautifulSoup package, and through a recursive function, it identifies additional pages for extraction if present.

To establish connections with both Redis and MongoDB, the generic crawler inherits from an abstract class.

After extracting all the raw data, it is stored directly in the MongoDB database for further processing and analysis.

<img src="media/web_crawler/diagram.png"/>

See the full project repository [here](https://github.com/lealre/properties-webcrawler?tab=readme-ov-file).

---------------------------------------------------------------------------------------------------

## Excel Schema Validator with Pydantic and Streamlit

Web application that validates a specific Excel schema and stores the data in a PostgreSQL database. The predefined schema is the contract schema, and the application validates it from Excel files using Pydantic, a Python validation library.

<img src="media/excel_validator_project/demo.gif" />

### Tools used
<div style="display: flex; justify-content: space-between;">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/streamlit/streamlit-original-wordmark.svg" height=100 />   
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlalchemy/sqlalchemy-original-wordmark.svg" height=100/>     
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original-wordmark.svg" height=100/>
    <img src="media/pydantic.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-plain-wordmark.svg" height=100 />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" height=100/>
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytest/pytest-plain-wordmark.svg" height=100 />      
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-plain-wordmark.svg"  height=100/>          
</div>

### How it works

The user can upload Excel files in the app, and if the schema differs from the contract, the application will display a message indicating where the data schema differs from the contract schema, highlighting the specific rows and columns where the data does not conform to the agreed-upon schema.

If the schema from the uploaded file passes validation, the app gives the option to store the data in the database

<img src="media/excel_validator_project/app-diagram.png" />

See the full project repository [here](https://github.com/lealre/excel-schema-validator).

---------------------------------------------------------------------------------------------------

## Analytic Report with SQL - Northwind database

This project aims to generate an analytical business report from a database that contains sales data from a company called Northwind Traders, which imports and exports specialty foods from around the world. 

It focus primarily on extracting insights from revenue, product, and customer data using SQL operations in a PostgreSQL database.

<img src="media/northwind_sql/demo.gif" />


It is possible to run this project using only Docker, as it builds both the PostgreSQL database and the client pgAdmin. All instructions are provided in How to run this project section.

See the full project repository [here](https://github.com/lealre/northwind-analytics-sql).

---------------------------------------------------------------------------------------------------

## Automating Northwind database operations using PL/pgSQL - Stored Procedures and Triggers

This project aims to use stored procedures and triggers in SQL to automate operations in a database.

By using the PL/pgSQL language on a PostgreSQL database server, two automations were implemented: the first to automatically register changes in an employee's title in a secondary table for future audits; the second to check if there is sufficient stock to fulfill a new order when it is added, as well as updating the stock quantity after the order is stored.

<img src="media/northwind_plpgsql/demo.gif" />

It is possible to run this project using only Docker, as it builds both the PostgreSQL database and the client pgAdmin. All instructions are provided in How to run this project section.

See the full project repository [here](https://github.com/lealre/northwind-PLpgSQL).
