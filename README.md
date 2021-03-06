# Photo-link
## The Idea
Photo-link is a service for turning photos sent from a phone into a link that can be shared with others. Some phones and phone services have trouble sending and receiving photos, so this would help those who may not be able to send a photo directly to someone. The way it works is that a user would send a photo to a number that is associated with Twilio. Once the image is received, it would be analyzed by AWS Rekognition, to make sure it is not inappropriate. If it is okay, the photo goes through API Gateway to be stored and hosted using S3 and DynamoDB. A link to that photo is then sent back to the sender. This link can be shared to others, so they can see the photo. 

![web app reference architectureweb app reference architecture-5](https://user-images.githubusercontent.com/12687830/34067367-244031ca-e1f2-11e7-97e1-5a345dc1c9de.png)
## The Code
#### TwilioRequest.txt
In this file is the request code you will need to use for sending texts back to the user who sent the text. First, you need to make a Twilio account and purchase a phone number than can receive mms. Then, in Twilio's dashboard, select that number and then build to create a send request. You must add your Twilio account id and the numbers you will be sending to and using to recieve. You can change the body to whatever message you want to send.

#### basic_lambda_function.py
Structures the message components for storage.

#### lambda_function.py
This portion is where the message would be analyzed, saved, and hosted. To use this, you need to add in your AWS keys, the names of your bucket, table, and region.

###### Note
Unfortunately, this service is not complete, so it still needs some work before being fully functional.

