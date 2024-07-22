# Quick Start

The W4H Toolkit provides an ecosystem of tools to manage and analyze wearable and other EHR data. We have created a Docker container to give you an overview of what's included in the toolkit. To get started, you must install the `Docker Engine` by following the instructions to [Install Docker Engine](https://docs.docker.com/engine/install/) for your platform. There are two ways to start the container:

- Using the command line
- Using Docker Desktop GUI

## Starting the Container Using the Command Line

This option is the preferred way to start the image as it will download it and initialize the container. To start the container as a background process, execute:

```sh
docker run -p 5432:5432 -e POSTGRES_DB=admin -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin -e hostname=db -dp 8501:8501 -p 8888:8888 --name w4h uscimsc/w4h:preview
```

You can verify that the container is running with 

```sh
docker ps
```

## Starting the Container Using Docker Desktop

Once that is done start and type `uscimsc/w4h` in the search bar and select  the `preview` tagged image. After pulling to download the image, run the container by clicking on the “run” icon under “Actions” next to the image name.

![Starting the container](images/docker_readme.png)

## Using the Dashboard

When the container is running you can open the dashboard

## Using the Sample Notebookes

## Next Steps

- [Working Docker](docker/working-with-docker.md))

