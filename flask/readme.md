# Flask RESTful API for Machine Learning Model

This repository contains a Flask app that serves as a RESTful API for a machine learning model. The API is designed to be deployed on Google Cloud Run. The machine learning model can be trained and deployed separately.

## Prerequisites

- Python 3.x
- Flask
- Google Cloud SDK

## Installation

1. Clone the repository and go to flask folder:

   ```bash
   git clone https://github.com/arsyaninsa/capstone-ml.git
    
   cd flask/
   ```

2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Configuration

Before running the Flask app, you need to set up the following configuration variables:

- `MODEL_PATH`: Path to the machine learning model file.

Create a file named `.env` in the project directory and define the variables:

```bash
MODEL_PATH={THE_MODEL_PATH}
```
You can get our model file [here]:(https://storage.googleapis.com/temantanam-bucket/model.h5) (**!large file**)

## Usage

### Running the Flask App Locally

To run the Flask app locally on your machine, follow these steps:

1. Set the Flask app environment variable:

   ```bash
   export FLASK_APP=app.py
   ```

2. Start the Flask development server:

   ```bash
   flask run --port 8080
   ```

   The API will be accessible at `http://localhost:8080`.

### Deploying to Google Cloud Run

To deploy the Flask app to Google Cloud Run, follow these steps:

1. Set up the Google Cloud SDK and authenticate with your Google Cloud account.

2. Build the container image:

   ```bash
   gcloud builds submit --tag gcr.io/[PROJECT-ID]/flask-api
   ```

3. Deploy the container to Cloud Run:

   ```bash
   gcloud run deploy --image gcr.io/[PROJECT-ID]/flask-api --platform managed
   ```

   Replace `[PROJECT-ID]` with your Google Cloud project ID.

   Follow the prompts to select the region, service name, and other options for the deployment.

4. Once the deployment is successful, you will receive a URL where the API is accessible.

## API Documentation 
Please access the API documentations here: [Model API Documentation](https://documenter.getpostman.com/view/21669206/2s93shypRh)
## Deployment URL:
[https://temantanam-model-nzc6yfaf5q-et.a.run.app/](https://temantanam-model-nzc6yfaf5q-et.a.run.app/)
