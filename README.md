# Deploy-a-serverless-web-application-using-AWS
In this project I am going to create a simple web application to do a  math equation – this will be done using serverless AWS services; Amplify, Lambda, API Gateway, Dynamo DB and IAM



In this project I am going to create a simple web application to do a  math equation – this will be done using serverless AWS services. 


•	I will need a way to create/host a webpage


•	A way to invoke the math functionality


•	A way to do some math


•	Somewhere to store/return the math result


•	A way to handle permissions

AWS services I will be using in this project


![image](https://github.com/user-attachments/assets/a353a88b-f5f2-42e2-af61-d5e3d32d8d50)

The first step in the project is to create my application using AWS Amplify, this was simply titled PowerOfMath we configured this to use the latest version of python and created a lambda function 

![image](https://github.com/user-attachments/assets/66ba5b13-16d5-45d7-9eb7-8a8d36201143)


My next step was to set up the lambda function, the use of the function was to solve the math question posed to it by users, the lambda function will be triggered by an API and I will give it the correct permissions to write to the dynamo db table. 

![image](https://github.com/user-attachments/assets/ff3ccea0-6d46-47d8-a29c-0399b4e36269)

I put the code into the function with our math equation in this case * to the power of * and in our test as seen below, the code returned an answer of ‘8.0’. I had to crate the relevant permissions in IAM to allow the lambda function to write to the database.

![image](https://github.com/user-attachments/assets/09ed98f3-6e15-41c0-99d1-48b72a420fc0)


![image](https://github.com/user-attachments/assets/89ab37e8-1e29-4988-8777-16e69339ae44)



With the lambda function set up and working, next I needed to set up an API Gateway and integrated it to the lambda function to trigger it. 



![image](https://github.com/user-attachments/assets/912895a8-478b-43c6-ba39-eaacc28fbafb)

![image](https://github.com/user-attachments/assets/9a3010f7-8186-4382-8356-11c56246218d)


![image](https://github.com/user-attachments/assets/1b30033a-1450-4c02-83e6-4061811648d6)

I wanted somewhere to store the results, the best options was to create a database. I chose to use Dynamo DB which I felt was most suited due to its structured table and being more lightweight than a relational database. I had to configure the DB so that I have full control over items, so I enabled the ability to put items, delete items etc, to do this I had to set the permissions in IAM to allow the lambda function to write to the database.


![image](https://github.com/user-attachments/assets/b885cf20-5927-4fcb-b9f1-c497a7a4a5b4)



![image](https://github.com/user-attachments/assets/db233da5-6b6f-4b22-a232-98fc7808bb6b)



Now I have the API, Lambda function, IAM permissions on the lambda function and my Dynamo DB set up, I now went and modified my application – I created the final version of the application, this is what users would see and interact with. The code used was inputted into a simple notepad which had to be saved and compressed into a zip folder, I then went back into my app on Amplify and re-uploaded the zip folder with the updated and final version of my application which would include all of the AWS services talked about so far.



![image](https://github.com/user-attachments/assets/a0a83da3-e81e-4ab6-ae3e-70ac9b2541ae)



The final version completed of my application ‘TO THE POWER OF MATH!’, the user would input their math equation so in this case 2 to the power of 8 an onscreen answer would populate as you can see the answer being 256.0.



![image](https://github.com/user-attachments/assets/923c4979-4296-4ec6-92aa-8e9060fedaf6)


Results as you can see were stored into the Database including date and time these were generated. 


![image](https://github.com/user-attachments/assets/9265a33f-c7b1-4d9f-b82f-cb81f2606058)






























