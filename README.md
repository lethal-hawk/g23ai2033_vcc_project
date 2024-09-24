
END TO END PROJECT FOR EMOTION CLASSIFIER

-------------------
STEP 1: WRITE THE CODE FOR THE DATASET AS BELOW (THE CODE IS UPLOADED IN THE REPOSITORY)

1. #Import the necessary libraries
2. #Create a function that reads an audio file and extracts three types of features (MFCC, chroma, and mel spectrogram) based on the provided flags, returning them as a single NumPy array. These features are commonly used in audio processing, speech recognition, and music information retrieval tasks.
3. #label the emotions
4. #write code that loads audio files from a specified dataset, extracts features related to emotions, and splits the data into training and test sets. This is commonly used in machine learning workflows for training models to classify emotions based on audio input.
5. #Split the dataset into training and testing
6. #Create an MLP Classifier
7. #Observe the accuracy of the model- In our case we have the got the accuracy as - 74.48%
8. #Plot ROC-AUC curve
9. #Create pickle file 

-----------------------------------------------

STEP 2: SETTING UP THE DJANGO PROJECT
----------------------------------------------------
1. Create a virtual environment.
2. Install django version-3.2.0
3. create a project: django-admin startproject <project_name>
-> pip install -r requirements.txt
4. cd into project.
5. create an app: python manage.py startapp <app_name>
6. Setting up the settings.py inside project directory.
7. run the command to initialize the tables: python manage.py migrate
8. run the command: python manage.py runserver
   
NOTE : When creating your private key using puttyGen, check the "save private key",

----------------------------------------------------
STEP3 :SET UP VIRTUAL MACHINE IN AWS
---------------------------------------------------
Setting up a Virtual Machine (VM) on AWS using Amazon EC2 (Elastic Compute Cloud) is straightforward. Here are the short steps to do so:

1. Sign in to AWS
Go to the AWS Management Console.
Sign in with your AWS account credentials.

2. Navigate to EC2
In the AWS Management Console, search for and select EC2 under the "Compute" section.

3. Launch an Instance
Click on "Launch Instance".

4. Choose an Amazon Machine Image (AMI)
Select an AMI (e.g., Amazon Linux, Ubuntu, Windows, etc.) that suits your needs.

5. Choose an Instance Type
Select the instance type (e.g., t2.micro for free tier eligibility).
Click "Next: Configure Instance Details".

6. Configure Instance Details
Configure the instance settings (number of instances, network, etc.).
Click "Next: Add Storage".

7. Add Storage
Adjust the storage settings if needed.
Click "Next: Add Tags".

8. Add Tags
(Optional) Add tags to organize and manage your instances.
Click "Next: Configure Security Group".

9. Configure Security Group
Set up firewall rules to control traffic (e.g., allow SSH on port 22).
Click "Review and Launch".

10. Review and Launch
Review your settings and click "Launch".
You’ll be prompted to select or create a key pair. This is important for SSH access to your instance. Download the key pair and keep it secure.

11. Access Your Instance
Once the instance is running, find its public IP or DNS.
Use an SSH client (e.g., terminal on Linux/Mac or PuTTY on Windows) to connect ssh -i /path/to/your-key.pem ec2-user@your-public-ip

12. Set Up Your VM
Once logged in, you can install software, configure settings, and deploy applications as needed.
-----------------------------------------------------------
STEP4 :RUNNING THE CODE IN VM

Install all the dependencies as needed (listed in the requirements file
-------------------------------------------------
sudo apt-get update
sudo apt-get install python3-pip
pip3 install -r requirements.txt


Make the migration to the production environment following the below code
------------------------------------------------------
python3 manage.py makemigrations
python3 manage.py migrate


Deploy the model in the server
---------------------------------------------------
python3 manage.py runserver 0.0.0.0:8000

running the server at - http://ec2-16-170-204-166.eu-north-1.compute.amazonaws.com:8000/home/upload
Prompt the input as needed we can see that our model is classifying the emotions for the uploaded image

