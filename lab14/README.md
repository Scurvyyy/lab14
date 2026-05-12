# README.md

## API Testing Assignment

Энэ лаб-д DummyJSON API - г ашиглаж Postman, Newman, and GitHub Actions дээр тэст хийсэн 

## API Used

 API: DummyJSON
* Base URL:

```text
https://dummyjson.com
```

## Features

 GET requests
 POST requests
 PUT requests
 DELETE requests
 Authentication testing
 Error handling tests
 Request chaining
 Newman CLI execution
 GitHub Actions CI/CD
 HTML reporting

## Project Structure

```text
bie-daalt-14/
├── .github/
│   └── workflows/
│       └── api-tests.yml
├── partA/
│   ├── SETUP.md
│   └── screenshot.png
├── postman/
│   ├── collection.json
│   ├── env.dev.json
│   └── env.ci.json
├── reports/
│   └── api.html
├── README.md
└── REFLECTION.md
```

## Requirements

Install Node.js first.

Install Newman:

```bash
npm install -g newman
```

Install HTML Reporter:

```bash
npm install -g newman-reporter-htmlextra
```

## Run Tests Locally

```bash
newman run postman/collection.json -e postman/env.dev.json
```

## Generate HTML Report

```bash
newman run postman/collection.json -e postman/env.dev.json --reporters cli,htmlextra --reporter-htmlextra-export reports/api.html
```

## GitHub Actions

The workflow automatically runs Newman tests on:

* push
* pull_request

Reports are uploaded as workflow artifacts.

