# Deployment Guide for ARS Frontend Application

This guide provides a simple walkthrough for deploying the ARS frontend application using **AWS CodeBuild** and **Ansible**.

---

## Prerequisites

1. Access to the **AWS Console** with the correct role.
2. Ensure the appropriate CodeBuild project exists (e.g., `ansible-deploy-dev`).
3. Verify that all necessary configurations are in place.

---

## Deployment Steps

### 1. Log in to the AWS Console
1. Open the [AWS Console](https://aws.amazon.com/console/).
2. Assume the correct IAM role for deployment.

### 2. Navigate to the Deployment Project
1. Go to **CodeBuild** in the AWS Console.
2. Search for the project corresponding to the environment (e.g., `ansible-deploy-dev`).

### 3. Start the Build with Overrides
1. Select the **Start Build** button for the project.
2. In the **Start Build** dialog:
   - **Source Override**: Specify the appropriate source repository.
   - **Environment Variables**:
     - Key: `RUN_VARIABLE`
     - Value: `run_deployARSWEB`

3. Confirm the configurations and click **Start Build**.

### 4. Verify Deployment
1. Check the **Build Logs** to ensure the deployment was successful.
2. Validate the application:
   - Ensure the deployed package is functioning as expected.
   - Refer to the generated log file for deployment details.

---

## Sample Log File

Below is an example of a log file generated after deployment:

---

## Post-Deployment Validation

1. Verify that the **URL** is accessible and the application is functioning.
2. Confirm the `Last Build Date` and `Version` match the expected values.
3. If any issues occur, review the build logs in CodeBuild for troubleshooting.
