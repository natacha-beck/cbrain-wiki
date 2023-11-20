If you have a program that can be executed on the command line, that program can be integrated into CBRAIN using Boutiques. We assume your tool takes one or more input files and produces some output file(s).

## Background

CBRAIN allows users to run pipelines on high-performance computing resources and to leverage the power of these HPC and distributed computing from a web user interface.

New scientific software is constantly being developed and updated, and the integration of those tools into the platform started to be challenging.
Initially, each tool integration required the web form and related logic to be coded directly within the CBRAIN framework in Ruby. 
Since 2015, the platform uses Boutiques to describe the command line invocation and parameters in a [JSON](https://github.com/topics/json) format. Based on the Boutiques descriptor CBRAIN will generate the user interface with a form for the pipeline parameters and will use the rules built-in Boutiques to validate them. 

Tools have been integrated via 3 different methods: 

* From 2009 to 2015: Developers integrate the tools by writing Ruby files

* From 2015 to 2020:  The 'old' Boutiques descriptor integration. The code to run the tool and to generate the UI was created at **boot** time from the descriptor. This method facilitated tool integration, however, some limitations persisted:
    * When we have multiple versions of the same tool, we were forced to create them as two different tool names.
    * There was no easy way to add logic to modify pre-processing or post-processing step of the pipeline. 

* Since 2020: The 'new' Boutiques descriptor integration. Support Code is no longer created, the behaviour of both the interface and the tool's integration is controlled by the descriptor's content.
* Now, it is easy to introduce CBRAIN-specific properties to Boutiques that enhance and adjust standard behaviour. 

## How to integrate a tool in CBRAIN with Boutiques

1. Containerize your tool, with Docker or Singularity/Apptainer.
    - For [Docker]( https://docker-curriculum.com/#dockerfile)
    - For [Singularity](https://sylabs.io/guides/3.0/user-guide/) 
    - For [Apptainer](https://apptainer.org/user-docs/master/definition_files.html#best-practices-for-build-recipes) 

2. Write a boutique descriptor for your tool. See here:
    - [Install Boutiques](https://github.com/boutiques/boutiques)
    - Write a Boutiques descriptor for your tool. Boutiques allow you to describe your tool in a JSON file.
    - See step 1 [here](https://nbviewer.org/github/boutiques/tutorial/blob/master/notebooks/boutiques-tutorial.ipynb)
    - Use the command line tool '`bosh validate`' to validate your descriptor.

3. Test your descriptor in CBRAIN with the **BoutiquesDescriptorMaker** tool. This tool is a fake interface generator that takes a descriptor and previews what a final integration would look like.

4. You can also override some methods in CBRAIN by writing special Ruby modules (For Example --> https://github.com/aces/cbrain/blob/master/BrainPortal/lib/boutiques_file_name_matcher.rb).

Additional technical information can be found [in this presentation](https://prioux.github.io/new-boutiques-presentation/#/title), which cover the programming internals of the integration framework.