The final option is to configure a personal data provider. 

<img src= "https://github.com/aces/cbrain/assets/115739667/4c6d6f42-19ed-423e-9783-55a0fbf541c0.png" width="50">
Given the Alliance now requires 2-Factor authentication to connect to their supercomputers, the use of personal
Data Provider is no longer supportable by CBRAIN for the Alliance systems and will no longer function

Creating a personal data provider will have great advantages such as connecting storage on systems such as lab-based systems, that don't require 2-factor authentification.

To do so, please follow the subsequent steps:

#### 1. Go to [CBRAIN Data providers](https://portal.neurohub.ca/data_providers) 
 
#### 2. Click on _Create Personal Data provider_

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/8e148428-41a3-49cd-b954-f6cac51ca4e9)</kbd>

#### 3. Add New Personal SSH-based Data Provider

A new page will pop up asking you to complete the following form:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/260bb98c-19bd-494b-813a-fa9e15d75e68)</kbd>

Complete the form as per:

* **Name**: Name of the personal data provider
* **Description**: Short description
* **Project**: assigned project
* **Remote Hostname**: this is the server name where you get the file. 
In this example, I want to move a file from Compute Canada Beluga to the personal data provider hosted in CBRAIN
* **Remote Username** of your Compute Canada Account
* **Full Directory Path**: where the file is located in Beluga

#### 4. SSH KEY SET UP

Before saving your configuration, you will need to configure the SSH in your **host** storage.
A public SSH key needs to be added to the authorized keys of the user on the host. Paste the SSH key provided on CBRAIN in a text file 

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/fb9d4815-1b0c-4d65-afc3-6a4a631464d5)</kbd>

* If you use the nano or pico text editor, please make sure to use the
`-w`
option to prevent the editor from splitting the line of the key. The SSH key must all be in a single long line

* Run a command to add it to the authorized keys file on the host, as for an example the below one:
`ssh-copy-id -f -i key.pub username@hostname`

If you prefer, you can also directly create a `.ssh` directory on your host server, add the `authorized key` file in `.ssh` and copy the SSH key in that file without using the previous command line.

![image](https://user-images.githubusercontent.com/115739667/234660916-06c5ba4c-3c7b-4570-b8cd-1dc5a39521b5.png)

Now, you can click on _Create new Data Provider_

<img src= "https://user-images.githubusercontent.com/115739667/223515025-f546da2a-831c-4478-abec-4ae7f2db6942.png" width="50">**Note**:

Please remember to manually push the CBRAIN SSH key to the cluster if you want the _personal data provider_ to be connected directly,  otherwise, you will get the following message:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/148bc6f2-5b5c-4c05-a2b3-5694701a24c3)</kbd>

To push the CBRAIN SSH key, please go to _My account_ then edit _your System SSH Key_

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/d5e9408f-4d3e-4408-a74b-b1df3c58dc80)</kbd>

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/a4fc1589-9069-49e4-8254-201c6d4a9a9d)</kbd>

#### 5. TEST CONFIGURATION, REGISTER FILES and DELETE 

To make sure your data provider has been successfully configured, you will have to test it before the files can be automatically registered. When you don't need it anymore, you will be able to deconfigure it as well.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/86eac441-2f96-4c61-b375-5bd41a8e5761)</kbd>

* TEST CONFIGURATION 
 
By clicking on the button, a message will pop up confirming the configuration is successful

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/e1637f3e-6515-409b-8ee3-845c32fe1b63)</kbd>

* REGISTER FILES

Please go to [Resources Data Providers](https://portal.neurohub.ca/data_providers) and select the personal data provider.

Click on browse and you will see the files available to be registered

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/1125d2fd-7168-486f-82d5-b242dc4b5a9d)</kbd>

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/ac772c16-afb0-4db0-b0fc-2a7cc19f86be)</kbd>

You can now go to the project you assigned the files, and you will see the new file(s) uploaded under **Files** with the personal data provider name:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/7f46c12d-cc69-43a7-a57e-78583367ad10)</kbd>

* DELETE

If you want to delete this personal storage, simply select your personal data provider from the list the list and click delete:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/0641e024-9c8f-456c-b317-9feb7273098d)</kbd>

