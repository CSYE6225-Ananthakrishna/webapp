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

Assignment 4:

This repository contains a web application built using nodeJS and PostgresSql as the database. The application includes RESTful API endpoints for users and products, which support GET, POST, and PUT methods.

Prerequisites:

To run the application, ensure that nodeJS, PostgresSql, and Packer are installed on your machine and added to the environment variables path. Also, make sure that Postman is installed to test the APIs.

Follow these steps to run the project:

1. Fork the web application repository and raise a pull request from the fork branch to the organization main with any small change.
2. The PR will trigger a GitHub workflow that merges the pull request and invokes the Packer file to build the AMI.
3. After the successful completion of the workflow, an AMI will be created in the dev AWS console.
4. Copy the AMI ID to the var.tfvars file in the cloned aws-infra repository.
5. Run the Terraform apply command with the var.tfvars file to create the EC2 instance in the dev/demo AWS console account.
6. Share the AMI created in dev with the demo account using the account ID configured while running the Packer template file.
7. Copy the public IP of the EC2 instance and paste it into Postman to test the API endpoints.
8. Start the server by running the command npm start in the terminal.
9. Use Postman to test the API endpoints as follows:

a. To add a new user, configure the method as 'POST' and enter http://{public_IP_of_EC2}:3000/v1/user in the request URL. Add first_name, last_name, username (email id), password in JSON format in the request body and click send.

b. To view a user's details, configure the method as 'GET' and enter http://{public_IP_of_EC2}:3000/v1/user/{ID} in the request URL. Set the authorization to basic authentication and enter the registered username as the email id and the password. Also, add the ID of the user in the URL and click send to get the data.

c. To update a user's details, configure the method as 'PUT' and enter http://{public_IP_of_EC2}:3000/v1/user/{ID} in the request URL. Set the authorization to basic authentication and enter the registered username as the email id and the password. Also, add the ID of the user in the URL. The user can only update the first_name, last_name, and password. Click send to update the data in the database.

d. To add a new product, configure the method as 'POST' and enter http://{public_IP_of_EC2}:3000/v1/product in the request URL. Add name, description, SKU, manufacturer, and quantity in JSON format in the request body. Only existing/authorized users can post products.

e. To view a product's details, configure the method as 'GET' and enter http://{public_IP_of_EC2}:3000/v1/product/{SKU} in the request URL. No authentication is done here.

f. To update a product's details, configure the method as 'PUT' or 'PATCH' and enter http://{public_IP_of_EC2}:3000/v1/product/{SKU} in the request URL. The user who creates the product can update its details. The values that need to be updated should be given in JSON format in the request body. The response for this call is the 'Data is Updated' message.

g. To delete a product, configure the method as 'DELETE' and enter `http://{public_IP_of_EC

Assignment 5:

In this assignment we are adding 4 new routes in our web application

1. POST : v1/product/productID/image -> to post a new image

2. GET : v1/product/productID/image -> to get all images

3. GET : v1/product/productID/image/imageId -> to get specific image

4. DELETE : v1/product/productID/image/imageId -> to delete a specific image

When we post and delete images , they should get uploaded and deleted in the S3 bucket in Aws ec2 instance

This assignment should ensure that our app runs in the ec2 instance and get connected to the rds instance.

Assignment 6: Namecheap

Registering a Domain Name:

Go to Namecheap or any other domain registrar and register a domain name. If you're a student, you can get a free .me TLD domain from Namecheap with the Github Student Developer pack.

Configuring Amazon Route 53:

1. Log in to your AWS account and go to the Amazon Route 53 console.
2. Create a public hosted zone for your domain name by clicking on "Create Hosted Zone" and entering your domain name (e.g. yourdomainname.tld) in the "Domain Name" field. Leave the other fields as default and click on "Create Hosted Zone."
3. After creating the hosted zone, you will see four Route 53 name servers listed for your hosted zone. Copy these name servers to use in the next step.
4. Go to Namecheap or your domain registrar's console and update the domain's name servers to the Route 53 name servers you copied in the previous step.
5. Create a subdomain and hosted zone for the dev AWS account by clicking on "Create Hosted Zone" again and entering "dev" in the "Name" field and selecting "Public Hosted Zone" in the "Type" field. Enter your domain name (e.g. yourdomainname.tld) in the "Domain Name" field and leave the other fields as default. Click on "Create Hosted Zone."
6. After creating the dev hosted zone, you will see four Route 53 name servers listed for the hosted zone. Copy these name servers to use in the next step.
7. Go back to the hosted zone for your main domain name and click on "Create Record Set." Enter "dev" in the "Name" field, select "A - IPv4 address" in the "Type" field, and enter the IP address of your dev server in the "Value" field. Leave the other fields as default and click on "Create."
8. Create a subdomain and hosted zone for the demo AWS account by repeating steps 5-7, replacing "dev" with "prod."

Assignment 7:


Assignment 8:


Assignment 9: