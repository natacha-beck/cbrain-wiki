If you have a script that can be executed by the command line, any tool can be integrated into CBRAIN using Boutiques. The script will take one or more inputs and produce output(s).=

## Background

CBRAIN allows users to run pipelines on high-performance computing resources and to leverage the power of these HPC and distributed computing from a web user interface.

New scientific software is constantly being developed and updated, and the integration of those tools into the platform started to be challenging.
Initially, each tool integration required the web form and related logic to be coded directly within the CBRAIN framework. 
Since 2015, the platform uses Boutiques to describe the command line inokation and parameters in a JSON format. Based on the Boutiques descriptor CBRAIN will generate the user interface in order to select pipeline parameters and will use parameter validation built-in Boutiques to improve the user interface. 

Tools have been integrated via 3 different methods: 
* From 2009 to 2015: Developers integrate the tools by writing Ruby files
* From 2015 to 2020: Boutiques descriptor method. Code to run the tool and to generate the UI was created at **boot** time. This method facilitated tool integration, however, some limitations persisted:
    * When we have multiple versions of the same pipeline, it was integrated as two different pipelines.
    * No easy way to add logic to modify pre-processing or post-processing step of the pipeline. 

* Since 2020: Boutiques descriptor method. Code is now created at **run** time. 
         * Now, it is easy to introduce CBRAIN-specific properties to Boutiques that enhance and adjust standard behaviour. 

## How to integrate a tool in CBRAIN with Boutiques

1. Containerize your tool, with Docker or Singularity.
    - For Docker see here: https://docker-curriculum.com/#dockerfile
    - For Singularity/Apptnair see here: https://sylabs.io/guides/3.0/user-guide/, https://apptainer.org/user-docs/master/definition_files.html#best-practices-for-build-recipes (not sure if it is the better link. )

2. Write a boutique descriptor for your tool. See here:
    - Install Boutiques: https://github.com/boutiques/boutiques
    - Write a Boutiques descriptor for your tool. Boutiques allow you to describe your tool in a JSON file.
    - See step 1 here: https://nbviewer.org/github/boutiques/tutorial/blob/master/notebooks/boutiques-tutorial.ipynb
    - use bosh validate to validate your descriptor.

3. Test your descriptor in CBRAIN with the BoutiquesDescriptorMakerTool.

4. You can also overwrite some methods in CBRAIN by writing module (For Example --> https://github.com/aces/cbrain/blob/master/BrainPortal/lib/boutiques_file_name_matcher.rb).

Usefull link: (Pierre presentation)[https://prioux.github.io/new-boutiques-presentation/#/title]