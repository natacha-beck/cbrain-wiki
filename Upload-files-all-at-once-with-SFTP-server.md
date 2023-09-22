If you have many files or files greater than 400 MB, please follow one of the 2 methods to upload them all at once.

#### Method 1: Filezilla or another GUI SFTP Client

If you are using Mac, Windows or Linux/Unix Operating systems, we recommend that you use Filezilla or another graphical user interface SFTP Client to transfer files.

* **Instructions for Filezilla:**
  * Download and install Filezilla on your computer
  * Select "File" menu, then click on "Site Manager"
  * Select "New Site"
  * Under "General Tab" in "Site Manager"
    * Enter hostname: ace-cbrain-1.cbrain.mcoill.ca
    * Enter port number: 7500
    * Select Server Type: SFTP - SSH File Transfer protocol
    * Select Logon Type: NORMAL
    * Enter the username and password for your CBRAIN account

<kbd>![image](https://user-images.githubusercontent.com/115739667/220480875-4e003254-570a-401e-adc3-598176fb134a.png)</kbd>  

* Under "Advanced" tab in "Site Manager"
    * Select "Bypass proxy"
    * Click connect

<kbd>![image](https://user-images.githubusercontent.com/115739667/220480672-42631307-22a7-41b4-bbe3-e148b6a5066b.png)</kbd>

  * Files on your local computer are listed on the left
  * Files on the remote computer are listed on the right
    * Files may be dragged to move them to and from the remote and local computers
    * Options for managing files are displayed by selecting the file and right clicking on the file

<kbd>![image](https://user-images.githubusercontent.com/115739667/220482265-d5b6a2ad-3d1b-4270-b996-47a864da5b5d.png)</kbd>

#### Method 2: Command line

It is very convenient to use a graphical user interface SFTP Client as described above.  However, if it is your preference you can use the command line.

Command-line users of MacOS X or Linux can connect using this sftp command, for instance:

``unix% sftp -o port=7500 myusername@ace-cbrain-1.cbrain.mcgill.ca``

Once your data files are uploaded, you need to **REGISTER** the files into CBRAIN before they can be processed. 

#### Common part: Move Files from Temporary Storage SFTP Server to Data Provider

At the top of CBRAIN page, go to _Resources_  and click on 'Data Providers' 

<kbd>![Screenshot 2023-04-28 at 2 10 16 PM](https://user-images.githubusercontent.com/115739667/235222472-08058556-0a17-474a-ac8a-a9bb22400fa5.png)</kbd>

This will show a list of Data Providers you have access to. The two special Data Providers SFTP-1 and SFTP-2 will be listed and each will be provided with a 'Browse' link.

<kbd>![image](https://user-images.githubusercontent.com/115739667/235228558-66f78556-9834-42b7-ac46-fd403b7fa03c.png)</kbd>

Click the 'Browse' link and you should see a list of files you already uploaded

  * Select the files to be registered
  * If the file format is not automatically detected correctly (e.g. "TextFile"), fix this by selecting the file format with the drop down menu under "Type" (click on "All files as…").

<kbd>![image](https://user-images.githubusercontent.com/115739667/235514719-f4a72ece-9509-4ca2-9a53-14c38046cc73.png)</kbd>

* Move your files from the temporary server to "MainStore":
  * Click on "Register Files" tab
  * Choose project where the files will go (e.g. "Example")
  * Select "Move the files to Data Provider"
  * Choose Data Provider where the files will go (e.g. "MainStore")
  * Click "Register the files"

<kbd>![image](https://user-images.githubusercontent.com/115739667/235515137-04bfccf8-e79b-480d-9f3c-c251ca01ecdb.png)</kbd>

*  Please note, if you register a large number of files, this can take some time.