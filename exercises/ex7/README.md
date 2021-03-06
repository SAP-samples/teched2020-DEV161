# Exercise 7 - Run the app on Cloud Foundry

In this exercise, you will create the app's deployment artifacts, deploy the app to Cloud Foundry, and test run the app on Cloud Foundry.

## Exercise 7.1 - Configure the App to Use the Cloud Foundry Runtime

After completing these steps, you will know how to prepare the app for deployment to the Cloud Foundry runtime, and use the Cloud Foundry command line tools as well as SAP BTP Cockpit.

1. Open a new terminal using *[CTRL] + ~ keyboard* shortcut or *Terminal | New Terminal* from the menu bar.
<br><br>![](images/2020-10_BAS_Open_Terminal_.jpg)<br><br>

    > Tip: You can toggle maximize the view, in this case the terminal, by double-clicking its tab header.

2. Change directory to the `productsinventory` folder:
<br><br>![](images/2020-10_BAS_Change_Directory_.jpg)<br><br>

    ```Shell/Bash
    cd productsinventory
    ```

    > Tip: You can use auto-complete to enhance your productivity, e.g. in the terminal, type *cd pro* and press [TAB] to auto-complete.


3. Prepare the app for deployment to Cloud Foundry. The preparation includes two steps: 
a) Generating the deployment artifacts and turning the app into a multi target application (MTA).
b) Generating the SAP Fiori launchpad. 
Both parts are executed using the following command:
<br><br>![](images/2020-10_BAS_NPX-1_.jpg)<br><br>

    ```Shell/Bash
    npx fiori add deploy-config
    ```

4. For the *Adding deploy-config to the project.* step, select the following:

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Please choose the target | *Cloud Foundry* |
    | B | Generate project artifacts in root folder: /home/user/projects/products-inventory? | *Yes* (default) |
    | C | Enter MTA ID | *products-inventory* (default) |
    | D | Enter MTA Description | *SAP Fiori Freestyle Demo* |
    | E | Enter MTA Version | *0.0.1* (default) |
    | F | Destination name | *Northwind* (case sensitive) |

    <br><br>![](images/2020-10_BAS_NPX-2_.jpg)<br><br>

5. As a result of executing the `npx` command, you'll see that the project structure was updated accordingly.
    ><br>![](images/BAS_Project_After_Config_Deploy_.png)<br><br>

## Exercise 7.2 - Build for the Cloud Foundry Runtime

To build the app for deployment, right-click the `mta.yaml` file, and select *Build MTA*.
    <br><br>![](images/BAS_Build_MTA_.png)<br><br>

   >The task is run in a new tab called *Task: Build MTA*.
   ><br>![](images/BAS_Build_MTA_Task_.png)<br><br>

   >When the build task is complete, additional artifacts are added to the project. The artifact that is used for deployment is the MTA archive (MTAR) `product-inventory_0.0.1.mtar`.
   ><br>![](images/BAS_Project_After_Build_MTA_.png)<br><br>

## Exercise 7.3 - Log in to Cloud Foundry

1. Before deploying the app to Cloud Foundry, take a look at what your Cloud Foundry space looks like. Log in to your trial account and enter your Cloud Foundry organization (your subaccount in SAP BTP, Cloud Foundry environment) and the space to which you'll deploy the app. A new Cloud Foundry space should look as follows:
    <br><br>![](images/2020-10_SCP_CF_Space_Applications_Before_Deployment_.jpg)<br><br>
    ![](images/2020-10_SCP_CF_Space_Service_Instances_Before_Deployment_.jpg)<br><br>

2. Log in to the Cloud Foundry space to which you'll deploy the app. From the menu bar, select *View | Find Command* to open the command palette.
<br><br>![](images/2020-10_BAS_Command_Palette_Open_.jpg)<br><br>

    >You can also log in to Cloud Foundry by clicking the Home icon at the left-hand side of the status bar or, in the terminal, execute the *cf login* command and follow the same steps.

3. Select the command *CF: Login to cloud foundry*.
<br><br>![](images/BAS_CF_Login-1_.png)<br><br>

    >Type *cf* to filter commands.

4. When prompted, provide your credentials, select the API endpoint, organization, and space for your project.

    >The Cloud Foundry organization and space appear in the status line at the bottom left part of the screen.
    ><br>![](images/2020-10_BAS_CF_Login-2_.jpg)<br><br>

## Exercise 7.4 - Deploy to Cloud Foundry

1. To deploy the app to Cloud Foundry, right-click the `products-inventory_0.0.1.mtar` file, and select *Deploy MTA Archive*.
    <br><br>![](images/BAS_Deploy_MTA_Archive_.png)<br><br>

    >The task is re-using the *Task: Build MTA* tab and changes its title to *Task: Deploy MTA Archive*.
    ><br>![](images/BAS_Deploy_MTA_Task_.png)<br><br>

    >You can follow the deployment progress both in the *Task: Deploy MTA Archive* tab and in the *SAP BTP Cockpit*.

2. To see the results of the deployment to Cloud Foundry, go to the *Cloud Foundry* tab. Your Cloud Foundry space should look as follows:
    <br><br>![](images/2020-10_SCP_CF_Space_Service_Instances_After_Deployment_.jpg)<br><br>
    <br><br>![](images/2020-10_SCP_CF_Space_Applications_After_Deployment_.jpg)<br><br>

## Exercise 7.4 - Run the App on Cloud Foundry

1. To run the application on Cloud Foundry, in the *SAP BTP Cockpit*, go to the Cloud Foundry space to which you deployed the app, and click the *Applications* tab. Click *products-inventory-router*, and then click the link in the *Application Routes* section.
    <br><br>![](images/2020-10_SCP_CF_Space_Application_Routes_.jpg)<br><br>

    >To run the application on Cloud Foundry without accessing *SAP BTP Cockpit*, copy the link to the application from the deployment task (without the commas), paste it in a browser tab, and click [ENTER].
    ><br>![](images/BAS_Link_To_App_On_CF_.png)<br><br>


2. You should see the app running on Cloud Foundry.
    <br><br>![](images/2020-10_App_on_CF_.jpg)<br><br>

## Summary

Congratulations, you completed the [Run the app on Cloud Foundry](#Run-the-app-on-CF) exercise!

With this, you have successfully completed the deployment of your SAP Fiori app to SAP BTP, Cloud Foundry runtime using SAP Business Application Studio.

In this exercise, you used high productivity tools that are available out-of-the-box in SAP Business Applications Studio that make it easy to build and deploy applications as well as work in the Cloud Foundry environment.

You reached a major milestone of this session, the full app lifecycle: creation, enhancement, connection to a backend system, testing with mock data and real data, build, deployment to Cloud Foundry, and running the app on Cloud Foundry. 

You're awesome!

Continue to [Connect Your Project to SAP Continuous Integration and Delivery - Github Setup](../ex8/README.md).
