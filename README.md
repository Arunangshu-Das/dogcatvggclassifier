# Cat-Dog-Classification

This Flask application is designed for Cat-Dog Classification. It utilizes a pre-trained model to predict whether an input image contains a cat or a dog.

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/Arunangshu-Das/dogcatvggclassifier.git
   ```

2. Install the required dependencies. It is recommended to set up a virtual environment before installing the dependencies:
   ```
   pip install -r requirements.txt
   ```

3. Download the pre-trained model weights and place them in the `prediction` directory.

## Usage

1. Start the Flask server by running the following command:
   ```
   python app.py
   ```

2. Access the application by opening your web browser and navigating to `http://localhost:8000`.

## Endpoints

### Home

- **URL**: /
- **Method**: GET
- **Description**: Renders the index.html template, which serves as the home page for the application.

### Predict

- **URL**: /predict
- **Method**: POST
- **Description**: Accepts a JSON object containing the image data in base64 format. The image is then decoded, saved as "inputImage.jpg", and passed to the pre-trained model for prediction. The predicted result (cat or dog) is returned as a JSON response.

## File Structure

- `app.py`: The main Flask application file that handles routing and serves the web pages.
- `index.html`: HTML template file for the home page.
- `utils.py`: Contains utility functions, including the `decodeImage` function for decoding base64-encoded images.
- `predict.py`: Contains the `DogCat` class, which uses a pre-trained model for cat-dog classification.

## Notes

- Make sure to have the required model weights in the `prediction` directory before running the application.
- The application runs on `http://localhost:8000` by default. You can modify the host and port in the `app.run()` statement if needed.


# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 315865595366.dkr.ecr.us-east-1.amazonaws.com/simple-app

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
