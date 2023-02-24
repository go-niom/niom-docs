---
sidebar_position: 1
---

# Introduction
Niom is a [Nestjs](https://github.com/nestjs/nest) inspired progressive [Golang](https://go.dev/) web framework for developing efficient and scalable server-side applications. Designed to ease things up for fast development

It is not completely a framework. It is more of a scaffold generator which easy and increases the development cycle. It is loaded with lots of features to pace up the go-based server-side project development.

As Niom is more of a generator framework so control is always in your hand.

### Philosophy
In Golang there are lots of HTTP and HTTP-based frameworks none of them provides the complete solution that makes code maintainable and development easy. In NestJS terms, none of them effectively solve the main problem of - **Architecture**.

Niom provides an out-of-the-box application architecture scaffold which allows developers and teams to create highly testable, scalable, loosely coupled, and easily maintainable applications. The architecture is heavily inspired by NestJS.

### Installation
To get started,run the following commands. This will create a new project directory, and populate the directory with the initial core Niom files and supporting modules, creating a conventional base structure for your project.

```base
$ go install github.com/go-niom/niom@latest  
$ niom new project-name 
```

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