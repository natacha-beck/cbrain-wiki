
Cell Ranger's pipelines analyze sequencing data produced from Chromium Single Cell Gene Expression. 
To know more about Cell Ranger please visit [10xgenomics](https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/what-is-cell-ranger)!

This section gives you a step-by-step process of the [Cellranger count](https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/using/count) tool.

## 1. Create YOUR project 

* Select _Create Project_

<kbd>![image](https://user-images.githubusercontent.com/115739667/234963069-b12b289b-43aa-4f52-8bb6-71a9d6096e5a.png)</kbd> 

A new window will pop up, allowing you to enter the name and description of your project 

<kbd>![image](https://user-images.githubusercontent.com/115739667/234963333-6819c164-09f2-4779-bf6f-bb2fd1ae4d16.png)</kbd>

* Click Create
* CBRAIN will confirm the project creation 
* The new project will be available on your Projects list view
* You can invite others to join by clicking on _Edit_ 

<kbd>![Screenshot 2023-04-27 at 2 55 13 PM](https://user-images.githubusercontent.com/115739667/234964476-74913960-171f-493e-9ae2-8fb42908e5cd.png)</kbd>

<kbd>![image](https://user-images.githubusercontent.com/115739667/234964772-e9dfd5d4-064b-42a4-bbb3-4c0e2049d338.png)</kbd>

## 2. Upload your file(s) to CBRAIN 

There are four ways to Transfer data in and out of CBRAIN:
* Transfer files [one by one](Upload-files-one-by-one) using the Web browser (works only for small files)
* Upload or download files using a [SFTP](Upload-files-all-at-once-with-SFTP-server) client to a special Data Provider
* Ask the CBRAIN admins to configure one or several Data Providers directly on a user's machine or at a user's lab.
* [[Configure a private data provider]]

## 3. Launch Cellranger count task

* File requirement: file(s) has to be registered as a [FASTQ](https://en.wikipedia.org/wiki/FASTQ_format) collection.

* Select your FASTQ Collection file(s).

For the purpose of this tutorial, the data have been downloaded directly from [10xgenomics](https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/using/tutorial_ct) and available [here](https://cf.10xgenomics.com/samples/cell-exp/3.0.0/pbmc_1k_v3/pbmc_1k_v3_fastqs.tar).

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/1db2b880-cbd8-48cd-84a2-bb7919aa60d8)</kbd>

Note: In most cases, more than one file is needed to run your Cellranger project. 
However, new collection creation will not be required if you only use one file. Simply select the file and launch the task as it is.

 * Launch 

Click on the Launch button, select the **tool**, **execution server** and the version then **Launch cellranger count**

If you want to run a quick run test, we recommend selecting Converter-1 or Converter-2.

<kbd>![tool_server](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/082828ec-511d-416d-9d50-2b688daa5a0f)</kbd>

* Task parameters settings

1. Choose the data provider where you want to save your results (for example MainStore)
2. Choose your project
3. Set up your Task parameters (transcription path and FASTQS data and prefix)

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/882e0031-8563-47c2-ad2c-06b914e6434f)</kbd>

4. Click Start cellranger-count

Once the task is running, you will get a notification advising the task is launched

* click on **Tasks** to monitor the status of your task(s)

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/9b6c6a30-998b-4472-960d-288bd94dbc3d)</kbd>

* Once your task is completed (or failed), you will get a new notification

* Go back to your task (by clicking on the task name) where you can see the information of your task including the input and output results

<kbd>![image](https://user-images.githubusercontent.com/115739667/235205394-3e7e1b22-f483-482c-8b6f-9183caa176ff.png)</kbd>

* Click on the Output files to view your results

<kbd>![image](https://user-images.githubusercontent.com/115739667/234685323-7570b03b-cd16-48e2-be05-40f960dc0d82.png)</kbd>

<kbd>![image](https://user-images.githubusercontent.com/115739667/234685379-18d7257b-9dfc-4cf5-ad13-211607f53f26.png)</kbd>

* Expand the outs file, as an example click on the web_summary_html and you will see the Cell Ranger counts results of your task


 



 


Fastql file
 
 

 

 
Mai note (will be removed )
ds le fasq collection there are 4 files 

![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/0eda5db5-4730-4c84-9d7d-95c21df17ced)

however it creates 2 tasks ( that is normal)
2 tasks 
•	HA776-s1 L007
•	HA800-S1 L006
•	les fichier vont par 2 voir 3	
•	Les HA776 vont ensemble (mais il pourrais y en avoir un 4eme)et les HA800 vont ensemble.

*Note* you can have HA800 and HA776 files in a single FASTQ Collection if you do so you will have to select both samples in the --sample field and then 
CBRAIN will launch 2 tasks one for HA800 and one for HA776.