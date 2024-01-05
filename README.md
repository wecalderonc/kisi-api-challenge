# Solution for The Kisi Backend Code Challenge

## ActiveJob with Google Cloud Pub/Sub Integration

## Author: William Eduardo Calderón Castillo

## Email: wecalderonc@unal.edu.co

## Introduction

This project demonstrates an integration of Rails ActiveJob with Google Cloud Pub/Sub. It includes a custom ActiveJob queue adapter for GCP Pub/Sub, a background job processing system, and a load testing script. The aim is to provide a robust solution for asynchronous job processing in a Rails application using Google Cloud Pub/Sub.

## Getting Started

### Setup

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/wecalderonc/kisi-api-challenge.git
   cd kisi-api-challenge
   git checkout code-challenge
   ```

2. **Start Docker Containers:**

   In the project directory, run:

   ```bash
   docker-compose up
   ```

   This command builds the necessary Docker containers for the web server and worker.

3. **Run the Load Test:**

   In another terminal, execute:

   ```bash
   docker-compose exec web bin/rails runner -e development "require './lib/load_test'; LoadTest.run(10)"
   ```

   Replace `60` with the number of seconds you want the load test to run.

4. **Check logs:**

    Return to first terminal, and check logs for review the Job Processing.

5. **Change the seconds of delay after a job failed**

    If you don't want to wait 5 minutes when a Job fails:

    - Open the project with your code editor
    - Open the worker.rake file
    - Go to line 55
    - Comment line 53, and uncomment line 56.
    - Stop the docker-compose up if its already running, and restart.
    - Run again the "Load Test script" and enjoy a quickly test. (Easy for review the logs).
    - Optional: Use only 1 second when running the Load test Script
