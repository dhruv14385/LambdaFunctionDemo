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
 11. You can create another lambda function in a similar way that can start the stopped EC2 instances.

## Creating a lambda function that protects an EC2 instance from stopping.  
When we will try to stop an EC2 instance, this lambda function will be triggered by EventBridge and it will restart the EC2 instance.  
Follow the steps mentioned above to create a lambda function from a python script called 03_lambda_instance_protect.py from the repository.
After creating lambda function, follow the steps below to create an EventBridge event.  
1. Go to EventBridge, select EventBridge rule and click on Create rule.  
2. In Step 1, name your rule and go to next.  
3. In step 2, in Sample event, select 'EC2 instance State-change Notification'. Under Event pattern, choose EC2 as AWS Service and under Event type, choose 'EC2 Instance State-change Notification'  
4. In step 3, select Lambda function as Target.  
5. Finally, review and create rule.  

