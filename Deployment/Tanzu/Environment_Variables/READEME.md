## Adding environment variable to a TANZU application 
### Pre-requisite
**Tanzu Deployment stage**
### Steps 
1. This step to add an environment variable can be part of only an Tanzu deployment stage.
2. There are two version of the step 
* Re-stages the app after adding the environment variable 
* Only adds the environment variable 
3. Depending on your use case, choose the yaml and replace **{VariableName}** with your variable name and replace **{VariableValue}** with your variable value. You can duplicate the line if you have multiple variables to be added. 
4. After replacing the variable values, you can reference the above template in your template library by following the below steps. 
* Click Account Settings
* Click account resources
* Click Templates
* Click "**+ New Template**"
* Click "**Import from Git**"
* Provide "**Name**, **version**"
* Select **Harness-Template-Library** in the Git Connector, Once you select it should prefill your repository and git branch details.
* Provide "**Deployment/Tanzu/Environment_Variables/{template_version}.yaml**" in the YAML path.  
* Post creating the template, you can reference this template step in your deployment stage.
