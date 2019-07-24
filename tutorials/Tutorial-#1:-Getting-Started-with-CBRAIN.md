# Introduction
This tutorial is meant to give a new CBRAIN user their first experience in managing files and running a parallel task in the CBRAIN platform.

In this tutorial, you will learn how to:

1. Upload files into your CBRAIN project space.
1. View and explore files the CBRAIN platform.
1. Launch a CBRAIN task over multiple files in parallel.
1. Monitor a CBRAIN task after it is launched.
1. Retrieve results from a completed CBRAIN task.

If you need any help during the tutorial, please post in the CBRAIN Support Forum at https://forum.cbrain.mcgill.ca and someone will be there to help as soon as possible.

# Sign up for a CBRAIN account

If you haven't already done so, you can sign up for a CBRAIN account free on the McGill CBRAIN portal.  Just go to https://portal.cbrain.mcgill.ca and click on the link for "Request an Account".  Please fill out the form and once completed, you will receive a confirmation email, just to verify that it is real. Please be patient as we will need to have the account approved, so it may take a little time to process (usually within a few hours).

If you already have a CBRAIN account or once you have your account approved, please login to the CBRAIN portal.

Once you log into CBRAIN you should see be taken directly to the **Projects** page, which will list all of the current projects to which you belong.  It should look something like below:

<kbd>[[/tutorials/images/CBRAIN_Tut_1_Screen1.png]]</kbd>

# Upload files to your user project

So everyone in CBRAIN that has an account gets a **Project** that is for their own individual user.  This project can be used as your personal space and allows you to organize **Files** and **Tasks** as well as control permission for others to share your files and work.  While you can create new **Projects** for your work in the future, we will use the one that was automatically created by CBRAIN.  It should be denoted by the tile on the screen that has your user name associated with it.

Please click on your project now to enter into this **Project**.

Once you do this, you will be taken to the **Files** page, which if you just started as a new user, should have no files in it.  We will now upload some neuroimaging files so that you can get some experience using CBRAIN.

1. First, please download the following three files from Zenodo and save them on your local computer.
...  * [CBRAIN_DEMO_MINC_Image_1.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_1.mnc?download=1)
...  * [CBRAIN_DEMO_MINC_Image_2.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_2.mnc?download=1)
...  * [CBRAIN_DEMO_MINC_Image_3.mnc](https://zenodo.org/record/3348309/files/CBRAIN_DEMO_MINC_Image_3.mnc?download=1)
2. On the **Files** page click on the button at the top labelled **Upload**, shown below:

<kbd>
[[/tutorials/images/CBRAIN_Tut_1_Screen_2.png]]
</kbd>

3. Once clicked, you will be asked to locate the files you just downloaded within your computer.  Please navigate to the file **CBRAIN_DEMO_MINC_Image_1.mnc** and select it.  A popup dialog will appear for you fill in the details of where you would like to store this file in the CBRAIN ecosystem. You will be placing the file in a **DataProvider** in CBRAIN which is a construct used to define a remote filesystem.  For more information about **DataProviders**, you can read the documentation [here](https://github.com/aces/cbrain/wiki/Data-Providers). You should select the "To" location to be *MainStore*, the "Project" should be your user's project.  You can click the triangle next to *Advanced options...*, and you will see that the file has already been detected as a "Minc File", which is indeed the correct type of file. If you would like to see what other file types are supported in CBRAIN, you can click the drop down menu, but do ensure that before you upload, it is still set at "Minc File". Your screen should look something like below:

<kbd>
[[/tutorials/images/CBRAIN_Tut_1_Screen_3.png]]
</kbd>

Once finished, click the "Upload" button on the dialog and your file will begin uploading.

