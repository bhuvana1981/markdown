# Deployment Guide for ARS Backend Application

This guide outlines the steps to deploy the ARS backend application using **AWS CodeBuild** and **Ansible**.

---

## Prerequisites

- Access to the **AWS Console** with the appropriate IAM role.
- Knowledge of the environment to deploy (e.g., `dev`, `prod`).
- Ensure the required CodeBuild projects are available:
  - Artifact promotion project.
  - Ansible deployment project for the desired environment.

---

## Deployment Steps

### 1. Log in to the AWS Console
1. Open the [AWS Console](https://aws.amazon.com/console/).
2. Assume the correct IAM role for deployment.

---

### 2. Promote Artifacts
1. Navigate to **AWS CodeBuild** in the console.
2. Locate the project responsible for promoting build artifacts (e.g., `build-artifacts`).
3. Click **Start Build**.
4. In the **Overrides** section:
   - Add the environment variable:
     - **Key**: `RUN_VARIABLE`
     - **Value**: `run_promoteArtifacts`
5. Click **Start Build** to promote the artifacts.

---

### 3. Deploy the Backend Application
1. Navigate to **AWS CodeBuild**.
2. Locate the Ansible deployment project for the environment (e.g., `ansible-deploy-dev`).
3. Click **Start Build**.
4. In the **Overrides** section:
   - Add the environment variable:
     - **Key**: `RUN_VARIABLE`
     - **Value**: `run_deployBackend`
5. Click **Start Build** to deploy the backend application.

---

### 4. Verify Deployment
After the application deployment completes:

1. Verify the deployment logs to ensure successful deployment.
2. Review the sample log file for the following details:
   - **Deployed Date**
   - **Application URL**
   - **Last Build Date**
   - **Version**
3. Confirm the deployed package matches the expected version.

---

## Troubleshooting

- **Build Fails in CodeBuild**:
  - Check the logs for any errors during the artifact promotion or deployment steps.
  - Ensure the correct environment variables were added in the overrides section.

- **Application Issues After Deployment**:
  - Verify the deployment logs for errors.
  - Confirm the application is accessible via the provided URL.

---

This guide ensures a smooth deployment process for the ARS backend application. Let me know if any additional details are needed!

