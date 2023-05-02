# Seller's Promotion Microservice

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python](https://img.shields.io/badge/Language-Python-blue.svg)](https://python.org/)
[![Build](https://github.com/devops-summer22-promotions/promotions/actions/workflows/tdd.yml/badge.svg)](https://github.com/devops-summer22-promotions/promotions/actions)

- [Seller's Promotion Microservice](#sellers-promotion-microservice)
  - [Run Steps](#run-steps)
  - [Implemented APIs](#implemented-apis)
    - [Root](#root)
    - [Create A Promotion](#create-a-promotion)
    - [List All Promotions](#list-all-promotions)
    - [Read A Promotion](#read-a-promotion)
    - [Update A Promotion](#update-a-promotion)
    - [Delete A Promotion](#delete-a-promotion)
  - [Overview](#overview)
  - [Automatic Setup](#automatic-setup)
  - [Manual Setup](#manual-setup)
  - [Contents](#contents)
  - [License](#license)

## Run Steps

- run test: `make test`
- start server: `make run`

## Implemented APIs

### Root

- url: /
- method: GET

sample response data:

```json
{
    "name": "Promotion REST API Service",
    "paths": "http://localhost:8000/promotions",
    "version": "1.0"
}
```

### Create A Promotion

- url: /promotions
- method: POST

sample request data:

```json
{
    "name": "promo 1",
    "type": "BUY_ONE_GET_ONE",
    "discount": 1,
    "customer": 1,
    "start_date": "2022-6-22",
    "end_date": "2022-6-25"
}
```

sample response data:

```json
{
    "customer": 1,
    "discount": 1,
    "end_date": "Sat, 25 Jun 2022 00:00:00 GMT",
    "id": 243,
    "name": "promo 1",
    "start_date": "Wed, 22 Jun 2022 00:00:00 GMT",
    "type": "BUY_ONE_GET_ONE"
}
```

### List All Promotions

- url: /promotions
- method: GET

sample response data:

```json
[
    {
        "customer": 1,
        "discount": 1,
        "end_date": "Sat, 25 Jun 2022 00:00:00 GMT",
        "id": 243,
        "name": "promo 1",
        "start_date": "Wed, 22 Jun 2022 00:00:00 GMT",
        "type": "BUY_ONE_GET_ONE"
    },
    {
        ...
    },
    {
        ...
    }
]
```

### Read A Promotion

- url: /promotions/\<id\>
- method: GET

sample response data:

```json
{
    "customer": 1,
    "discount": 1,
    "end_date": "Sat, 25 Jun 2022 00:00:00 GMT",
    "id": 243,
    "name": "promo 1",
    "start_date": "Wed, 22 Jun 2022 00:00:00 GMT",
    "type": "BUY_ONE_GET_ONE"
}
```

### Update A Promotion

- url: /promotions/\<id\>
- method: PUT

sample request data:

```json
{
    "name": "promo 2",
    "type": "BUY_ONE_GET_ONE",
    "discount": 1,
    "customer": 1,
    "start_date": "2022-6-22",
    "end_date": "2022-6-25"
}
```

sample response data:

```json
{
    "customer": 1,
    "discount": 1,
    "end_date": "Sat, 25 Jun 2022 00:00:00 GMT",
    "id": 321,
    "name": "promo 2",
    "start_date": "Wed, 22 Jun 2022 00:00:00 GMT",
    "type": "BUY_ONE_GET_ONE"
}
```

### Delete A Promotion

- url: /promotions/\<id\>
- method: DELETE

## Overview

This project template contains starter code for your class project. The `/service` folder contains your `models.py` file for your model and a `routes.py` file for your service. The `/tests` folder has test case starter code for testing the model and the service separately. All you need to do is add your functionality. You can use the [lab-flask-tdd](https://github.com/nyu-devops/lab-flask-tdd) for code examples to copy from.

## Automatic Setup

The best way to use this repo is to start your own repo using it as a git template. To do this just press the green **Use this template** button in GitHub and this will become the source for your repository.

## Manual Setup

You can also clone this repository and then copy and paste the starter code into your project repo folder on your local computer. Be careful not to copy over your own `README.md` file so be selective in what you copy.

There are 4 hidden files that you will need to copy manually if you use the Mac Finder or Windows Explorer to copy files from this folder into your repo folder.

These should be copied using a bash shell as follows:

```bash
    cp .gitignore  ../<your_repo_folder>/
    cp .flaskenv ../<your_repo_folder>/
    cp .gitattributes ../<your_repo_folder>/
```

## Contents

The project contains the following:

```text
.gitignore          - this will ignore vagrant and other metadata files
.flaskenv           - Environment variables to configure Flask
.gitattributes      - File to gix Windows CRLF issues
.devcontainers/     - Folder with support for VSCode Remote Containers
dot-env-example     - copy to .env to use environment variables
requirements.txt    - list if Python libraries required by your code
config.py           - configuration parameters

service/                   - service python package
├── __init__.py            - package initializer
├── models.py              - module with business models
├── routes.py              - module with service routes
└── utils                  - utility package
    ├── error_handlers.py  - HTTP error handling code
    ├── log_handlers.py    - logging setup code
    └── status.py          - HTTP status constants

tests/              - test cases package
├── __init__.py     - package initializer
├── test_models.py  - test suite for business models
└── test_routes.py  - test suite for service routes
```

## License

Copyright (c) Alex, Ankita, Daming Zeyu, Zihao and Prof. John Rofrano. All rights reserved.

Licensed under the Apache License. See [LICENSE](LICENSE)

This repository is part of **CSCI-GA.2820-001 DevOps and Agile Methodologies** created and instructed by *John Rofrano*, Adjunct Instructor, NYU Courant Institute, Graduate Division, Computer Science, and NYU Stern School of Business.
