# CICD with Dockerhub and Github Actions

### Step 1: Build the docker image locally

> docker build .

### Step 2: Push it on a new github repository

Create a new repository on github and push your project there.

### Step 3: Time for Actions

On your github repository, there is an **Actions** page, go there and click on **New Workflow**.

You have a list of templates that you can choose from, or you can create your own workflow by pressing **set up a workflow yourself**, for the sake of learning, let's do that but you can look at templates to get inspired.

You need to create a workflow that will build the docker image. You can commit it to see if it worked.

The file can be found in **.github/workflows/** you can modify it until it works how you want it to.

### Step 4: Set up Dockerhub

Go to https://hub.docker.com/ and create an account if you don't have one yet.

Create a new public repository.

On your computer, run this command and enter your credentials:

> docker login

Now that you are logged in, you can manually push the image you build previously to the Dockerhub repository you just created with **docker push**, and on Dockerhub you can see that a new image was pushed.

### Step 5: Automate the pushing of your image

Good job, you pushed an image by hand, but automating it is much better, let's add to our github workflo to make it also push the image to dockerhub.

For this, you need to run **docker login** in the workflow, but we don't want our docker credentials to be visible so we'll use **github actions secrets** to make sure no one can see them.
