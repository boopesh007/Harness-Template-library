## Tanzu application
### What is a Tanzu application 
What is a Tanzu application platform ?
Tanzu is a suite of products that helps users run and manage multiple Kubernetes (K8s) clusters across public and private “clouds”. While introducing Kubernetes as a first class VMware product, it still keeps strong ties to the VMware virtualization portfolio. It consists of:
### Pre-Requisites 
These steps which have to be performed before using any of the templates related to Tanzu deployment  

**1. Service onboarding ( What you want to deploy ? )**   
Onboarding your Tanzu application onto Harness as a service.  
**2. Environment and Infra onboarding ( Where you want to deploy ? )**  
Creating Tanzu connector that will connect Harness to your TAZ infrastructure in cloud. 

### Service onboarding
### Steps
**1. Artifact source configuration**  
The build job of you code would you have pushed the output which is the artifact to a artifact repository. Usually it will be container registries like Docker hub, Azure Container Registry, Google Cloud registry etc. The artifact in such cases would be the docker image. Depending on your artifact repository, you need to connect the respective artifact repository onto Harness. You can create your artifact repository connector in the connector section of your project or at the account resources section.  

**2.** **Onboarding the service onto Harness**  
Now you are ready with your artifact which needs to be deployed. We need to onboard the service onto Harness.
* Goto your Harness Account
* Click Account Settings 
* Click account resources
* Click Services 
* Click on "**+ New Service**"
* Click on "**Yaml**"
* Copy and past the "service.yaml" from above and paste the yaml there
* Click "Save"

### Environment and Infra onboarding
### Steps
**1. Configuring your TAZ infra**  
This will answer the "Where you want to deploy ?" 
* Goto your Harness Account
* Click Account Settings
* Click account resources
* Click Connectors 
*  Click on "**+ New Connector**"
* Select **Tanzu Application Service** from the Cloud providers section
* Provide **Name**, continue 
* Provide **URL**, **username**, **password**, continue
* Choose the way you want to connect to your cloud provider, depending on your security policies. Delegate is a Harness agent running on your premises to coordinate deployments and various other activities depending on your usecase. If you are concerned about a 3rd party tool like Harness connecting to you're infra / Firewall rules will prevent requests from external IPs, You can choose the Delegate approach. But make sure you install a Harness Delegate on your cloud infra choosing that approach. Details on configuring your delegate is given here https://developer.harness.io/tutorials/platform/install-delegate/
* Click on **Finish** once your connection test is successful 

**2. Onboarding the environment onto Harness**
* Goto your Harness Account
* Click Account Settings
* Click account resources
* Click Environments
* Click on "**+ New Environment**"
* Give a Name and select the type of environment
* Click "Save"

**3. Mapping your infra to your environment**  
Once your environment is created, the next step is to map which part of your cloud infra is what environment of yours. 
In your env 
* Click **Infrastructure Definitions**
* Click on **+ Infrastructure Definition**
* Click on "**Yaml**"
* Copy and past the "infra.yaml" from above and paste the yaml there
* Click "Save"



