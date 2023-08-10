The final option is to configure your own private data provider. To do so, please follow the following steps:

1. Go to [NeuroHub Storage](https://portal.neurohub.ca/nh_storages) 
 
2. Click on _Storage Configuration_

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/05e7248f-0556-4704-9ae2-09bc378250c7)</kbd>

3. Configuration of your private data provider

Complete the form as per:

* **HOSTNAME**: this is the server’s name where you are getting the file from. 
In this example, I want to move a file from Compute Canada Beluga to the private data provider hosted in CBRAIN
* **USERNAME** of your Compute Canada Account
* **PATH**: where the file is located in Beluga

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/b0282e7c-a09c-4ae3-87c6-e94a31b0ec1b)</kbd>

4. SSH KEY SET UP

Before saving your configuration, you will need to configure the SSH in your host storage.
A public SSH key needs to be added to the authorized keys of the user on the host. Paste the SSH key bellow in a text file 

* If you use the nano or pico text editor, please make sure to use the
`-w`
option to prevent the editor from splitting the line of the key. The SSH key must all be in a single long line

* Run a command to add it to the authorized keys file on the host, as for an example the below one:
`ssh-copy-id -f -i key.pub username@hostname`

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/addd7584-54ee-4df9-9e84-14b32618c1c5)</kbd>

If you prefer, you can also directly create a `.ssh` directory on your host server, add the `authorized key` file in `.ssh` and copy the SSH key in that file without using the previous command line.

![image](https://user-images.githubusercontent.com/115739667/234660916-06c5ba4c-3c7b-4570-b8cd-1dc5a39521b5.png)

Now, you can save the configuration by clicking on **SAVE CONFIGURATION**

![image](https://user-images.githubusercontent.com/115739667/234661034-d1882ecf-0371-452b-9123-6c42b0618c4d.png)

![image](https://user-images.githubusercontent.com/115739667/234661086-d9398b5b-0df2-445b-860a-bba5c34cfe49.png)
 
5. TEST CONFIGURATION, AUTO REGISTER FILES and DECONFIGURE THIS STORAGE

To make sure your data provider has been successfully configured, you will have to test it before the files can be automatically registered. When you don't need it anymore, you will be able to deconfigure it as well.

![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/70c1e57f-d2b8-451c-97c1-f9d0677c4070)

* TEST CONFIGURATION by clicking on the button
 
A message will pop up confirming the configuration is successful

* AUTO REGISTER FILES by clicking on the button will confirm  how many files have been registered

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/0145db66-180f-4549-9347-3334ef3b2d40)</kbd>

You can now go to your **Projects**, and you will see the new file(s) uploaded under **Files** with the private data provider name:

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/ac5d3bfd-0243-4869-b027-52c79246adbc)</kbd>