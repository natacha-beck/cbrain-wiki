ExploreASL is a pipeline and toolbox for image processing and statistics of arterial spin labeling perfusion MR images. 
It is designed as a multi-OS, open source, collaborative framework that facilitates cross-pollination between image processing method developers and clinical investigators.

The pipeline allows minimum manual intervention and increases the reproducibility of studies.
More information can be found [HERE](https://exploreasl.github.io/Documentation/1.9.0/).

To run your analysis in CBRAIN, please follow the steps: 

## 1. [[Create a project]]

## 2. [[Upload files]]

#### Select your input file(s)

Please note the following prerequisites:
1. Input format: **BIDS dataset**. 
More information about the BIDS data requirements can be found [HERE](https://sites.google.com/view/exploreasl/tutorials/how-to-start-exploreasl)

Once your file(s) is uploaded, please select from the Files list:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/970b7768-7d05-41b3-adee-3d09dfd9a159)</kbd>

## 3. [[Launch Task]]

Process the Launch Task steps and select ExploreASL tool:
 
<kbd>![image](https://github.com/aces/cbrain/assets/115739667/0c634375-9843-4c70-97cd-fb9de0cb3f4e)</kbd>

## 4. Task parameters

* Select where you want to _Save results to_ and to which _Project_
* Set up the task parameters according to your analysis.

Note: 
* You will have to select an input folder. 

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/832009be-b4b5-4008-90be-0a605e80b0fb)</kbd>

* Study parameters are available: you can specify sessions name, sessions options but when the subject datais in BIDS format, you don't need them.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/df39bffe-5a28-4a67-8847-9d0c2d286f10)</kbd>

## 5. Output 

All the outputs are BIDS conform and stored under their correspondent directory (e.g. anat, func dwi..). 

You can navigate in the tree directory by expanding each folder and visualize files without the need to download them by simply clicking on the link. Once the image is loaded, you will be able to change the settings like the color map or the threshold for example.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/4dfa5f29-df19-463a-9da8-02b10e5a4934)</kbd>

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/5aa0e58d-d758-47cd-a0c2-57b0fb587116)</kbd>

## WARMING NOTE:

The status of your task might be COMPLETED, however you might not have any results. It usually due to the input file. If you have any issue please don't hesitate to contact us at support@neurohub.ca .



