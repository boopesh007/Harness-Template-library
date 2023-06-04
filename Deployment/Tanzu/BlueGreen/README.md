## Tanzu application blue green deployment 
### What is a blue-green deployment ?
![bg.png](..%2F..%2F..%2F.ignore%2Fbg.png)
Blue-Green is about having two identical environments called “blue” (aka staging) and “green” (aka production) run simultaneously with different versions of service/artifact. QA and UAT are typically done in the blue environment. When satisfied, traffic is flipped (via a load balancer) from the green environment (current version) to the blue environment (new version). You then have the option of decommissioning the old environment or rolling back to it should your deployment succeed or fail.
### Pre-Requisites steps
Please follow the instructions at the Tanzu section to complete the pre-requisites.  
**1. Service onboarding**  
**2. Environment onboarding**  
**3. Cloud Infrastructure connector configuration**


### Steps
1. Complete your Pre-requisite steps. 
2. Provide your **ROUTE** on the vars.yaml 
3. Reference the above template in your template library. 
* Click Account Settings
* Click account resources
* Click Templates
* Click "**+ New Template**"
* Click "**Import from Git**"
* Provide "**Name**, **version**"
* Select **Harness-Template-Library** in the Git Connector, Once you select it should prefill your repository and git branch details. 
* Provide "**Deployment/Tanzu/BlueGreen/blue_green_deployment.yaml**" in the YAML path.  
4.You can edit the template values if you want to. Switch to the visual mode to have a better experience while updating the values. 