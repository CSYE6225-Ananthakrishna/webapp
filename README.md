# webapp

Assignment 1: Webapp


Prerequisites:

1. Node.js and npm (Node Package Manager) installed on your system.
2. PostgreSQL database installed and set up, with a user and password.
3. Basic understanding of Node.js and SQL.

Build Instructions:

1. Create a new Node.js project using npm init.
2. Install the required packages using npm install, including express, pg (PostgreSQL client), crypto and any other necessary packages.
3. Create a new file for the database connection and configure the connection using the pg package.
4. Set up the models for the database tables.
5. Implement the RESTful API routes using express.
6. Test the API using a tool like Postman or curl.

Deploy Instructions:

1. Choose a hosting platform for the Node.js application, such as Heroku, Amazon Web Services (AWS), or Google Cloud Platform (GCP).
2. Create a new app on the chosen platform.
3. Connect the app to the PostgreSQL database.
4. Deploy the Node.js application code to the hosting platform.
5. Test the deployed application to ensure it is working as expected.

Steps to execute:

1. Clone the repository to your local machine using the git clone command: git clone <repository-url>.
2. Navigate to the repository directory using the cd command: cd <repository-directory>.
3. Install the required dependencies by running the command npm install.
4. Check if the application has a configuration file, such as .env, and set up any necessary environment variables.
5. Start the application by running the command npm start or node index.js (or another file name if the entry point is different).
6. Check if the application is running correctly by visiting the URL specified in the console output or in the app's configuration file.
7. Make any necessary changes to the code and push the changes back to GitHub using the git push command.

Assignment-2

The RESTful API Endpoints implemented are

1. POST - to add new products to the table in the database POST is used. The values to be given in JSON are name, description, sku, manufacturer and quantity. API address is http://localhost:3000/v1/product. If any one field is missing then the error message is "Incomplete Data". Basic authorization is used to check if the user exists. Only existing/authorized users can post the products.
 
2. GET - to view all the values present in the table GET is used. sku of the particular product should be given in the url for the POSTMAN to show the response. API address will be http://localhost:3000/v1/product/{sku}. no authentication is done here.
 
3. PUT/PATCH - to update the values like name, description, sku, quantity and manufacturer PUT/PATCH is used. sku should be a unique value. Basic authorization should happen successfully when a user wants to update the values. API address will be http://localhost:3000/v1/product/{sku}. The values that need to be updated should be given in the json format. The response for this call is the 'Data is Updated' message. Only user who creates the product can update the details

4. DELETE - to delete the row in the table products basic authentication have to be successful and only user who creates the product can delete it. API address will be http://localhost:3000/v1/product/{sku}

All the values in rows in table format can be viewed using pgAdmin

Steps to run the project:

1. Clone the github repository.
2. In VS Code, open the folder and run npm install which will install all the dependencies.
3. In order to run the application, open a terminal and run command "npm start".
4. To test the code, run "npm test" on terminal.

Packer: