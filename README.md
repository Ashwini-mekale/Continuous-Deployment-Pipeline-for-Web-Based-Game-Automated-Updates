# Continuous-Deployment-Pipeline-for-Web-Based-Game-Automated-Updates<br><br>

# Introduction
## Objective:
Explain the goal of the project: "The primary objective of this project is to automate the deployment process for a web-based game, ensuring that any updates made to the codebase on GitHub are automatically reflected on the live site hosted on AWS S3."

## Key Technologies:
### List and briefly describe the technologies used:
- GitHub Actions: A CI/CD tool for automating software workflows.
- AWS S3: A scalable storage service used for hosting static websites.
- AWS CodePipeline (Optional): A service for automating the release pipelines.
- Visuals: Use logos of GitHub Actions, AWS S3, and CodePipeline to make the slide visually appealing.

<br><br>


# Project Overview
## Description:
"This project involves setting up a continuous deployment pipeline that automatically deploys a web-based game to AWS S3 whenever changes are pushed to the GitHub repository. This approach ensures that the latest version of the game is always live, reducing manual errors and speeding up the deployment process."

## Benefits:
- Speed: Updates are deployed immediately after being pushed.
- Reliability: Reduces human errors in the deployment process.
- Scalability: Easily accommodates new features or updates.
- Visuals: A flowchart illustrating the deployment pipeline, from GitHub to AWS S3.

<br><br>

