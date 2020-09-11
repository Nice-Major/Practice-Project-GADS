# LAB: Google Cloud Fundamentals: GEtting Staterted with App Engine

# Objectives

In this Lab we will learn how to perform the following tasks:

  -Initialize App Engine

  -Preview an App Engine Application running locally in Cloud Shell.

  -Deploy an App Engine application, so that others can reach it.

  -Disable an App Engine Application when you no longer want it to be Visible

## Steps

1. Activate Cloud Shell and list the active account name.
    gcloud  auth list

  -List the Project ID with this command
   gcloud config list project

2. Initialize App Engine
    gcloud app create --project=$DEVSHELL_PROJECT_ID

  -Clone the repository for a sample application in the hello_world directoruy
    git clone https://github.com/GoogleCloudPlatform/python-docs-samples
  
  -change the directory to the source directory
    cd python-docs-samples/appengine/standard_python3/hello_world

3. Run Hello_world Applicstion locally.
  -Execute the following command to download and update the packages list
    sudo apt-get update
  
  -set up a Python Virtual Environment. Python Virtual environments are used to isolate package installations from the system
    sudo apt-get install virtualenv
  
  -When prompted press Y and then ENTER key. Then input the command
    virtualenv -p python3 venv

  -Activate the virtual environment
    source venv/bin/activate

  -Navigate to project directory and install dependencies
    pip install -r requirements.txt

  -Run the application
    python main.py

  -In cloud shell click web preview on port 8080
  
  -Return to Cloud shell andd press Ctrl + C to abort the deployed source

  -Check and verify there were no app engine resources deployed in the console

3. Deploy and run Hello_World on App Engine.
  -Navigate to the source directory
    cd ~/python-docs-samples/appengine/standard_python3/hello_world

  -Deploy your hello_world application
    gcloud app deploy

  -when prompted press Y and ENTER key.

  -Open a new browser Tab and vieew the app at
    http://YOUR_PROJECT_ID.appspot.com

4. Disable the application through the console, alternatively through the command line 
    gcloud app versions stop VERSION
