
As described in the official [MICAPIPE](https://micapipe.readthedocs.io/en/latest/) page:

>Micapipe is a processing pipeline providing a robust framework to analyze multimodal MRI data. This pipeline integrates processing streams for T1-weighted, microstructure-sensitive, diffusion-weighted, and resting-state functional imaging to facilitate the development of multiscale models of neural organization. For this purpose, we leverage several specialized software packages to bring BIDS-formatted raw MRI data to fully-processed surface-based feature matrices.

You can now run MICAPIPE in CBRAIN by following the steps:

## 1. [[Create a project]]

## 2. [[Upload files]]

#### Select your input files
Please note the following prerequisites:
1. [Download an open access dataset](https://micapipe.readthedocs.io/en/latest/pages/04.start2end/index.html#download-an-open-access-dataset)
2. Converting to BIDS
3. BIDS format validation 

    *   Any new dataset has to be BIDS-compliant (see specifications at http://bids-specification.readthedocs.io/) and should be validated with tools provided by BIDS, such as the BIDS-validator available in CBRAIN.

Full information can be found here [HERE](https://micapipe.readthedocs.io/en/latest/pages/04.start2end/index.html#download-an-open-access-dataset)

Once your file(s) is uploaded, please select from the Files list:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/35d5d49a-d86b-4fef-8ed4-7fdc8a10a000)</kbd>

## 3. [[Launch Task]]

Process the Launch Task steps and select MICAPIPE tool:
 
<kbd>![image](https://github.com/aces/cbrain/assets/115739667/86999c34-0fde-4117-bc56-66d2bafe0512)</kbd>

## 4. Task parameters

Set up the task parameters according to your analysis

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/708f77b3-8489-4a44-a84f-86dcaec8c155)</kbd>

Please make sure to select all the required processing flags (proc_structural, proc_surfs, T1w string identifier, proc_dwi..) based on your expected results.

## 5. Output (Derivatives)

All the outputs are BIDS conform and stored under their correspondent directory (e.g. anat, func dwi..). 

You can navigate in the tree directory by expanding each folder and visualize files without the need to download them by simply clicking on the link.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/22328b43-a529-4b79-87eb-b884529a9b20)</kbd>

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/85051f8f-ba0f-4df2-8b16-56358852bb8c)</kbd>

MICAPIPE includes an integrated module for [Quality Control](https://micapipe.readthedocs.io/en/latest/pages/02.qc/index.html) of the outputs:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/b88ab8fa-d1ca-4754-a516-dd242c2dbf23)</kbd>

You can find more information about the MICAPIPE tool by visiting their [page](https://micapipe.readthedocs.io/en/latest/).





