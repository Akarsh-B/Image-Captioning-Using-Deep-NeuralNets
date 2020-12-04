# Image Captioning using Deep Neural Networks

# Hardware Requirements

	1. Workstation with 64GB RAM and above
	2. GPU with atleast 2-4GB capability for faster processing
	3. Google Cloud Platform or Amazon AWS cloud services are preferred

# Download the data

The data used for the project is very large and cannot be uploaded to BlackBoard due to size restrictions.

Please download the two files provided below and extract only the images file

	1. https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip - Flick8k Images Dataset (~1.2GB)
		(wget https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip)
		Please extract this folder to the Image Features dicrectory where the Image_Features.ipynb notebook is stored.

	2. https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip - Flickr8k Image Captions Dataset (~ 2 MB)
		(wget https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip)
		Do not extract the file. Place this file in the directory alongside the notebook file Image_Captioning.ipynb.

# Instructions to run the notebooks

	1. Make sure Python 3.5+ version is installed in the system

	2. Install pip to download all necessary packages

	3. Command to install pip : 
		a) curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py 
		b) python3 get-pip.py

	4. All the packages needed to execute the programs are placed in the requirements.txt file
		a. Command to install packages: pip install requirements.txt

	5. Image_Features.ipynb
		a. Make sure the Flickr8k Images Dataset is downloaded and extracted and is available in the current working directory
		b. Run the notebook
		c. The execution time of the notebook depends on the hardware used. On a general machine with 6-8GB ram and integrated GPU. It would take around 9-10hrs to complete. On a machine with GPU it will generally take 2-3hrs. Google Cloud Platform or Amazon AWS services are preferred
		d. Once the notebook is executed, the image features from different imageNet models are dumped into its respective pickle files. The pickle files are stored in the image_features folder

	6. Image_Captioning.ipynb
		a. Make sure the Flicker8k Image Captions dataset is downloaded and is available in the current working directory
		b. Run the notebook
		c. Since all the image features are processed without progressive loading, a normal workstation will not support the execution. Please use a system with 32-64GB RAM. Google Cloud Platform offers virtual machines with 128GB RAM and 6 vCPU's, which can be used to speed up execution
		d. The text data is pre-processed and image features are read from pickle files. Models are run with different image features that are extracted. Each model runs for 5 epochs with 30-40 mins per epoch. The entire notebook takes around 9-10hours to complete the training
		e. Once the model is trained, the best model will be saved in the model_results/{model} directory.
		f. This model is loaded again to predict captions for the test images and evaluate the performance.
		Note: At every run the final best model varies, BLEU scores for each model have to be evaluated and the best model has to be loaded manually

# Credits

	1. jbrownlee - For making the Dataset open-source and available to general public

