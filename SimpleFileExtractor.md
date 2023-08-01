
CBRAIN now offers a new way to mass-extract files out of existing datasets. The tool is called SimpleFileExtractor and it is installed on most of the supercomputers.

You use it by selecting the set of files (or rather, FileCollections) you want to extract from, and then providing a list of patterns to match to the files inside. The result will be a new FileCollection containing the extracted files.

Here is an example.

Let say you have 20 CivetOuputs and you are interested in some of the thickness and surface files, deep in them. You select those 20 CivetOuputs and launch the SimpleFileExtractor tool. Then you provide your file patterns:

`*/thickness/*_30mm.txt`
`*/surfaces/_30mm.txt`

When you run the tool, all the files matching these patterns will be extracted (copied) into a new FileCollection.

There is one limitation you must be aware of: in order to avoid having to copy the entirety of the original (source) files, the tool will only run if the input data is stored locally. That means that you must select a version of SimpleFileExtractor that runs on a particular server, depending on the location of your inputs. The mapping is as follows:

Use Beluga for files stored on: Local-Beluga

Use Cedar for files stored on: Local-Beluga

Use Graham for files stored on: Local-Graham

Use GrahamPlatform for files stored on: Local-GrahamPlatform

Use Converter-1 or Converter-2 for files stored on:
MainStore
NeuroHubStore
SFTP-1
SFTP-2
NeuroHub-UKBB-Civet
CONP-VisualWorkingMemory
CONP-OpenPreventAD
CONP-OpenPreventAD-BIDS-Subjects
CONP-BigBrain-3DClassifiedVolumes
CONP-BigBrain-3DSurfaces
CONP-BigBrain

Because of some internal limitations in the size of operands inside CBRAIN, you can’t run the tool on more than about 5000 input file collections. Just run it multiple times on different subsets of 5000 inputs if you have larger input sets.