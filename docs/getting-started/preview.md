# W4H-Preview
This document is for the preview of Wearables for Health (W4H) toolkit.  

This Toolkit is available as a Docker image, which can be easily pulled from [Docker Hub](https://hub.docker.com/r/uscimsc/w4h). This containerized version includes all the necessary components and dependencies, making it simple to set up and use the toolkit.

### Pulling the W4H Docker Image
To get started with the W4H Toolkit, follow these steps:
1. Get [Docker](https://docs.docker.com/engine/install/) for your OS.
2. Install Docker engine.
3. Open a terminal or command prompt.
4. Verify Docker installation using:
```bash
docker --version
```
5. Pull the W4H Docker image from Docker hub by running the following command:
```bash
docker pull usc-imsc:w4h-toolkit-preview
```

The W4H toolkit provides the following components:

**Streamlit Dashboard** : An integrated interface for GeoMTS data extraction, presentation & analysis. It facilitates the analysis of both streaming & stored data. 

**Database supporting GeoMTS**: A postgres database with TimescaleDB for temporal data management, PostGIS for spatial data management & FFT postgres for aggregate queries on time series data.

**Notebooks**: A collection of sample Jupyter notebooks that help analyse compliance using Pandas & Pyspark .


## Accessing the Dashboard
After running the docker container, the dashboard is available at http://localhost:8501/

A default account is configured in the preview for the initial testing. Credentials for it are:
```
username: admin
password: admin
``` 

This dashboard provides the following buttons:
+ ImportHub: The ImportHub allows to integrate offfline datasets into the W4H platform.  It aligns the data with GeoMTS schema & automatically maps attributes.
+ Input Page : It allows creation of queries for the data by selecting the required database & transforming the data using filters for visualizations.
+ Result Page: It takes you to the result of the query. It provides outlier detection, comparative analysis between different groups of subjects, health insights, etc. 
+ Query History: You can browse through the history of your visualizations using the Query History Button.
+ Getting Started: It provides a detailed tutorial on how to get started with the preview.

## Accessing Jupyter Notebooks
To access the Jupyter notebooks in the W4H Toolkit, follow these steps:
1. Navigate to http://localhost:8888 in browser
2. When prompted for authentication, use:
```
token: admin
```
3. Once logged in, you'll see the Jupyter notebook interface with access to the /app/notebooks/ directory, which contains the sample notebooks provided by the W4H Toolkit.
4. You can now open existing notebooks or create new ones to work with the W4H datasets.

## Accessing the Database
The  postgres database can be accessed using tools like pgadmin or psql.
To access the database using pgadmin use the following steps:
1. Download & install [pgadmin](https://www.pgadmin.org/) & launch it.
2. In the pgAdmin dashboard, click on "Add New Server" or right-click on "Servers" in the browser pane and select "Create" > "Server...".
3. In the "Create - Server" dialog, fill in the following details:

    General Tab:

        Name: W4H Database (or any name you prefer)
    Connection Tab:

        Host name/address: localhost
        Port: 5432
        Maintenance database: postgres
        Username: postgres
        Password: postgres
4. Save to establish the connection. Once connected, you should see the server appear in the browser pane.
5. To interact with the database:
    + Expand the sample database to view its schemas, tables, and other objects.
    + Use the Query Tool (accessible via Tools > Query Tool) to run SQL queries.

