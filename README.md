# Hate Speech Classification with NLP

This project is focused on building a hate speech classification system using Natural Language Processing (NLP) techniques. The solution involves data cleaning, feature engineering, and model training with custom model to detect hate speech in text. The deployment process leverages **CircleCI** for continuous integration (CI) and **AWS EC2** for hosting the model.

## Project Structure

The project is organized into the following key components:

- **`constants`**: Holds constant values such as file paths, column names, and configuration settings.
- **`config_entity`**: Defines configuration entities used across the project, including data transformation and model training configurations.
- **`artifact_entity`**: Manages artifact entities like data ingestion and transformation artifacts.
- **`components`**: Contains the core modules responsible for data ingestion, transformation, model training, and evaluation.
- **`pipeline`**: Manages the entire machine learning pipeline, combining components to execute the workflow from raw data to model deployment.
- **`app.py`**: Flask application that provides an interface for interacting with the trained model, including predictions and monitoring.

## Getting Started

Follow the instructions below to set up the project locally.

### Prerequisites

Ensure that the following are installed on your machine:
- **Conda**: To manage Python environments.
- **Python**: Version 3.8 (or higher).
- **Google Cloud SDK or AWS**: For deploying via Google Cloud or AWS (optional).

### Installation Steps

1. **Create a virtual environment** using Conda:

    ```bash
    conda create -n env python=3.8 -y
    ```

2. **Activate the virtual environment**:

    ```bash
    conda activate env
    ```

3. **Install the required dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

4. **Run the Flask application**:

    ```bash
    python app.py
    ```

At this point, the application should be running locally, and you can interact with it through the provided API endpoints.

## Deployment

This project uses **CircleCI** for Continuous Integration (CI) and **AWS EC2** for deployment. Below are the steps to set up deployment on AWS using CircleCI.

### CircleCI Setup

1. **Setting up CircleCI**:
   - Log in to [CircleCI](https://circleci.com/) and set up a new project repository.
   - Integrate your GitHub repository with CircleCI for automatic builds and tests.

2. **Switch on the Self-Hosted Runner**:
   - In the CircleCI dashboard, enable self-hosted runners to use your own infrastructure for the CI process.

3. **Create an EC2 Instance** on AWS:
   - Log in to your AWS account and create an EC2 instance (Linux-based).
   - Ensure that the necessary security groups and ports (such as HTTP, HTTPS) are configured.
   - Install Docker and Python on the EC2 instance.

4. **Configure EC2 for Deployment**:
   - SSH into your EC2 instance and configure it for the deployment of your Python Flask application.
   - Set up environment variables like database credentials, secret keys, etc.

5. **Create `config.yml` for CircleCI**:
   - In the root of your repository, create a `.circleci` folder with a `config.yml` file for defining your CI pipeline.

6. **Set Environment Variables in CircleCI**:
   - In your CircleCI project settings, define environment variables such as `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `EC2_INSTANCE_IP`, and other relevant credentials.

### Google Cloud SDK (Optional)

To deploy the project on Google Cloud, install the [Google Cloud SDK](https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe) and follow these steps:

1. **Initialize gcloud**:

    ```bash
    gcloud init
    ```

2. **Follow the prompts** to set up your Google Cloud environment and select your project.

3. **Deploy the project** using the ec2 for deployment of the project with circle ci

### Key Features:

- **NLP Pipeline**: Data cleaning, transformation, and model training using techniques like stemming, stopword removal, and tokenization.
- **CircleCI Integration**: Automates testing and deployment workflows.
- **AWS EC2 Deployment**: Reliable cloud hosting for the model, ensuring scalability and availability.
- **Fast API Interface**: Provides endpoints for model predictions and training.

