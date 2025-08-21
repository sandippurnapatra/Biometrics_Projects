### This is the original YuNet model with weights and parameters shared in the original publication. Use Git Clone - 

https://github.com/ShiqiYu/libfacedetection.train

### Put the script - "YuNet_Original-Git.ipynb" inside a folder with the "libfacedetection" folder as subfolder

### Find the "req.txt" file or the copy of the Anaconda environment that was used to run the script - "YuNet_Original-Git.ipynb"

### Simply import the "req.txt" file into an Anaconda environment and run the script. 

### if there is any trouble with importing the environment, use the following quick install guide - 

## create env
conda create -n YuNet python=3.8.20 -y
conda activate YuNet

## PyTorch CPU (official channel)
conda install pytorch=2.3.1 torchvision=0.18.1 cpuonly -c pytorch -y

## NumPy & Pandas via conda
conda install numpy=1.24.4 pandas=2.0.3 -y

## The rest via pip
pip install opencv-python==4.12.0.88 openpyxl==3.1.5 pillow==10.4.0
# (optional ONNX)
# pip install onnx==1.17.0 onnxruntime==1.19.2

#### You do not need mmcv, mmcv-full, or mmdet for the tools/detect_image.py. YuNet inference path you’re using; those are for training/other frameworks in the repo.

### The script was run in Jupyter Notebook but can be run on other IDEs.
### If you are using Jupyter Notebook, add a kernel (optional):

conda install -y ipykernel
python -m ipykernel install --user --name retinaface_dml --display-name "retinaface_dml"

##### Now run the script "retina_face_original_Sandip.ipynb" to get the detection results
	#### replace the local directories after recreating them on your machine, and change the directories in the code
		#### The file resizes images by a scale defined in the last block "fc" variable (fc=1.0 means no scaling or down-scaling 			image). Feel free to change as required.	
			#### The detected bounding box coordinates are scaled back and drawn on the original images to check detection 					performance manually
				#### Detection coordinates and other necessary details are automatically saved as per the image file in an 						Excel/CSV file for convenience and to find "Detection" or "No Detection"

