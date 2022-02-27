# uipath-with-github-action
GitHub Actions uses YAML syntax to define the workflow. 
1.	Each workflow is stored as a separate YAML file in your code repository, in a directory called. github/workflows.
2.	You should be able to select a workflow from the ones available or create a new one. For this tutorial, we will create new.
3.	To create your workflow, create a .yml file in the path .github/workflows/action1.yml. Commit the file, GitHub will automatically understand that it is a workflow.
4.	For security’s sake, it’s important not to hard code secrets inside the codebase. A good way to avoid this is by using environment variables to refer to the secrets. 
•	Open your repository on GitHub and go to the Settings tab. On the left navigation bar, click Secrets.
•	Here we can define any ORCH_URL, ORCH_TENANT, ORCH_CLIENT_ID, ORCH_USER_KEY, ORCH_ACC_NAME or ENV Specific Values.

Pretty easy right! 
Let’s first understand the branching strategy and then we will create our workflow step by step.

## GitHub Branching and CI/CD strategy [You can define as per need]
1.	GitHub repository with two branches ‘master’ and ‘develop’ to track the UiPath project.
2.	New ‘feature’ branch from develop branch (to perform changes)
3.	pull request against the develop branch on GitHub
4.	Two CI/CD pipelines (Separately for development and production using yml file configuration) to publish changes in the UiPath Orchestrator environment.
5.	Development pipeline will run when pull request successfully merged with develop branch or push on develop branch.
6.	The production pipeline will run when the developed branch will be merged with the master branch. 


## Set up the GitHub repository
1.	Go ahead and log into your GitHub account. Click on the + sign in the top right corner, then click on new repository:
2.	Let's say - uipath-with-github-action (Name of Repository)
3.	At this point in the article, we assume that you understand how to manage different branches using git client or UiPath Studio.
4.	Next; Create a new project/or use the existing UiPath project and perform git init to initialize it locally
5.	Now we need to set up a remote repository so that it can be tracked remotely. This can be done using UiPath Studio using manage Remotes
a.	Give a Name – Say, Master
b.	URL - https://github.com/rpabotsworld/uipath-with-github-action.git  
6.	The above will automatically create a master branch for you. Simply create a new branch called to develop with the following command using git client or UiPath Studio.
7.	git checkout -b develop
8.	Now, let’s go back to our project on GitHub-actions- UiPath and click on Settings > Secrets > New repository secret, as shown in the screenshot below:
9.	Now we’re done with our GitHub and local repo setup.
