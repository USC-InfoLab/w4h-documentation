# W4H-Preview
## Introduction
This document is for the preview of W4H toolkit. W4H Toolkit is an ecosystem that covers most of the common features needed when using wearables in a clinical study or or trial. As studies can have very different requirements, W4H toolkit is designed to be flexible and incrementally adoptable. This toolkit provides the following components:


**Dashboard** : An intuitive interface that offers data input forms and visual analytics tools.

**Notebooks**: A collection of sample Jupyter notebooks that showcase various data analysis techniques. These include Pandas notebook & Pyspark notebooks.

**Database**: A curated postgres database specifically used in W4H examples, providing real-world data for testing and demonstration purposes.

## Docker Image
The W4H Toolkit is available as a Docker image, which can be easily pulled from [Docker Hub](https://hub.docker.com/r/uscimsc/w4h). This containerized version includes all the necessary components and dependencies, making it simple to set up and use the toolkit.

### Pulling the W4H Docker Image
To get started with the W4H Toolkit, follow these steps:
1. Ensure Docker is installed on your system.
2. Open a terminal or command prompt.
3. Pull the W4H Docker image from Docker hub by running the following command:
```bash
docker pull usc-imsc:w4h-toolkit-preview
```

### Running the container
Once the image is pulled, run the container using following command:
```bash
docker run -e POSTGRES_DB=postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -p 8501:8501 -p 5432:5432 -p 8888:8888 --user root -v $(pwd):/app usc-imsc:w4h-toolkit-preview
```

## Accessing the Dashboard
After running the container, the dashboard is available at http://localhost:8501/

***1. Login***

A default account is configured in the preview for the initial testing. Credentials for it are:
```
username: admin
password: admin
``` 

This dashboard provides the following buttons:
+ ImportHub: It allows to add your database to the dashboard. 
+ Input Page : It allows creation of queries for the data by selecting the required database & transforming the data using filters for visualizations.
+ Result Page: It takes you to the result of the query.
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
The curated postgres database used in the examples can be accessed using tools like pgadmin or psql.
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

