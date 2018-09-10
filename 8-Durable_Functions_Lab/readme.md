# Durable Functions Hands-On Lab

## Azure Portal Experience

![Architecture Diagram](images/architecture.png "Architecture Diagram")

### Create Funcitons App

 Browse to the azure portal [https://portal.azure.com](https://portal.azure.com)
1. Click the New button

    ![New Button](images/new_button.png "New Button")

1. Type "azure functions" into the search box and select Event Hub when it pops up

    ![Function App](images/function_search.png "Function App")

1. On the next blade select Function App

    ![Function App](images/function.png "Function App")

1. Then click "Create"

    ![Create](images/create.png "Create")

1. On the next screen select a unique name for your function app (confirm with checkmark), create new resource group, keep consumption plan selected for the hosting plan, and make sure you choose "On" for Application Insights and then click "Create"

### Modify Settings

Durable Functions are available in the Azure portal only after migrating to version 2 of the Azure Function Runtime. Version 2 is still in Preview. Please follow the instructions below.

1. After the app is created you can access it via the Funcitons button in the left menu

     ![Functions Menu](images/left-menu-smaller.png "Functions Menu")

2. From the list select the funciton app you created and then select Function app settings
   
     ![Functions App Details Screen](images/details-screen.png "Functions App Details Screen")

3. Next, select ~2 (Preview) for Runtime version. This will migrate the Functions runtime to version 2
    
    ![Migrate to Version 2](images/function-app-settings.png "Migrate to Version 2")

### Create Durable Functions

In this section we will create the Durable Functions.

1. Select the function app from the left menu and create a new function

     ![Create new function](images/create-new-function.png "Create new function")

2. Pick the Custom function option

    ![Create custom function](images/create-custom-function.png "Create custom function")

3. From the scenario dropdown select Durable Functions

    ![Durable Functions scenario](images/durable-functions-scenario.png "Durable Functions scenario")

4. We will need to create one of each Durable Functions type but let's start with Http Starter

     ![Http Starter](images/http-starter.png "Http Starter")

5. Since this is the first Durable Function under the Function app, an extension should be installed

    ![Durable Functions extension required](images/install-extension.png "Durable Functions extension required")

6. After pressing the install button it will take less than 2 minutes to complete

    ![Extension installation](images/extension-installation.png "Extension installation")

7. Press continue after the succesful installation

    ![Installation successful](images/extension-insalled.png "Installation successful")

8. Let's complete the creation of the Http Start function and call it HttpStart

    ![Create Http Start function](images/http-start-new-function.png "Create Http Start function")

9. The Http Starter function comes with autogenerted code that extracts any objects sent in the payload, starts new orchestration and returns the standard set of endpoints for managing and checking the status of the orchestration 

    ![Http Start code](images/http-start-code.png "Http Start code")

10. Next, let's create an activity function

    ![Create activity function](images/create-activity-function-details-screen.png "Create activity function")

11. Pick the activity function option

    ![Select activity function](images/activity.png "Select activity function")

12. Let's name it Hello

    ![Select activity function](images/create-activity-function-main-screen.png "Select activity function")

13. The autogenerated code is very simple and just appends hello to the name parameter 

    ![Activity code](images/activity-code.png "Activity code")

14. The last function we need is the orchestrator. Start by adding new function under the function app

    ![Create orchestrator function](images/create-orchestrator-function-details-screen.png "Create orchestrator function")

15. Select the Orchestrator type function

    ![Orchestrator](images/orchestrator.png "Orchestrator")

16. Let's name it Orchestrator

    ![Orchestrator Creation Screen](images/create-orchestrator-main-screen.png "Orchestrator Creation Screen")

17. The autogenerated code calls three time Hello activity function with different parameters 

    ![Orchestrator Code](images/orchestrator-code.png "Orchestrator Code")

### Test Durable Functions

In this section we will test our first Durable Function in the Azure Portal

1. Select the HttpStart funciton under the function app. Then click on Test section and provide Orchestrator for function name. Finally click the Run button at the bottom

    ![Test Durable Function](images/test-orchestrator.png "Test Durable Function")

2. The output is an JSON object. Use the statusQueryGetUri to find the Durable Function output

    ![JSON output](images/testing-response-links.png "JSON output")

3. Open the link and you will get the orchestration output

    ![Orchestrator JSON output](images/actual-response-json.png "Orchestrator JSON output")


Congratulations! You created your first Durable Function and you successfully run your first orchestration! 




    