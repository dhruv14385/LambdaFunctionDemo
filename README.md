# LambdaFunctionDemo
## Creating a simple lambda function which can start or stop EC2 instances.  
Follow these steps.  
 1. Go to IAM section in your AWS account, click on Policies on left and create a policy lambdarole.json  
 2. Create a role and attach above policy to it.
 3. Create 2 EC2 instances.
 4. Create a new lambda function from scratch. Call it 'EC2 stop'. 
 5. Choose runtime as Python 3.9  
 6. Assign the role you created above.  
 7. Copy code from 01_lambda_instance_stop.py and paste it into code source and deploy the function.
 8. Go Environment variables. Enter Key as 'EC2_INSTANCES' and instance_id of 2 EC2 instances in Value.
 9. Go to Test tab and enter Event name and then click on Test.
 10. Go to EC2 tab and you will notice that both EC2 instances are stopped now.
 11. 
