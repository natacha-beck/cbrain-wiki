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

1. Containerize your tool, with Docker or Apptainer, formerly known as Singularity.
    - For [Docker]( https://docker-curriculum.com/#dockerfile)
    - For [Apptainer](https://apptainer.org/user-docs/master/definition_files.html#best-practices-for-build-recipes) 

2. Write a boutique descriptor for your tool. See here:
    - [Install Boutiques](https://github.com/boutiques/boutiques)
    - Write a Boutiques descriptor for your tool. Boutiques allow you to describe your tool in a JSON file.
    - See step 1 [here](https://nbviewer.org/github/boutiques/tutorial/blob/master/notebooks/boutiques-tutorial.ipynb)
    - Use the command line tool '`bosh validate`' to validate your descriptor.

3. Test your descriptor in CBRAIN with the **BoutiquesDescriptorMaker** tool. This tool is a fake interface generator that takes a descriptor and previews what a final integration would look like.

4. You can also override some methods in CBRAIN by writing special Ruby modules (For Example --> https://github.com/aces/cbrain/blob/master/BrainPortal/lib/boutiques_file_name_matcher.rb).

Additional technical information can be found [in this presentation](https://prioux.github.io/new-boutiques-presentation/#/title), which cover the programming internals of the integration framework.

## Recommendations for tool containerization for integration with CBRAIN

For smooth integration with CBRAIN, a scientific tool needs to be containerized. When building a container, we recommend following a few best practices.

**1.  CBRAIN is for command line tools.**
Before you start working on containers make sure the scientific tool (the tool) is Linux shell friendly, has a command line interface, can be used on a system without a graphical interface, and is not just a software library or a loose collection of scripts. If this is not the case, create a wrapper script which allows your tool to be used as a command line utility. Python is a good choice of programming language to write such a wrapper script, thanks to an excellent standard argument parsing module. If your scientific tool contains more than one set of actions and is rather a pipeline containing multiple steps of individual selectable actions, that is then a set of tools.  In such a case, consider first selecting and integrating only the most useful pipelines or use cases rather than every possible tool with the range of possible ones to containerize.


If you are creating a new tool, avoid calling your tool simply ‘the tool’, ‘toolkit’  or even the ‘xxxx tool’. If time allows, you can learn more about unix Command Line Interface philosophy at [Command Line Interface Guidelines](https://clig.dev/) or [The Poetics of CLI Command Names](https://smallstep.com/blog/the-poetics-of-cli-command-names/). 


Usually if a tool works on the command line of a Unix-like system, there is a good chance that it is Linux compatible.


**2. Use GitHub to create, store, manage and share your code.**
Place the code for your tool, the Boutiques descriptor, the instructions of how to build the container and the container itself, in a GitHub repository or a similar code management system to streamline versioning and code review.


Ideally, keep the Boutiques descriptor in a repository separate from the tool code or the container, setting your repository permissions so as to be open to the public or at least accessible to the CBRAIN development team.  By keeping the Boutiques descriptor in a separate repository, it reduces the amount of disk space required by CBRAIN on each of the connected HPC resources where the tool will be available to be run.


**3. File Permissions within the container.**
Make sure that within the container, the tool file permissions allow for unprivileged user access.  For example, if your tool script is brain_map.py, then set the permissions using chmod a+rx brain_map.py.  HPC clusters, such as those of the Alliance, do not give users root access.  Therefore CBRAIN needs to be able to run your tool as an unprivileged user. 






**4. Do not make assumptions about the work directory.**
Make sure that your tool can be launched from any directory location on the system where the tool is to be run. Each time a tool is run, CBRAIN creates and mounts a new work directory to contain your input data and output files generated by the tool.


**5. Use /tmp or, if you have to, the work directory for intermediate data.**
Make sure the tool writes intermediate (temporary) data only either to /tmp or the work directory. It is recommended to delete all intermediate data from the work directory once the computation has completed.  You can delete the intermediate data by adding appropriate commands to the Boutiques descriptor or as a wrapper script within the tool container.
 
**6. Path support.**
Make sure your tool can work with absolute and relative paths for input and output files. 


**7. No internet. Make sure that running the tool does not require access to the internet.**
Disable auto-updates, reporting, and downloading of additional modules or data. For instance, if a tool requires access to brain atlases, then download them separately and place them into a directory separate from the container.  Within CBRAIN, a collection of TemplateFlow atlases are stored, and can be configured to be accessed by your container.  Please contact us for additional information about this option.


**8. Test and validate.**
Unless you are using advanced features of the Boutiques descriptor integration in CBRAIN, test your container and Boutiques descriptor on a physical or virtual machine where you can install the Boutiques bosh utility. To do so you may need to install the Docker and Apptainer utilities as well.  If running the tool with bosh is not possible, at least use bosh to simulate the command line invocation of the tool. 


**9. Share your test data and the results of the test.**
In order to help CBRAIN make efficient use of resources, please do not place large amounts of data (over 100 MB, for example) into the container.  Also, large amounts of data should not be stored in GitHub since it has difficulties with very large files.  As an alternative, consider storing test data in a designated storage location such as within CBRAIN via sftp upload, or using a file sharing service such as S3 or Google Drive, for example.


**10. Use DockerHub.**
Within CBRAIN, most of the tools are containerized with Docker and submitted to [DockerHub](https://hub.docker.com/), with CBRAIN executing them with Apptainer.  It is recommended to containerize your tool first using Docker and then converting it to the APptainer sif format, but directly building the container in Apptainer is possible. You can learn about Docker from the official [Docker Getting Started Guide](https://docs.docker.com/get-started/), or alternatively through various video tutorials available on [YouTube](https://youtu.be/zJ6WbK9zFpI?si=7J5ISbtaGf4ZaTJW).  Topics such as tagging, bind mounts, volumes, base images and layered containerization are particularly relevant when looking to learn about containerizing a tool for integration in CBRAIN.


**11. Use DockerHub tags to codify the tool version and stability.**
For example, 1.0.0-alpha, 1.0.1-dev.  Do not rely on the latest tag only.  Consistent tagging increases clarity and traceability, and simplifies troubleshooting.


**12. Follow the Apptainer best practices for compatibility when creating a Dockerfile.**
While Apptainer aims to fully support Docker, there are a few differences to take into consideration.  Therefore, following some [best practices](https://apptainer.org/docs/user/main/docker_and_oci.html#best-practices-for-docker-apptainer-compatibility) is recommended.


**13. For MATLAB-based tools.**
Often MATLAB-based tools, especially earlier versions, require compilation so as to avoid run-time license connection issues, and to also properly work with the command line interface.  See our [recommendations](https://docs.google.com/document/d/1ziBeVfbnA_QuDyqus_ZfkYDKqKstJxNU_p69csfVexg/edit#heading=h.ltp1n4elo5zf) regarding the integration of MATLAB tools into CBRAIN for specific examples.