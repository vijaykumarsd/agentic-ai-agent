## Project Kisan Backend Setup and Running Guide
This document outlines the steps to set up and run the FastAPI backend for the Project Kisan application.

## Backend Setup (FastAPI)
Clone the Repository:

git clone <your-backend-repo-url>
cd project-kisan-service

Create a Virtual Environment (Recommended):

python3 -m venv venv
source venv/bin/activate # On Windows: .\venv\Scripts\activate

Install Python Dependencies:

pip install -r requirements.txt

If pip is not found, refer to the "How to install pip" section in previous conversations.

Set up Environment Variables:

Create a .env file in the project-kisan-service directory (next to main.py).

Add your Firebase service account key path and any other necessary environment variables.

Important: Replace your-service-account-key.json with the actual name of your downloaded service account key file if you didn't rename it to serviceAccountKey.json.

GOOGLE_APPLICATION_CREDENTIALS =your-service-account-key.json
# Optionally, if you need to specify the model name or other settings
MODEL_NAME =gemini-2.0-flash
PORT=8005 # Or any other port you prefer

Update Firebase Storage Bucket Name:

In main.py, locate the storage_bucket_name variable in the Firebase initialization section.

Ensure it matches your actual Firebase Storage bucket name (e.g., your-project-id.appspot.com). You can find this in the Firebase Console under "Storage."

# main.py
# ...
storage_bucket_name = "your-project-id.appspot.com" # <-- Update this line
# ...

Running the Application
Running the Backend
Activate your virtual environment (if you closed your terminal):

cd project-kisan-service
source venv/bin/activate # On Windows: .\venv\Scripts\activate

Start the FastAPI server:

uvicorn main:app --host 0.0.0.0 --port 8005 --reload

The --reload flag is useful for development as it restarts the server on code changes.
 