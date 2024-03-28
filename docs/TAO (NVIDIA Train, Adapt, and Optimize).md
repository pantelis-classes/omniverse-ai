All instructions stem from this <a href="https://docs.nvidia.com/tao/tao-toolkit/text/tao_toolkit_quick_start_guide.html">Nvidia Doc</a>.

# Requirements

### Hardware Requirements (Recommended)

    32 GB system RAM

    32 GB of GPU RAM

    8 core CPU

    1 NVIDIA GPU

    100 GB of SSD space

### Hardware Requirements (REQUIRED)

     - TAO Toolkit is supported on **A100**, **V100** and **RTX 30x0 GPUs**.

# Login to the NGC docker registry.

Login to the NGC docker registry:
Use the command 

       docker login nvcr.io 
and enter the following credentials:

       a. Username: "$oauthtoken"
       b. Password: "YOUR_NGC_API_KEY"

 - Where YOUR_NGC_API_KEY corresponds to the key you generated from step 3.

![image](https://user-images.githubusercontent.com/589439/143663405-5323b62f-74a8-409f-80a8-c2c6ad961497.png)

# Installing TAO Toolkit

 - TAO Toolkit is a Python pip package that is hosted on the NVIDIA PyIndex. The package uses the docker restAPI under the hood to interact with the NGC Docker registry to pull and instantiate the underlying docker containers. You must have an NGC account and an API key associated with your account. See the Installation Prerequisites section for details on creating an NGC account and obtaining an API key.

## 1. Create a new virtualenv using virtualenvwrapper

 - Click this <a href="https://python-guide-cn.readthedocs.io/en/latest/dev/virtualenvs.html"> link</a> to understand how virtual enviroments in python work.

 - Make sure you have virtualenv installed by checking it's version. (Instructions are in this <a href="https://github.com/pantelis-classes/omniverse-ai/wiki/NVIDIA-Transfer-Learning-Toolkit-(TLT)-Installation#1-create-new-python-virtual-environment">page</a> of the)

        virtualenv --version

![image](https://user-images.githubusercontent.com/589439/143723668-73111ae8-0ac5-4729-b89b-481d29b25d16.png)

 ## 2. Define the environment variable called VIRTUALENVWRAPPER_PYTHON.

  - Run this command to see where your python is located.

        which python3

![image](https://user-images.githubusercontent.com/589439/143723824-968874c9-5f8e-44cc-a535-d0d336a72b78.png)

  - Define the environment variable of your Python location.

        export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3

![image](https://user-images.githubusercontent.com/589439/143723906-baf552bc-e9d1-435b-8d43-553f6f0a6707.png)

 - Run this command to make sure the enviroment variable was created. (There should be red output with the variable name.)

        env | grep 'VIRTUALENVWRAPPER_PYTHON'

![image](https://user-images.githubusercontent.com/589439/143723930-c9c8658f-339d-4693-894a-daf70dea28ae.png)

 - Run this command.

        source `which virtualenvwrapper.sh`

 - Run this command to create a virtualenv named "TAO".

        mkvirtualenv TAO -p $VIRTUALENVWRAPPER_PYTHON

![image](https://user-images.githubusercontent.com/589439/143724459-afaf363f-dd92-494b-9707-5400f409d05a.png)

 - You should now see a (TAO) prepending your username in the CLI.

![image](https://user-images.githubusercontent.com/589439/143724476-77609fc2-e5a7-4773-94d9-799f2b78be6f.png)

## Intructions on how to activate/deactive the vitualenv.

 - When you are done with you session, you may deactivate your virtualenv using the deactivate command:

        deactivate

![image](https://user-images.githubusercontent.com/589439/143724159-ae6c0578-14e4-463b-8287-ef4147ff0f34.png)

 - You may re-instantiate this created virtualenv env using the workon command.

        workon TAO

![image](https://user-images.githubusercontent.com/589439/143724492-3036d310-3569-4820-9087-daca2bf9869f.png)

## 3. Download Jupyter Notebook.

 - TAO Toolkit provides samples notebooks to walk through and prescrible TAO workflow. These samples are hosted on NGC as a resource and can be downloaded from NGC by executing the command mentioned below.

 - Run these commands to set up your notebook.

        workon TAO

![image](https://user-images.githubusercontent.com/589439/143725152-cbbd609d-6d94-452c-8a48-a2bcf66dc4ab.png)

 - Copy the command belown and keep pressing enter until you are in ~/cv_samples_v1.2.0.

        wget --content-disposition https://api.ngc.nvidia.com/v2/resources/nvidia/tao/cv_samples/versions/v1.2.0/zip -O cv_samples_v1.2.0.zip
        unzip -u cv_samples_v1.2.0.zip  -d ./cv_samples_v1.2.0 && rm -rf cv_samples_v1.2.0.zip && cd ./cv_samples_v1.2.0

![image](https://user-images.githubusercontent.com/589439/143725176-02cc805c-4a98-4afe-9d49-ff17b48e171c.png)
![image](https://user-images.githubusercontent.com/589439/143725173-3c7d7cf0-c3b7-487a-9ed9-818aa5615e84.png)
![image](https://user-images.githubusercontent.com/589439/143725183-3d1caa61-125e-43fe-be67-683429c272ab.png)

## 4. Start Jupyter Notebook

 - Once the notebook samples are downloaded, you may start the notebook using the below commands:

        jupyter notebook --ip 0.0.0.0 --port 8888 --allow-root

![image](https://user-images.githubusercontent.com/589439/143725216-d67fe159-5f1f-47b1-8dbe-5c14a4e6a7aa.png)

 - Open an internet browser on localhost and navigate to the following URL:

        http://0.0.0.0:8888

![image](https://user-images.githubusercontent.com/589439/143725228-4696d70e-ec0b-485c-985b-3bffb83be6ac.png)

 - Navigate to ./detectnet_v2/detectnet_v2.ipynb

![image](https://user-images.githubusercontent.com/589439/143725266-806cf049-c46f-4e22-9940-ac4e9d952117.png)
![image](https://user-images.githubusercontent.com/589439/143725290-0778740c-3b39-45b4-8d83-a254f545844c.png)
![image](https://user-images.githubusercontent.com/589439/143725306-14110acd-9a61-460a-be5d-df45a55c5b65.png)
