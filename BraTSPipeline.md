As highlighted in [BraTS Toolkit: Translating BraTS Brain Tumor Segmentation Algorithms Into Clinical and Scientific Practice](https://www.frontiersin.org/articles/10.3389/fnins.2020.00125/full) remains a major challenge.

When it comes to neuroinformatics, data standardization and preprocessing can be challenging and slow down clinical and scientific practices such as brain tumor segmentation.
To overcome these issues, BraTS Toolkit has been implemented and is now fully integrated in CBRAIN.

> BraTS Toolkit is a holistic approach to brain tumor segmentation and consists of three components: First, the BraTS Preprocessor facilitates data standardization and preprocessing for researchers and clinicians alike. It covers the entire image analysis workflow prior to tumor segmentation, from image conversion and registration to brain extraction. Second, BraTS Segmentor enables orchestration of BraTS brain tumor segmentation algorithms for generation of fully-automated segmentations. Finally, Brats Fusionator can combine the resulting candidate segmentations into consensus segmentations using fusion methods such as majority voting and iterative SIMPLE fusion. 

For more information about the BraTS pipeline, please visit the [Cancer Imaging Phenomics Toolkit](https://cbica.github.io/CaPTk/preprocessing_brats.html) and [BraTS github ](https://github.com/neuronflow/BraTS-Toolkit) pages.

## 1. Create your project

* Select _Create Project_

<kbd>![image](https://user-images.githubusercontent.com/115739667/234963069-b12b289b-43aa-4f52-8bb6-71a9d6096e5a.png)</kbd> 

* A new window will pop up, allowing you to enter the name and description of your project 

<kbd>![image](https://user-images.githubusercontent.com/115739667/236532750-3ce8d79f-e120-4bf1-bdd8-060d5d1dfb3e.png)</kbd>

* Click Create
* CBRAIN will confirm the project creation 
* The new project will be available on your Projects list view
* You can invite others to join by clicking on _Edit_ 

<kbd>!<img width="1425" alt="Screenshot 2023-05-05 at 1 57 51 PM" src="https://user-images.githubusercontent.com/115739667/236533564-0f306842-d890-4897-a021-28c3a6e8846a.png"></kbd>

<kbd>![image](https://user-images.githubusercontent.com/115739667/236534186-6e4f3c94-fba2-4182-84f2-4c8a94df31e3.png)</kbd>

## 2. Upload your file(s) to CBRAIN 

There are four ways to [Transfer data](How-to-Transfer-files) in and out of CBRAIN:
* Transfer files [one by one](Upload-files-one-by-one) using the Web browser (small files)
* Upload or download files all at once using a [SFTP](Upload-files-all-at-once-with-SFTP-server) client to a special Data Provider 
* Ask the CBRAIN admins to configure one or several Data Providers directly on a user's machine or at a user's lab.
* [[Configure a personal data provider (CBRAIN)]]

## 3. Launch BraTS task

### Select your input files
The input pules required to launch the task are 4 mandatory structural MRI images, preferably in NIfTI format or DICOM :
* T1 
* T1CE 
* T2
* FLAIR

For the purpose of this tutorial, we are getting the files from [Github BraTS Toolkit example data](https://github.com/neuronflow/BraTS-Toolkit/tree/master/example_data) and transferring using the web browser.** @Mai - Can you please indicate the source location from where you downloaded the 4 example input data files to BraTS?

<kbd>![image](https://user-images.githubusercontent.com/115739667/236532203-1e5d1668-84e6-4af0-9f65-b6d99966fc87.png)</kbd>

### Launch 

Click on the Launch button, select the tool and execution server then **Launch BraTSpipeline**

<kbd>![image](https://user-images.githubusercontent.com/115739667/236537884-80e4d331-23e1-4ce7-a442-4997b114a384.png)</kbd>

### Task parameters settings

1. Choose the data provider to save your results to (for example MainStore)
2. Choose your project

<kbd>![image](https://user-images.githubusercontent.com/115739667/236539044-19a655e7-d660-4a17-8c53-9a724f7cd7b4.png)</kbd>

3. Set up your Task parameters

<kbd>![image](https://user-images.githubusercontent.com/115739667/236539271-623a1965-7940-4a8a-bc21-f054270f8836.png)</kbd>

<kbd>![image](https://user-images.githubusercontent.com/115739667/236540189-30d86284-5e28-4834-b1fe-bb5a5fa8f1ba.png)</kbd>

4. Click Start BraTS pipeline

Once the task is running, you will get a notification advising the task is launched

<kbd>![image](https://user-images.githubusercontent.com/115739667/236540543-12d08390-092d-4c72-839f-f0bbd8c36eaa.png)</kbd>

### Task monitoring

You can continuously monitor your task by clicking on Tasks and check the _Current Status_

<kbd>![image](https://user-images.githubusercontent.com/115739667/236543725-32a341c5-1fc0-4914-96cc-944ef442ffb8.png)</kbd>

## 4. Visualize the Output

* Once your task is completed (or failed), you will get a new notification

<kbd>![image](https://user-images.githubusercontent.com/115739667/236542993-6b337d7f-2c9f-4d4b-9c1f-cf14792df1e9.png)</kbd>

* Go back to your task (by clicking on the task name) where you can see the information of your task including the input and output results

* Click on the Output files to view your results

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/76490edd-b302-4c95-b403-2cbf77b4ad66)</kbd>

* Select the file you want to open by clicking on it

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/4c9e54e9-8595-4120-b2bf-71ef741e48a9)</kbd>

* Wait a few seconds to view the image that will show up directly on the browser

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/80e81f20-83da-4bc7-a225-fea86b6a21c9)</kbd>
