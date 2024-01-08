# Model-testing
# README for Model Testing Lab

## Lab Overview

This lab focuses on evaluating the performance of different model deployment strategies, including:

- Deployment using FastAPI.
- Deployment via Docker containerization.
- Deployment using TensorFlow Extended (TFX).


## Pre-requisites

Before starting the lab, ensure the following packages are installed:

- TensorFlow
- PyTorch
- Transformers (version >= 4.00)
- FastAPI
- Docker
- Locust

## Resources

Consult the following documentation for guidance:

- [Locust](https://docs.locust.io)
- [TensorFlow Extended (TFX)](https://www.tensorflow.org/tfx/guide)
- [FastAPI](https://fastapi.tiangolo.com)
- [Docker](https://docs.docker.com)
- [HuggingFace TFX Serving](https://huggingface.co/blog/tf-serving)

## Part 1: Serving an NLP Model Using FastAPI

Leveraging a Question Answering (QA) model served using FastAPI, students will utilize the “transformers” library to load DistillBERT pre-trained on the SQuAD dataset.

- Create a data model with Pydantic for QA inputs.
- Load the pre-trained model using the "pipeline" module from the "transformers" library.
- Implement an asynchronous endpoint in FastAPI for the QA model.
- Start the FastAPI application using uvicorn.

## Part 2: Containerizing the API Using Docker

Containerization with Docker offers ease of deployment and operational consistency across environments.

- Place the main FastAPI application inside the "app" folder.
- Build a Dockerfile to set up the FastAPI application.
- Construct and launch a Docker container for the FastAPI service.

## Part 3: Serving a Transformer Model Using TFX

TFX enables efficient and fast model serving. Students will:

- Produce a saved model suitable for TFX.
- Pull the TFX Docker image and run the container.
- Serve the model with TensorFlow Extended using Docker.
- Use FastAPI to consume the TFX served model.

## Part 4: Load Testing with Locust

Load testing with Locust helps evaluate the performance of the deployed models.

- Install Locust and prepare a file to simulate user behavior.
- Test the APIs for the different deployment methods.
- Analyze the performance metrics to determine the most efficient deployment strategy.
  
## Comparison
It appears that the first test (TFX-based FastAPI) might be handling a higher load (as indicated by the higher RPS) but also shows higher latency (potentially worse performance if the response time is critical). In contrast, the second test (regular FastAPI) seems to have lower latency but also lower RPS, which might indicate it's not handling as many requests per second but is responding faster.
<img width="633" alt="Comparison" src="https://github.com/hkhey/Model-testing/assets/76151779/312150ad-d257-486b-9452-8ed4be8a15f3">
