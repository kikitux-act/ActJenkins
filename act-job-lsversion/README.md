# List Actifio VDP version

The following is a good start on how you can integrate Jenkins with Actifio VDP appliance. We will be using the Jenkins freestyle job and perform the Build using PowerShell scripts.

![image](https://user-images.githubusercontent.com/17056169/70362640-c6c52480-18d9-11ea-9aa5-bbf4e63d4856.png)

You will need to have a Jenkins instance running on Windows and ActPowerCLI installed. If you need information on how to install the ActPowerCLI module, please checkout https://github.com/Actifio/powershell or https://github.com/Actifio/powershell/tree/master/setup-actpowercli . Also, check under Plugin Manager to ensure that PowerShell plugin is installed. This plugin is required to support Windows PowerShell as build scripts.

We will be creating a Jenkins job that accepts Actifio VDP CLI user and credentials, login to the appliance and lists out the VDP version.

## Step 1:
Login to the Jenkins server and create a freestyle project by clicking on the New Item link on the top left hand corner. Enter the name of the job - act-job-lsversion , and click on Freestyle project. Click OK to confirm.

## Step 2:
In this job, we want to allow the user to provide inputs when running the job. We will create three parameters: ActUser, ActPass and ActIP by checking on the This project is parameterized. ActUser and ActIP will be of String type, whereas ActPass will be Password type.
![image](https://user-images.githubusercontent.com/17056169/70215213-206e0780-1791-11ea-8749-e612266cc0b7.png)

## Step 3:
Go to the Build section and define the tasks required to build the job. We will be making calls to Actifio VDP appliance using the commands in ActPowerCLI modules. You can copy and paste the source code from https://github.com/Actifio/ActJenkins/blob/master/act-job-lsversion/act-job-lsversion.ps1 into the PowerShell Build window .

## Step 4:
To build the job, click on Build with Parameters to kick it off. If required, you can change any the build parameters before triggering the build. 
![image](https://user-images.githubusercontent.com/17056169/70215366-6fb43800-1791-11ea-907c-89c8ba525145.png)

## Step 5:
Once it's completed, click on the Console Output to view the output of the job. An example of the output is as follow:
![image](https://user-images.githubusercontent.com/17056169/70215685-24e6f000-1792-11ea-8326-a1e1a96f2604.png)

---
   
https://www.youtube.com/watch?v=Mblnx0pxobw   
