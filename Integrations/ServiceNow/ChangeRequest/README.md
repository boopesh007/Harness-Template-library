## Service Now change request
### Read the status of a service now change request from Harness 
Using the template `snow_read_change_request_status.yaml`, you can read the status of a service now change request from Harness. 

### Steps
1. First base64 encode your credentials. Goto this link https://www.base64encode.org/. Enter your SNOW credentials in this format ```username:password```, click Encode. The output is your bearer token for SNOW.  
Note: You can use other modes of authentication as well, if you want to use other authentication mechanisms, then you can skip step 1, 2 and directly go to Step 3. After step 3, Provide the respective value for ```Authorization``` Header depending on your Auth mechanism.
2. Store the bearer token as a secret in Harness with the identifier ```Snow_Bearer_Token```. 
Follow the steps to create a secret in your Harness account.
* Click **Account Settings**
* Click **Account resources**
* Click **Secrets**
* Click **"+ New Secret"** and select **Text**
* Provide ```Snow_Bearer_Token``` as the name and your bearer token as the secret value.
3. The template needs to be onboarded onto Harness.
* Click Account Settings
* Click Account resources
* Click Templates
* Click "**+ New Template**"
* Click "**Import from Git**"
* Provide "**Name**, **version**"
* Select **Harness-Template-Library** in the Git Connector, Once you select it should prefill your repository and git branch details.
* Provide **Integrations/ServiceNow/ChangeRequest/snow_read_change_request_status.yaml** in the YAML path.
4. Reference the stage template in a pipeline
5. Run the pipeline and provide the inputs when prompted.

#### SOME COMMON RUNTIME INPUT DESCRIPTIONS
 1. ```snow_instance_name``` Your Service now instance name. Example if your service now url is https://xyz.service-now.com/, then xyz is your Service now is your instance name.
 2. ```change_request_id``` Your change request id in service now for which you want the status information. 