![Screenshot 2024-09-03 115920](https://github.com/user-attachments/assets/548ea646-a0b8-4ccd-96db-eecfee6f1a9e)<br><br>


# The Game
- Code for a game is hosted in GitHub. We create an S3 bucket for static website hosting, then create a continuous deployment pipeline (using AWS Code Pipeline) to automatically deploy the code whenever changes are made.
- A simple memory matching game. The user clicks two cards (images of memes) to try to match them. If there's a match, the cards disappear from the board. If there's no match, the cards are flipped back to their blank side so the user can try again.
- The game consists of HTML, CSS and JavaScript.

## Ideas for additional features:
- A scoring mechanism
- A timer
- Add additional cards
- Multi-player capabilities so you can compare scores<br><br>



# Step 1 - Setting Up the Game Repository
## Create a GitHub Repository:
- "Start by creating a new repository on GitHub where the game’s source code will reside. Ensure that the repository is public or properly configured if it’s private."

## Organize the Files:
- "Structure your project files logically. The main game code should be in the root directory, with folders for assets, scripts, and deployment configurations."

### Include Deployment Scripts:
- "Add necessary deployment scripts to the repository. These scripts might include build commands, scripts for uploading to S3, and any environment configurations."
- Visuals: Screenshot of a sample GitHub repository structure.

<br><br>
![Screenshot 2024-09-03 160322](https://github.com/user-attachments/assets/c0aaf757-3378-4246-ad81-610610a58d88)
<br><br>




# Step 2 - Configuring AWS S3
## Create an S3 Bucket:
- "Log into AWS, navigate to S3, and create a new bucket. Name the bucket appropriately (e.g., ‘my-game-deployment’)."

## Enable Static Website Hosting:
- "In the S3 bucket settings, enable static website hosting. Specify the index document (e.g., index.html) and optionally an error document."

## Set Permissions:
- "Adjust the bucket policies to allow public access if the game is meant to be publicly accessible. Ensure that only the necessary files are public."
Visuals: Provide a screenshot of the S3 bucket settings, highlighting the static website hosting and permissions sections.

<br><br>
![Screenshot 2024-09-03 160906](https://github.com/user-attachments/assets/614d99af-49ef-414d-ab0c-dabc68bbcef7)

<br><br>

![Screenshot 2024-09-03 160757](https://github.com/user-attachments/assets/90ffd96b-1f0b-4c2b-8d4d-0d580ae33c31)

<br><br>

![Screenshot 2024-09-03 161016](https://github.com/user-attachments/assets/57a6526a-cacb-4482-ab55-2291ab3c1a10)



# Step 3 - Setting Up GitHub Actions
## Create a Workflow File:
- "In the .github/workflows directory of your repository, create a YAML file (e.g., deploy.yml) that defines the actions GitHub should take on specific events."

## Configure Triggers:
- "Set up triggers for the workflow. Common triggers include push or pull_request events on the main branch."

## Define Steps:
- "Outline the steps GitHub Actions will take, such as checking out the code, building the project, and deploying the files to S3 using the AWS CLI."
- Visuals: Show a snippet of a sample GitHub Actions YAML file.

<br><br>


# Step 4 - Configuring AWS CodePipeline (Optional)
## Create a Pipeline:
- "If using AWS CodePipeline, create a new pipeline that integrates with your GitHub repository. This pipeline will automate the process of building and deploying the project."

## Add Stages:
- Source Stage: "Set GitHub as the source, pulling the latest code on commit."
- Build Stage: "Optional - Add a build stage if your game requires building (e.g., compiling assets)."
- Deploy Stage: "Deploy the built files to the S3 bucket."

## Integrate with GitHub:
- "Link GitHub as the source provider, and configure access permissions."
- Visuals: Flowchart showing the stages in CodePipeline.

<br><br>
![Screenshot 2024-09-03 162012](https://github.com/user-attachments/assets/625617c5-3ca7-478d-a2a4-fb17cdfd8a0e)

<br><br>


![Screenshot 2024-09-03 162021](https://github.com/user-attachments/assets/811c8571-f292-46da-823f-651d90da0b89)

<br><br>

![Screenshot 2024-09-03 162030](https://github.com/user-attachments/assets/b5a50aef-1278-420b-9d9d-87a08a58e66d)

<br><br>




# Step 5 - Testing the Deployment
## Test the Workflow:
- "Push changes to the GitHub repository and observe the workflow in action. Verify that the deployment completes successfully and that the game is live."

## Monitor S3 Bucket:
- "Check the contents of the S3 bucket to ensure all files are updated correctly. Test the game URL to confirm that the latest version is served."

## Debug and Iterate:
- "If issues arise, check the GitHub Actions logs and S3 logs for errors. Make necessary adjustments to the workflow and scripts."
- Visuals: Screenshot of a successful deployment pipeline run and the updated S3 bucket content.

<br><br>

![Screenshot 2024-09-03 162519](https://github.com/user-attachments/assets/d53daa5f-acd4-4010-a6d8-d0a4a3c70538)

<br><br>

![Screenshot 2024-09-03 163008](https://github.com/user-attachments/assets/5e24bd8c-3f64-4396-9452-48db81193420)

<br><br>

![Screenshot 2024-09-03 163029](https://github.com/user-attachments/assets/f849ab44-daf1-4245-8b80-adb798bca64a)

<br><br>

![Screenshot 2024-09-03 163331](https://github.com/user-attachments/assets/33dc87af-6185-4918-804e-dda912243a9d)

<br><br>






# Challenges and Solutions
## Common Issues:
- Deployment Errors: "Incorrect AWS credentials or permissions can cause deployment failures."
- Access Issues: "Public access may need to be configured correctly in S3."

## Solutions:
- "Ensure correct AWS IAM roles and permissions."
- "Use the AWS CLI to troubleshoot and manually upload files if needed."
- Visuals: Bullet points or a simple table listing issues and their corresponding solutions.

<br><br>

# Conclusion
## Project Success:
- "The continuous deployment pipeline effectively automated the process of updating the web-based game, ensuring that new features and bug fixes are quickly reflected on the live site."

## Future Improvements:
- **Add Testing :** "Integrate automated testing into the pipeline to catch bugs before deployment."
- **Use CDN :** "Consider using a Content Delivery Network (CDN) for faster game delivery to users worldwide."
- **Visuals :** A summary diagram showing the complete workflow from development to deployment.

<br><br>

# References:

- ### GitHub Actions Documentation
  https://docs.github.com/en/actions

- ### AWS S3 Documentation
  https://docs.aws.amazon.com/s3/index.html

- ### AWS CLI Documentation
  https://docs.aws.amazon.com/cli/index.html

- ### AWS CodePipeline Documentation
  https://docs.aws.amazon.com/codepipeline/index.html



