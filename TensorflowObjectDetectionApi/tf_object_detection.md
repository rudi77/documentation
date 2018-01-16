# Installation of Tensorflow's Object Detection API

Here, I describe how Tensorflow's object detection API can be installed on a windows machine.

- Install all the prerequisites which are described [here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md).
- Download protoc for windows from https://github.com/google/protobuf/releases and add it to our PATH:
- Clone the repo: https://github.com/tensorflow/models.git
- Open a powershell and execute the following command:

	```cd .\Source\Tensorflow\models\research\```
 
	```Get-ChildItem object_detection/protos -Filter *.proto |Foreach-Object { protoc.exe ($_ | Resolve-Path -Relative) --python_out=.}```

	 ``` $env:PYTHONPATH="$env:PYTHONPATH;$pwd;$pwd\slim"``` This adds the current folder as well as the \slim folder to your PYTHONPATH but only for the currenlty opened powershell. If you want to add theses folders permanently to the PYTHONPATH then you have to add them your System Variables.

	Now you can test that you have correctly installed the Tensorflow Object Detction API:

	```python object_detection/builders/model_builder_test.py```
		