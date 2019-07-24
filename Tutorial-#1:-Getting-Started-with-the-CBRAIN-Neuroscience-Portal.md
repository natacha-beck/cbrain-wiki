# Introduction
This tutorial is meant to give a new CBRAIN Portal user a first experience in managing files and running a parallel task in the McGill hosted CBRAIN Neuroscience Portal (https://portal.cbrain.mcgill.ca).

In this tutorial, you will learn how to:

1. Upload files into your CBRAIN project space.
1. View and explore files the CBRAIN platform.
1. Launch a CBRAIN task over multiple files in parallel.
1. Monitor a CBRAIN task after it is launched.
1. Retrieve results from a completed CBRAIN task.

If you need any help during the tutorial, please post in the CBRAIN Support Forum at https://forum.cbrain.mcgill.ca and someone will be there to help as soon as possible.

# Sign up for a CBRAIN Portal account

If you haven't already done so, you can sign up for a CBRAIN account free on the McGill CBRAIN Neuroscience portal. Just go to https://portal.cbrain.mcgill.ca and click on the link for "Request an Account".  Please fill out the form and once completed, you will receive a confirmation email, just to verify that it is real. Please be patient as we will need to have the account approved, so it may take a little time to process (usually within a few hours).

If you already have a CBRAIN account or once you have your account approved, please login to the CBRAIN portal.

Once you log into the CBRAIN Portal, you should see be taken directly to the **Projects** page, which will list all of the current projects to which you belong. It should look something like below:

<kbd>[[/tutorials/images/CBRAIN_Tut_1_Screen1.png]]</kbd>

# Upload files to your user project

So everyone in CBRAIN that has an account gets a **Project** that is for their own individual user.  This project can be used as your personal space and allows you to organize **Files** and **Tasks** as well as control permission for others to share your files and work.  While you can create new **Projects** for your work in the future, we will use the one that was automatically created by CBRAIN.  It should be denoted by the tile on the screen that has your user name associated with it.

Please click on your project now to enter into this **Project**.

Once you do this, you will be taken to the **Files** page, which if you just started as a new user, should have no files in it.  We will now upload some neuroimaging files so that you can get some experience using CBRAIN.

1. First, please download the following three files from Zenodo and save them on your local computer.
   * [CBRAIN_DEMO_MINC_Image_1.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_1.mnc?download=1)
   * [CBRAIN_DEMO_MINC_Image_2.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_2.mnc?download=1)
   * [CBRAIN_DEMO_MINC_Image_3.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_3.mnc?download=1)
2. On the **Files** page click on the button at the top labelled **Upload**, shown below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_2.png]]
   </kbd>

3. Once clicked, you will be asked to locate the files you just downloaded within your computer.  Please navigate to the file **CBRAIN_DEMO_MINC_Image_1.mnc** and select it.  A popup dialog will appear for you fill in the details of where you would like to store this file in the CBRAIN ecosystem. You will be placing the file in a **DataProvider** in CBRAIN which is a construct used to define a remote filesystem.  For more information about **DataProviders**, you can read the documentation [here](https://github.com/aces/cbrain/wiki/Data-Providers). You should select the "To" location to be *MainStore*, the "Project" should be your user's project.  You can click the triangle next to *Advanced options...*, and you will see that the file has already been detected as a "Minc File", which is indeed the correct type of file. If you would like to see what other file types are supported in CBRAIN, you can click the drop down menu, but do ensure that before you upload, it is still set at "Minc File". Your screen should look something like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_3.png]]
   </kbd>

   Once finished, click the "Upload" button on the dialog and your file will begin uploading. Once this is done, you should see the file appear in your list of files like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_4.png]]
   </kbd>

4. Repeat steps 2 and 3 for the other two image files.  Once done, all three of the files should appear in your list of files like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_5.png]]
   </kbd>

5. Let's take a look at one of the files so that we can see what is in there.  The MINC file is a common neuroimaging format used in MRI imaging. It contains the information needed to view a 3-D image of the brain.  Click on the name of the file "CBRAIN_DEMO_MINC_Image_1.mnc" in the file list, and a new screen will appear that will provide you the information about the file at the top, and a visualization of the data in the file using "BrainBrowser" embedded below that, such as below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_6.png]]
   </kbd>

   Feel free to interact with the data through the visualization, you can move through and see different areas of the brain by dragging the red crosshairs around in each axis, change the color map to highlight areas, and get a picture of all of the slices in any of the directions.  Don't worry, you are not altering the file, just exploring it, so you can feel free to play with it to see all of the options.  When you are finished, you can click "Files" tab a the top of the screen to return to the *Files** page.

# Launch some task on CBRAIN

In this part of the tutorial, you will learn how to launch a computational task in parallel for the three files that you just uploaded. One of the powerful features of CBRAIN is that you can define very large sets of computations that need to be performed, and the platform will take care of all of the data movement, job submission, and results gathering for you, greatly simplifying the process. We will use the example task of converting these three files that are in the MINC format to NIfTI another widely used neuroimaging format.

1. We will begin by clicking all the check boxes on the left side of each of the file entries in your **Files** list, as below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_7.png]]
   </kbd>

