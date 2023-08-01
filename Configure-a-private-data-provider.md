1. Go to NEUROHOB ->MAIN PAGE->STORAGE

![image](https://user-images.githubusercontent.com/115739667/234659957-e1c06adf-b98e-4d27-84d9-94f1f7a372b6.png)
 
2. Create Storage Configuration

![image](https://user-images.githubusercontent.com/115739667/234660027-fca7dadf-d9b0-405d-9588-7506822b49de.png) 

3. Configuration of your private data provider

* **HOSTNAME**: this is the server’s name where you are getting the file from. 
In this example, I want to move a file from Compute Canada Beluga to the private data provider hosted in CBRAIN
* **USERNAME** of your Compute Canada Account
* **PATH**: where the file is located in Beluga

![image](https://user-images.githubusercontent.com/115739667/234660210-db0bac95-86fa-4b2c-8094-082c9229b344.png)

4. SSH KEY SET UP

Before saving your configuration, you will need to configure the SSH in your host storage.
A public SSH key needs to be added to the authorized keys of the user on the host. Paste the SSH key bellow in a text file 

* If you use the nano or pico text editor, please make sure to use the
`-w`
option to prevent the editor from splitting the line of the key. The SSH key must all be in a single long line

* Run a command to add it to the authorized keys file on the host, as for an example the below one:
`ssh-copy-id -f -i key.pub username@hostname`

![image](https://user-images.githubusercontent.com/115739667/234660697-de9acbe1-d903-48e4-ba86-fc4475890fff.png)

If you prefer, you can also directly create a `.ssh` directory on your host server, add the `authorized key` file in `.ssh` and copy the SSH key in that file without using the previous command line.

![image](https://user-images.githubusercontent.com/115739667/234660916-06c5ba4c-3c7b-4570-b8cd-1dc5a39521b5.png)

Now, you can save the configuration by clicking on **SAVE CONFIGURATION**

![image](https://user-images.githubusercontent.com/115739667/234661034-d1882ecf-0371-452b-9123-6c42b0618c4d.png)

![image](https://user-images.githubusercontent.com/115739667/234661086-d9398b5b-0df2-445b-860a-bba5c34cfe49.png)
 
5. TEST CONFIGURATION & AUTO REGISTER FILES

* TEST CONFIGURATION by clicking on the button
 
A message will pop up confirming the configuration is successful

![image](https://user-images.githubusercontent.com/115739667/234661194-91603ef6-d92b-46dc-9208-fccbb6801f4d.png)

* AUTO REGISTER FILES by clicking on the button will confirm  how many files have been registered

![image](https://user-images.githubusercontent.com/115739667/234661593-f75ab506-41b6-4393-babe-e991d65a5e82.png)

You can now go to your **Projects**, and you will see the new file(s) uploaded under **Files** with the private data provider name:

<kbd>![image](https://user-images.githubusercontent.com/115739667/234966098-814dc918-4772-4adc-a602-fcb58e8d5fad.png)</kbd>