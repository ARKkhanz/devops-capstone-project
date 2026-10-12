# devops-capstone-project

![Build Status](https://github.com/ARKkhanz/devops-capstone-project/actions/workflows/ci-build.yaml/badge.svg)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

## Project Description

This DevOps Capstone Project develops a Customer Accounts microservice
for an e-commerce application using Python, Flask, and PostgreSQL.
The REST API supports creating, reading, updating, deleting, and
listing customer accounts.

The project applies Agile planning using GitHub Projects, test-driven
development with at least 95% code coverage, continuous integration
with GitHub Actions, security using Flask-Talisman and Flask-CORS,
containerization with Docker, deployment to Kubernetes and OpenShift,
and continuous delivery using Tekton.

This project is part of the
[IBM DevOps Capstone Project](https://www.coursera.org/learn/devops-capstone-project)
within the
[IBM DevOps and Software Engineering Professional Certificate](https://www.coursera.org/professional-certificates/devops-and-software-engineering).

## Repository

Repository name: `devops-capstone-project`

GitHub URL: https://github.com/ARKkhanz/devops-capstone-project

## Agile Planning

The GitHub Projects Kanban board contains these seven columns:

- New issues
- Icebox
- Product backlog
- Sprint backlog
- In progress
- Review/QA
- Done

The project is organized into three one-week sprints:

- **Sprint 1:** Set up the development environment and implement the
  read, update, delete, and list account endpoints using TDD.
- **Sprint 2:** Add continuous integration and application security.
- **Sprint 3:** Containerize the microservice, deploy it to Kubernetes,
  and automate deployment using a Tekton CD pipeline.

## Usage

This repository was created from the
[DevOps Capstone starter template](https://github.com/ibm-developer-skills-network/aolwx-devops-capstone-template)
using GitHub's **Use this template** option.

## Development Environment

The labs are designed to run in the IBM Skills Network Cloud IDE
with OpenShift. Use the lab links provided in the Coursera course.

Initialize the development environment by sourcing the setup script:

```bash
source bin/setup.sh
```

**Do not run this script using `bash bin/setup.sh`.** It sets environment
variables and must be sourced.

The setup script installs Python 3.9, configures the environment,
creates a Python virtual environment, and activates it.

After setup, the terminal prompt should look like:

```text
(venv) theia:project$
```

## Useful Commands

### Activate the Python Virtual Environment

```bash
source ~/venv/bin/activate
```

### Install Dependencies

With the virtual environment activated:

```bash
make install
```

### Start PostgreSQL

```bash
make db
```

Verify that PostgreSQL is running:

```bash
docker ps
```

## Project Layout

The microservice code is in the `service` package, and tests are in
the `tests` directory.

The application follows the Model-View-Controller pattern. Database
operations and business logic are implemented in `models.py`, while
REST API endpoints are implemented in `routes.py`.

```text
├── service
│   ├── common/
│   ├── config.py
│   ├── models.py
│   └── routes.py
├── setup.cfg
└── tests
    ├── factories.py
    ├── test_cli_commands.py
    ├── test_models.py
    └── test_routes.py
```

## Data Model

The Account model contains the following fields:

| Name | Type | Optional |
|------|------|----------|
| id | Integer | False |
| name | String(64) | False |
| email | String(64) | False |
| address | String(256) | False |
| phone_number | String(32) | True |
| date_joined | Date | False |

## Implementation Requirements

Complete the account microservice by implementing the REST APIs for
**READ**, **UPDATE**, **DELETE**, and **LIST**.

Follow test-driven development:

1. Write tests for the required behavior.
2. Run the tests and observe the expected failures.
3. Implement the code needed to pass the tests.
4. Maintain at least **95% test coverage**.

## Local Kubernetes Development

The repository also supports local Kubernetes development. These
commands are intended for a local computer, not the Cloud IDE.

Install [Docker Desktop](https://www.docker.com/products/docker-desktop).
For the provided development container environment, also install
[Visual Studio Code](https://code.visualstudio.com/) and its
[Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

### Create a Local K3D Cluster

```bash
make cluster
```

### Install Tekton

```bash
make tekton
```

### Install ClusterTasks

```bash
make clustertasks
```

## Credits

Starter code by
[John Rofrano](https://www.coursera.org/instructor/johnrofrano),
Senior Technical Staff Member, DevOps Champion at IBM Research,
and Coursera Instructor.

Capstone implementation by **ARKkhanz**.

## License

Licensed under the Apache License, Version 2.0.
See [LICENSE](LICENSE).

© IBM Corporation 2022. All rights reserved.
