---
sidebar_position: 1
---

# First step

In this set of articles, you'll learn the **core fundamentals** of Niom. To get familiar with the essential building blocks of Niom applications, we'll build a basic CRUD application with features that cover a lot of ground at an introductory level.

### Prerequisites

Please make sure that [Golang](https://go.dev) is installed on your operating system and `Go bin path` is in the system path.

* [Go Installations steps](https://go.dev/doc/install)

You can check using the following command:
```bash
#To verify go installation
$ go version #output go version go1.19 darwin/amd64
```


### Setup

Installing and creating a new project with the [Niom](/cli/overview) is quite straightforward with the following commands in your PC terminal:

```base
$ go install github.com/go-niom/niom@latest  
$ niom new project-name 
```
With the above `niom new` command directory with the `project-name` will be created and required go modules will be installed automatically. The project directory will be populated with scaffolds to manage and run the application and the core server files will be in the `/src` directory.

### Folder structure

```
project-name/
├──pkg/
│  ├──common/
│  │  ┗ common.go
│  ├──config/
│  │  ├──app.go
│  │  ├──config.go
│  │  ├──db.go
│  │  ├──helper.go
│  │  ┗ jwt.go
│  ├──helpers/
│  │  ┗ response.go
│  ├──logger/
│  │  ┗ logger.go
│  ├──middleware/
│  │  ┗ fiber.go
│  ┗ utils/
│    ┗ utils.go
├──server/
│  ├──connecters.go
│  ├──middleware.go
│  ├──router.go
│  ┗ server.go
├──src/
│  ┗ app/
│    ├──dto/
│    │  ┗ app.dto.go
│    ├──model/
│    │  ┗ app.model.go
│    ├──app.controller.go
│    ├──app.router.go
│    ┗ app.service.go
├──.Dockerfile
├──.dockerignore
├──.env
├──README.md
├──env.example
├──go.mod
├──go.sum
├──main.go
├──myapp
┗ niom-cli.json
```

### Platform

As NIOM is developed upon Golang it is platform independent framework. Platform independence makes it install and developed applications on any platform (Linux/Mac/Wins) OS

### Running the application

Once the installation process is complete, you can run the following command at your OS Terminal prompt to start the application listening for inbound HTTP requests:

```bash
$ niom start
```

This command starts the app with the HTTP server listening on the port defined in the `.env` file. Once the application is running, open your browser and navigate to `http://localhost:7000/`. You should see the `Hello World!` message.

To watch for changes in your files, you can run the following command to start the application:

```bash
$ niom start:dev
```

This command will watch your files, automatically recompiling and reloading the server.