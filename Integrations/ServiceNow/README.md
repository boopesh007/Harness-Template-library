# Service now onboarding
1. First base64 encode your credentials. Goto this link https://www.base64encode.org/. Enter your SNOW credentials in this format ```username:password```. The output is your bearer token for SNOW.  
  Note: You can use other modes of authentication as well, if you want to use other authentication mechanisms, then you can skip step 1, 2 and directly go to Step 3. After step 3, Provide the respective value for ```Authorization``` Header depending on your Auth mechanism. 
2. Store the bearer token as a secret in Harness with the identifier ```Snow_Bearer_Token``` 
3. Copy the paste the YAML you require onto your Harness template library
4. Reference the template in a pipeline
5. Run the pipeline and provide the inputs when prompted. 

# SOME COMMON RUNTIME INPUT DESCRIPTIONS
### 1. ```snow_instance_name```  Your Service now instance name. Example if your service now url is https://xyz.service-now.com/, then xyz is your Service now instance name. 
### 2. ```change_request_id``` Your change request id in service now. 
