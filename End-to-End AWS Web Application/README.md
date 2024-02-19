In this project we are going to build an End-to-End application. We will use 5 differents AWS Services: AWS Amplify, AWS Lambda, Amazon API Gateway, Dynamo DB and AWS IAM.
The app will consist of mini calculator that takes two number and return the first number to the power of the second number. The results will be sored in a Dynamo DB Table.

Step 1: Host a webpage with Amazon Amplify
AWS Amplify is a set of products and tools that enable mobile and front-end web developers to build and deploy secure, scalable full-stack applications, powered by AWS.
![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/a5f34d29-3ea1-43dd-bb54-c293f27ccf27)



Step 2: The math Functionality

In this step, we are creating a lamda function that will will implement the function with Python.
We are going to run some Python code to do the calculation that we need which is the base power to the exponent.

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/0a720960-4500-4199-af68-e881824c0775)

Step 3: Use Amazon API Gateway to build REST APIs for user interaction with the app.

connect the API to the lamda function
![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/c084ee65-dd29-4dc8-a4ab-d38a318a0e07)

Step 4: Craete a Dynamo Db table to sore the result and  update Dynamo DB policy
![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/1994c9aa-a035-4523-a17a-92d5132c89dc)

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/1977d3e8-0afc-4963-943a-088b618e08f1)

Update the lamda funtion to write to the database:

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/990e2ed7-afb0-4bfd-b270-fb59cac422b0)


Test the application:
Redoploye your updated htnl code with Amazon Amplify:
![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/6a0b096b-8018-41b1-b75d-05af42b732c5)

Then run the app 
![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/9180985b-2d49-4ba5-a64f-8cd9e2bf968c)

And the result 126.0 will be stored in our Dynamo DB Table

![image](https://github.com/ChannickE/AWS_Projects/assets/148730724/78d4b381-6658-4ace-859e-24af6b30a7db)

