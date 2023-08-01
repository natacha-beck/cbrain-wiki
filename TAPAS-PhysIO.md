This page will walk you through the process of running TAPAS PhysIO in CBRAIN but first, let's give some background of the Physio tool.

## What is Physio 

Quote From the [PhysIO github page:](https://github.com/translationalneuromodeling/tapas/blob/master/PhysIO/README.md)

> The PhysIO Toolbox provides physiological noise correction for fMRI-data from peripheral measures (ECG/pulse oximetry, breathing belt). It is model-based, i.e. creates nuisance regressors from the physiological monitoring that can enter a General Linear Model (GLM) analysis, e.g. SPM8/12. Furthermore, for scanner vendor logfiles (PHILIPS, GE, Siemens), it provides means to statistically assess peripheral data (e.g. heart rate variability) and recover imperfect measures (e.g. distorted R-peaks of the ECG).

TAPAS PhysIO has two use cases: a BIDS single subject as input (bids_directory), or the individual BOLD and physlog files (manual_input).

# Case 1: BIDS directory
This is currently only supported for Philips and BIDS format physlog files and there are no plans to expand to other file formats. It is recommended to convert your physlog data to BIDS format (.tsv) when organizing your data into a BIDS directory.

## File Requirements and launch of the task
* A single file collection, either a single BIDS subject or a BIDS dataset.
* Select your BIDS single subject directory or dataset  
* Select TAPAS_PhysIO tool 
* Launch the task

## Task Parameters
*  For that use case: bids_directory.
* FMRI Input: select your BIDS directory.

**Note**: In order to be launched, the tool requires two types of files, the fMRI BOLD images and files containing physiological recordings from ECG or PPU devices for example. If the input file does not meet the requirement, the task will fail.

<kbd>![image](https://user-images.githubusercontent.com/115739667/236021518-dbc5e60e-5e4e-4461-8a86-99d35a718441.png)</kbd>

## Log file parameters
* Set **Logfile vendor** to "Philips" or "BIDS" depending on the format of your physlog data (.txt or .log for Philips, .tsv for BIDS).
* Leave **Cardiac logfile, Respiration logfile, and Cardiac and Respiratory logfile** blank. These will be read automatically from the input directory, assuming that the naming scheme is consistent and BIDS-valid for BOLD files and physlog files.
* For the rest, set the desired parameters.

## Output
The output of BIDS directory processing will have a BIDS-valid derivatives structure. The output data will be nested under derivatives/PhysIO and will have the same directory structure as the input collection.

The [model]_corrected.nii.gz images will be in the place of the rawdata images, and additional PhysIO outputs and diagnostic information will be placed inside subdirectories.

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/608b977e-97d5-4697-af7c-07ab410bd952)</kbd>

#### Visualization enable directly from the web browser

<kbd>![image](https://github.com/xmpham/CBRAIN_USERGUIDE_PXM/assets/115739667/b38b0326-0b84-4815-84ec-7178d9d23745)</kbd>

# Case 2: Manual input
This case is similar to the native MATLAB version of PhysIO. The user must separately input an fMRI run and a physlogfile to be analyzed.

## Requirements
* An fMRI run in NIfTI format.
* A physiological logfile containing cardiac and/or respiratory data.
Select your fMRI file and physlogfile and launch TAPAS_PhysIO.

## Task Parameters
* Use Case: Select manual_input.
* FMRI Input: Select your fMRI file in .nii or .nii.gz format.

## Log file parameters
* Set Logfile vendor to the appropriate physlogfile vendor format.
* If your physlogfile contains cardiac data only, select it for Cardiac Logfile. If it is respiratory data only, select it for Respiration Logfile. OR, if it contains both, select it for Cardiac and Respiratory File.

## Output
The PhysIO output will be placed in a single file collection in your project.