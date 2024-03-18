# Counter Python App

This project is a Python counter application that provides a web interface to increment and display a counter.

## Containerization of the Application

The application has been containerized using Docker for better portability and ease of deployment.

## Setting Up the Environment

To run this project and set up the CI/CD pipeline, you'll need three virtual machines:

1. **gitlab-instance**: This machine hosts a GitLab instance.
2. **gitlab-runner**: This machine hosts a shell-based GitLab runner.
3. **dev-srv**: This machine is used to deploy the containerized application.

## Running the CI/CD Pipeline

1. Start by launching the GitLab instance on the `gitlab-instance` virtual machine.
2. Install and configure the GitLab runner on the `gitlab-runner` virtual machine.
3. Ensure the `dev-srv` virtual machine is set up for deployment.

## CI/CD Pipeline Configuration

To integrate the CI/CD pipeline:

1. Configure the pipeline to have three stages:
   - **build-image**: Builds the Docker image of the application.
   - **publish-image**: Publishes the Docker image to Docker Hub with the commit Git tag.
   - **deploy-app**: Deploys the containerized application to the development server (dev-srv).
   
2. The pipeline should use the custom GitLab runner (`gitlab-runner`) for execution.

## Variables Setup

Ensure the following variables are set up in your GitLab project:

1. `DOCKERHUB_LOGIN`: Your Docker Hub username.
2. `DOCKERHUB_PASSWORD`: Your Docker Hub password.
3. `SSH_PASSWORD`: Password for SSH authentication to the `dev-srv` machine.

## Running the Project

Once the pipeline is configured and variables are set up:

1. Push your code changes to the GitLab repository.
2. The pipeline will automatically trigger.
3. Monitor the pipeline execution in the GitLab CI/CD interface.
4. Once the pipeline is successful, access your deployed application on the `dev-srv` machine.

## Notes

Make sure to replace placeholder values with your actual credentials and configurations for successful pipeline execution.
