# Question-Answer Bot with FastAPI, Elasticsearch, and OpenAI Embeddings

## Overview
This project implements a Question-Answer (QA) bot using FastAPI and Elasticsearch. It is designed to receive questions and provide relevant answers by leveraging the power of Elasticsearch for efficient data retrieval and OpenAI's embedding model for semantic understanding.

## Prerequisites
- Python 3.x
- Docker
- Elasticsearch

## Setup Instructions

### Setting up the Virtual Environment
1. Ensure Python 3.x is installed on your system.
2. Follow the guide [here](https://biplov.dev/mastering-python-development-a-step-by-step-guide-to-setting-up-virtual-environments-on-your-pc/) to set up a Python virtual environment.
3. Activate the virtual environment.
4. Install the required dependencies by running `pip install -r requirements.txt` (ensure you have a `requirements.txt` file with all necessary packages).

### Running Elasticsearch with Docker
1. Install Docker on your machine if you haven't already.
2. Start Elasticsearch using Docker by executing the following command in the terminal:

```
docker compose -f ./docker-compose.es.yml up --build -d
```
This will set up Elasticsearch to run on `localhost:9200`.

## Running the Application
1. Start the FastAPI server by running all the cells in juypter notebook.
2. The API will be available at `http://localhost:5001`.
3. Elasticsearch can be accessed at `http://localhost:9200`.

## API Endpoints
- `POST /train/`: Add a question-answer pair to the system.
- `POST /ask/`: Retrieve answers for a given query.
- `GET /health/`: Check the health status of the API.

## High-Level Architecture
The application uses FastAPI for handling HTTP requests. Questions and answers are indexed in Elasticsearch with their respective vector representations. OpenAI's embedding model is used to convert textual data into vectors for semantic search. When a query is made, the system finds the most relevant answers using cosine similarity in Elasticsearch.

