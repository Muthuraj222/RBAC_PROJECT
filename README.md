Health Monitoring System Web App

A web application designed for monitoring health data using Role-Based Access Control (RBAC). Employees working in the company can register their data, such as ECG and BPM, which are compiled based on their employee ID and stored in MongoDB. The stored data is anonymized to protect personal identities because Data Scientists, who are also employees of the company, access this data for analysis.
Employees sign a disclosure agreement, enabling the implementation of an anonymization technique to de-identify their personal information, which is then stored in a separate collection in the local MongoDB database.

The app provides two types of access with basic authentication:

->Simple Comparison-Based Access: For employees who want to modify their disclosure or health data by entering their company ID.

->Blockchain-Based Access: For Data Scientists using Ganache (a local blockchain server) and the MetaMask browser extension for authentication. The login timestamp of each Data Scientist is recorded and stored in a MongoDB collection.

Steps to Run the Project:
->Start Ganache
->Open an Ubuntu terminal and type:
         ganache
->Select one of the private keys from the 10 accounts displayed in the Ganache server and import it into MetaMask.
Note: Each time Ganache restarts, the old accounts are reset, and new ones are created. You must re-import a new account into MetaMask for authentication.
=>Set Up MetaMask
->Install the MetaMask browser extension.
->Create a password for MetaMask.
->Add the local Ganache network:
->Navigate to the Ethereum Main Network.
->Click Add Network and configure it:
->Network Name: Ganache Localhost
->RPC URL: http://127.0.0.1:8545
->Chain ID: 1337
->Import a Ganache account using its private key.
=>Start MongoDB

=>In the Ubuntu terminal, start the MongoDB service:
        sudo systemctl start mongod
=>Optionally, open the GUI for MongoDB using Compass:
        mongodb-compass
Run the Project

=>Start the server by running:
        node server.js
=>Access the web app through the following URLs:
Employee Registration: 
         http://localhost:3000
Data Scientist Login: 
         http://localhost:3000/datascientist-login-page
Employee Admin Login: 
         http://localhost:3000/employee-admin-page
=>Features:

->Employee Registration: Allows employees to submit their health data securely.
->Data Anonymization: Protects employee identities by de-identifying personal data and storing it separately.
->Data Scientist Login: Grants Data Scientists access to anonymized data using blockchain-based authentication.
->Timestamp Recording: Logs the login time of Data Scientists into the blockchain and MongoDB.
->Employee Admin Access: Enables employees to update or modify their disclosure agreement or health data using their company ID.
