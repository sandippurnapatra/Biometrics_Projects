### Follow the steps to run RetinaFace original models using MXNET in Windows 64bit

### Clone the original RetinaFace repo
git clone https://github.com/deepinsight/insightface.git

### Download RetinaFace model weights and parameters from this link:
https://github.com/deepinsight/insightface/blob/master/model_zoo/README.md
### Use RetinaFace-R50 download link available from 2.1 RetinaFace section of the readme file

### Now unzip the downloaded file and put the weights and parameters inside the cloned original repo by following the cd directory -

cd insightface\detection\retinaface

### Put your two files here:
### .\model\retinaface_r50\R50-symbol.json
### .\model\retinaface_r50\R50-0000.params

### Now create a new conda environment inside Anaconda. Use base cmd prompt:

conda create -n retinaface_dml python=3.10 -y
conda activate retinaface_dml


### Next install the following packages in the new environment

pip install --no-cache-dir ^
  "numpy==1.24.4" ^
  "protobuf==3.20.3" ^
  "onnx==1.15.0" ^
  "onnxruntime-directml==1.16.3" ^
  "insightface==0.7.3" ^
  "opencv-python==4.8.0.76" ^
  "scipy==1.10.1" ^
  pillow tqdm prettytable coloredlogs pandas

### Do a quick sanity check in the cmd of the environment to confirm the "onnx==1.15.0" package installation:

python
import onnxruntime as ort
print("providers:", ort.get_available_providers())

## You should see DmlExecutionProvider (and CPUExecutionProvider). Move on to running the script "retina_face_original_Sandip-GitV2.ipynb"

### Feel free to use req.txt file in this repo for mirroring the environment where the original RetinaFace detection was run by me or in case you get any package error running the script

### The script was run in Jupyter Notebook but can be run on other IDEs.
### If you are using Jupyter Notebook, add a kernel (optional):

conda install -y ipykernel
python -m ipykernel install --user --name retinaface_dml --display-name "retinaface_dml"

##### Run the script "retina_face_original_Sandip.ipynb" to get the detection results
	#### replace the local directories after recreating them on your machine, and change the directories in the code
		#### The file resizes images by a scale defined in the last block "fc" variable (fc=1.0 means no scaling or down-scaling image). Feel free to change as required.	
			#### If fc>1.0 then it resizes the input image as per scale but draws the scles back face bounding box coordinates on the original images.
			#### The detected bounding box coordinates are scaled back and drawn on the original images to check detection 					performance manually

				#### Detection coordinates and other necessary details are automatically saved as per the image file in an 						Excel file for convenience and to find "Detection" or "No Detection"