2. Click on the "Launch" button in the upper left, below the **Files** tab.  This will launch a dialog box that will allow you now to pick the **Tool** that will be used to create our tasks. This dialog allows you to explore all of the tools available to you. We will want to find the tool "Mnc2nii". You can explore all of the available tools and narrow them down using the categories on the left side of the dialog if you would like to see what is avaiable.  To fine our tool, type "Mnc2nii" in the "Search:" box at the top, and you should see something like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_8.png]]
   </kbd>

3. Click on the "Mnc2nii" entry in the "Tools:" box.  Doing so will transform the box to adding a dropdown menu for "Server & Version", where you can select the resource within the CBRAIN ecosystem to run your tasks. If click on the dropdown, you will see a list of where this tool has been deployed along with the versions that have been deployed on each server.  Let's choose "Converter-1 > 2.1.0" from this dropdown.  Once that is done, you will see 2.1.0 show up on the dropdown box and an estimate of the time it potentially take to start your tasks.  Note, CBRAIN utilizes a number of remote computing resources, and many of them are used by 100s of users at a given time, so there may be a wait time associated with your selection.  Once you have completed this, your screen should look something similar to below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_9.png]]
   </kbd>

4. Click the "Launch Mnc2nii" button.  This will then take you to a page that will allow you to set input options for the selected **Tool**. You will see the following sections:
   * **Task Control** - This contains parameters that are used to contol the running of the tool. You can select, for instance, where you would like results from your run to be stored.  By default, this is set to the "Data provider of input files", which in our case is "MainStore", but you are able to save them anywhere in the ecosystem that you have access.  You can also set the project to run the job in, which in our case is our user's project.  Finally, you can add a brief description of the job, so that you can add notes particular to the task you are running for future reference.
   *  **Preset Management** - By default this section is hidden, and allows you to have preset configurations stored and recalled for future reference.  This is an advanced feature and we will not be using it in this tutorial.
   *  **Task Parameters** - Finally, this is the section of the page that will allow you to set the input parameters for your task.  This section will change depending on the tool that you run. Fortunately, Mnc2nii has very few parameters that need to be set, but some of the tools will have a large number of options that you can set to get the desired analysis.

5. Let's set the parameters for our tasks. This will set the inputs for all three conversions that we will be doing.
   * Set the "Output voxel data type:" to "'default': let the program choose!"
   * Set the "For **integer** voxel data types, use" to "let the program choose!"
   * Ensure that the "Output file format:" is "nii", which will produce NIfTI files.
   Your screen should look like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_10.png]]
   </kbd>

6. Click the "Start Mnc2Nii" button at the bottom of the page.  This will take you to the **Tasks** list, where you can see all of the tasks that you have started, are currently running, or have completed in the past.  You should see an entry in the list for Mnc2nii, with the "Current Status" of "3xNew".  There is "+" sign at the beginning of the entry, and if you click on that, it will expand and you will see that there have been three tasks created on "Converter-1", one for each of the files we asked for.  CBRAIN has now told the remote machine to run the Mnc2nii tool on each of these files with the input parameters we provided.  It should look like below:

   <kbd>
   [[/tutorials/images/CBRAIN_Tut_1_Screen_11.png]]
   </kbd>

7. Click on the name of the first task.  This will bring you to a page where you can see the details of the task that you have submitted.  On there you will the sections:
   * A series of buttons at the top give you the ability to perform different operations on the task, such as restarting the task if it fails at various stages, archiving the task, or deleting the task.  These will not be necessary for this tutorial.
   * "Info:" - This section shows you all of the details such as where the job was submitted to, who is running the job, when it was submittted, and the size of the directory.
   * "Parameters:" - This section is a summary of the input files, input parameters, and the output files to be created.  As you can see, the Outputs have automatically been set to a file name that is the same at the input, but instead with an extension of ".nii".  These are active links so you can get the information about these files from here as well as the **Files** page.  The "Raw" tab will provide you the list of parameters that were used to run the task.
   * "Processing Log:" - This is a log of the activities that CBRAIN performed to run your task.  It is not necessary to understand all of the items in this file, but it is very helpful when something goes wrong or you want to see what are the stages and processes being performed by CBRAIN.
   * "Cluster Job's Captured Output" - This section contains the "Standard Out" and "Standard Error" from the running task.  These are the same as if you ran the tool in a command line and represent the interactive outputs to the task.  They are very helpful to see what the task is doing once it starts running and if there are any errors that occured.

  The screen should look something like below:

  <kbd>
    [[/tutorials/images/CBRAIN_Tut_1_Screen_11.png]]
  </kbd>

  Click the **Tasks** tab at the top to be taken back to the **Tasks** list.

7. Reload the page, as the tasks run, the "Current Status" will move through the various stages of a CBRAIN execution as they execute on the remote machine.  Reloading the page will update the status, until eventually, all 3 tasks will be in the "Completed" state.  This means that your tasks have successfully finished and the outputs have been stored back in the "MainStore" **DataProvider**.

8. Now that the tasks have all completed (should not take more than a few minutes, depending on how many people are using "Converter-1" at the time you are performing the tutorial), lets click on the **Files** tab to be taken back to the **Files** list page. You should now see three new files have appeared there, each corresponding to the newly created NIfTI file.  They have been properly identified as a NIfTI file.  If you click on the name of any of them, you will be able to see the result file in "BrainBrowser", just like you did for the MINC files earlier.

This concludes the tutorial.
