
CBRAIN  offers a way to mass-extract files out of existing datasets. The tool is called SimpleFileExtractor and is installed on most supercomputers.

You use it by selecting the set of files (or rather, FileCollections) you want to extract from, then providing a list of patterns to match the files inside. The result will be a new FileCollection containing the extracted files.

### 1. Select file(s)

For example, you have many CivetOutputs and you are interested in some of the thickness and surface files. You select those CivetOuputs files and launch the SimpleFileExtractor tool.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/cb6f091c-832c-47a0-a551-b1150d12f1e5)</kbd>

### 2. Launch task 

<kbd>![simplefilelaunch](https://github.com/aces/cbrain/assets/115739667/06be6c2c-5f95-45b8-bd91-330df113a441)<kbd/>

In the task parameters, you provide the file patterns of your interest:

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/2f9a31a6-3496-4734-8111-eb6db33339c9)</kbd>

### 3. The output

All the files matching these patterns will be extracted (copied) into a new FileCollection.

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/15b4a660-7bb1-47fd-bf53-ff3bfdf99b97)</kbd>

<kbd>![image](https://github.com/aces/cbrain/assets/115739667/18a9cc2a-1c48-4fc7-ba85-3aef9c9672a6)</kbd>

### 4. Note 

In order to avoid having to copy the entirety of the original (source) files, the tool will only run if the input data is stored locally. That means that you must select a version of SimpleFileExtractor that runs on a particular server, depending on the location of your inputs. The mapping is as follows:

* Use Beluga for files stored on: Local-Beluga

* Use Cedar for files stored on: Local-Beluga

* Use Graham for files stored on: Local-Graham

* Use GrahamPlatform for files stored on: Local-GrahamPlatform

* Use Converter-1 or Converter-2 for files stored on:
  * MainStore
  * NeuroHubStore
  * SFTP-1
  * SFTP-2
  * NeuroHub-UKBB-Civet
  * CONP-VisualWorkingMemory
  * CONP-OpenPreventAD
  * CONP-OpenPreventAD-BIDS-Subjects
  * CONP-BigBrain-3DClassifiedVolumes
  * CONP-BigBrain-3DSurfaces
  * CONP-BigBrain

**Note**: you can’t run the tool on more than about 5000 input file collections. Just run it multiple times on different subsets of 5000 inputs if you have larger input sets.