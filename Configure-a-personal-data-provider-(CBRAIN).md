The final option is to configure your personal data provider. To do so, please follow the following steps:

1. Go to [CBRAIN Data providers](https://portal.neurohub.ca/data_providers) 
 
2. Click on _Create Personal Data provider_

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/8e148428-41a3-49cd-b954-f6cac51ca4e9)</kbd>

3. Add New Personal SSH-based Data Provider

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/260bb98c-19bd-494b-813a-fa9e15d75e68)</kbd>

Complete the form as per:

* **Name**: Name of the personal data provider
* **Description**: Short description
* **Project**: assigned project
* **Remote Hostname**: this is the server name where you get the file. 
In this example, I want to move a file from Compute Canada Beluga to the personal data provider hosted in CBRAIN
* **Remote Username** of your Compute Canada Account
* **Full Directory Path**: where the file is located in Beluga

4. SSH KEY SET UP

Before saving your configuration, you will need to configure the SSH in your host storage.
A public SSH key needs to be added to the authorized keys of the user on the host. Paste the SSH key provided on CBRAIN in a text file 

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/fb9d4815-1b0c-4d65-afc3-6a4a631464d5)</kbd>

* If you use the nano or pico text editor, please make sure to use the
`-w`
option to prevent the editor from splitting the line of the key. The SSH key must all be in a single long line

* Run a command to add it to the authorized keys file on the host, as for an example the below one:
`ssh-copy-id -f -i key.pub username@hostname`

If you prefer, you can also directly create a `.ssh` directory on your host server, add the `authorized key` file in `.ssh` and copy the SSH key in that file without using the previous command line.

![image](https://user-images.githubusercontent.com/115739667/234660916-06c5ba4c-3c7b-4570-b8cd-1dc5a39521b5.png)

Now, you can click on **Create new Data Provider**
 
5. TEST CONFIGURATION, AUTO REGISTER FILES and DECONFIGURE THIS STORAGE

To make sure your data provider has been successfully configured, you will have to test it before the files can be automatically registered. When you don't need it anymore, you will be able to deconfigure it as well.

![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/70c1e57f-d2b8-451c-97c1-f9d0677c4070)

* TEST CONFIGURATION by clicking on the button
 
A message will pop up confirming the configuration is successful

* AUTO REGISTER FILES by clicking on the button will confirm  how many files have been registered

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/0145db66-180f-4549-9347-3334ef3b2d40)</kbd>

You can now go to your **Projects**, and you will see the new file(s) uploaded under **Files** with the private data provider name:

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/ac5d3bfd-0243-4869-b027-52c79246adbc)</kbd>