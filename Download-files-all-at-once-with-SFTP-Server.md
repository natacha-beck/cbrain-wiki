* Select the file(s) you want to download 
* Click "copy"

<kbd>![image](https://user-images.githubusercontent.com/115739667/224405424-79d94315-c2c6-42ea-adc4-a3811f9345db.png)</kbd>
* Select a SFTP data provider in this case "SFTP-1" from drop down menu 
* Click "copy"

<kbd>![image](https://user-images.githubusercontent.com/115739667/224405613-117c400a-c0f4-4f14-a332-c289ad8aeb61.png)</kbd>

##### Method 1: Filezilla or other GUI interface SFTP client

* Open Filezilla (or other) application
* Use same SFTP settings as before ([3.2](Upload-files-all-at-once-with-SFTP-server)), but transfer files in the opposite direction
* Drag/drop files from SFTP-1 to your computer

##### Method 2: Command line SFTP

Use commands to change to the right directory and download files:
* cd < directory_name_to_download_files >
* sftp -o port=7500 myusername@ace-cbrain-1.cbrain.mcgill.ca 
* get -r *

**Note**: depending on your system, you may get an error message if you try to download files that haven’t been archived using get -r *. If this is the case,  go to "File Management", and click on
**"(Un)Archive" to archive files. This is a toggle switch, meaning that if a file is unarchived it will archive it, and vice versa. Once archived, copy it to the SFTP server. Then do the following:
* cd < directory_name_to_download_files >
* sftp -o port=7500 myusername@ace-cbrain-1.cbrain.mcgill.ca
* get */*.tar.gz

##### Common part: Delete your data from the temporary storage SFTP Server

* Click on "Resources" and drop-down menu to "Data Providers"

<kbd>![Screenshot 2023-04-28 at 2 10 16 PM](https://user-images.githubusercontent.com/115739667/235222472-08058556-0a17-474a-ac8a-a9bb22400fa5.png)</kbd>

* Click on "Browse" to the right of your Data Provider 

<kbd>![image](https://user-images.githubusercontent.com/115739667/235222728-c7faeedb-9466-4462-8c3b-fb2a4e9cd856.png)[[/interface-guides/user-guides/images/go_browse.png]]</kbd>

* Select the files you want to delete and click "Delete Files"
<kbd>![image](https://user-images.githubusercontent.com/115739667/235223109-0b104a3d-4bda-4502-b53c-e62bd4ea3f66.png)</kbd>
