CBRAIN leverage Linux container engines such as [Singularity](https://sylabs.io/singularity/) in order to encapsulate your tool.
And used [Boutiques](http://boutiques.github.io/) to integrate your tool based on the Boutiques descriptor. 

A pre-requisite to use this ability of CBRAIN is to have a Bourreau able to run Singularity, and configurate to do that. Please set the container engine of your Bourreau: 

[[/programmer-guides/images/Container_setup.png]]

To integrate your tool in CBRAIN you should have: 

* A Singularity container or a Docker container. In case of a Docker container it will be converted in a Singularity container before running your tool in CBRAIN (it is transparent to the user). 

* A Boutiques descriptor see the [getting started page of Boutiques](https://nbviewer.jupyter.org/github/boutiques/tutorial/blob/master/notebooks/boutiques-tutorial.ipynb#Publishing-your-own-tool) to get the information about how to write a Boutiques descriptor. The information about the Singularity container could be in the Boutiques descriptor like this: 

>     "container-image":{
>        "image":"image_path_on_singularity_hub",
>        "index":"shub://",
>        "type":"singularity"
>     }

<br/>

Then the Boutiques descriptor should be saved in one of the cbrain-plugins folder under the cbrain_task_descriptors as a json file. For example ` cbrain_plugins/cbrain-plugins-neuro/cbrain_task_descriptors/your_tool.json`

In order to install your tool you should run the following command on the `Brainportal` and the `Bourreau`: 

>     rake cbrain:plugins:clean:all 
>     rake cbrain:plugins:install:all 

This will allow CBRAIN to automatically generate the code for your tool. 

Once this is done please restart the Portal and the Bourreau, doing that will create a new tool configuration for your tool on the specific Bourreau. 
