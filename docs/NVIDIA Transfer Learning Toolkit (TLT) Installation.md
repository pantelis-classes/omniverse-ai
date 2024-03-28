# Installing the Pre-requisites
## 1. Install docker-ce:
### *  Set up repository:
Update apt package index and install packages.

       sudo apt-get update

![image](https://user-images.githubusercontent.com/589439/143660967-37eb6626-62c0-4afa-af3a-c43a3c172e85.png)

       sudo apt-get install \
           ca-certificates \
           curl \
           gnupg \
           lsb-release

- The following image has these dependencies already installed.

![image](https://user-images.githubusercontent.com/589439/143660985-4ae4366b-8d28-4514-b1df-bd7fe03e581d.png)

Add Docker's official GPG key:

       curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

![image](https://user-images.githubusercontent.com/589439/143661077-2d0ce142-be2f-4ab6-ad99-a685fa709182.png)

### *  Install Docker Engine:
Update the apt package index, and install the latest version of Docker Engine.

       sudo apt-get update

![image](https://user-images.githubusercontent.com/589439/143661094-a2b86161-c37f-42fd-9110-34523343f65a.png)

       sudo apt-get install docker-ce docker-ce-cli containerd.io

![image](https://user-images.githubusercontent.com/589439/143661447-8fa25b3b-1c79-470d-b962-88c21bd56f63.png)

Verify that Docker Engine is installed correctly by running the hello-world image.

       sudo docker run hello-world

![image](https://user-images.githubusercontent.com/589439/143661433-d67e18ac-c098-4665-b7ba-127e397b0df6.png)

### *  Manage Docker as a non-root user: 
Create the docker group.

       sudo groupadd docker

![image](https://user-images.githubusercontent.com/589439/143661491-c43c3f94-90d7-47d4-8bd4-dee974f67838.png)

Add your user to the docker group.

       sudo usermod -aG docker $USER

![image](https://user-images.githubusercontent.com/589439/143661478-cff5282c-e864-4821-a084-7f1f8360b4bc.png)

Log out and log back in so that your group membership is re-evaluated.

![image](https://user-images.githubusercontent.com/589439/143661541-098c52b5-0c54-46c9-9d14-fd0250f27a1e.png)

Verify that you can run docker commands without sudo.

       docker run hello-world

![image](https://user-images.githubusercontent.com/589439/143661708-6baceb75-a047-4f75-8b51-9496e6908d15.png)

 - If you get the WARNING error in the above image, run these two commands. Otherwise Skip to #2.

       sudo chown "$USER":"$USER" /home/"$USER"/.docker -R

       sudo chmod g+rwx "/home/$USER/.docker" -R

 - Run docker run hello-world to double check it works now.

       docker run hello-world

![image](https://user-images.githubusercontent.com/589439/143661749-52f2103f-19c5-47bb-85b3-0b5069957b87.png)

## 2. Install NVIDIA Container Toolkit:
Setup the stable repository and the GPG key:

       distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
          && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
          && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

![image](https://user-images.githubusercontent.com/589439/143662010-9b31cc9d-bbbe-4aa7-af69-ade75e18ccc6.png)

Install the nvidia-docker2 package (and dependencies) after updating the package listing:

       sudo apt-get update

       sudo apt-get install -y nvidia-docker2

![image](https://user-images.githubusercontent.com/589439/143662034-8e020c83-780b-40d0-a17b-ad0cdfd4210f.png)

Restart the Docker daemon to complete the installation after setting the default runtime:

       sudo systemctl restart docker

![image](https://user-images.githubusercontent.com/589439/143662068-dfcad334-8466-4c9a-9cd0-e08a23f31b66.png)

At this point, a working setup can be tested by running a base CUDA container:

       sudo docker run --rm --gpus all nvidia/cuda:11.0-base nvidia-smi

 - This should result in a console output shown below:

![image](https://user-images.githubusercontent.com/589439/143663183-0bdb6ee0-84be-4788-bdc7-0ab23e9e5d41.png)

## 3. Get an NVIDIA NGC account and API key:

 - Go to <a href="https://ngc.nvidia.com/signin">NGC</a> and click the Transfer Learning Toolkit container in the Catalog tab. This message is displayed: “Sign in to access the PULL feature of this repository”.

![image](https://user-images.githubusercontent.com/589439/143662546-8e8053f4-9aa9-40bb-bb8c-432d652db64b.png)

 - Enter your Email address and click Next, or click Create an Account.

 - Choose your organization when prompted for Organization/Team.

 - Click Sign In.

 - Once redirected to this <a href="https://catalog.ngc.nvidia.com/">page</a> with your account made, click the top right corner to click your profile and click "Setup"

![image](https://user-images.githubusercontent.com/589439/143662652-a6595488-44e6-494e-8e11-17056209a3fd.png)

 - Click Get API Key.

![image](https://user-images.githubusercontent.com/589439/143662747-cda7d160-6f1f-41dc-815f-65bf13ba7bc7.png)

 - Click Generate API Key.

![image](https://user-images.githubusercontent.com/589439/143662782-9bebeb67-26ec-4980-9624-1a91f0d1a6cc.png)

 - Your API key and username will be shown under the DOCKER tm section. Copy the text with your username and API password and save it in a file somewhere.

![image](https://user-images.githubusercontent.com/589439/143663255-907bff87-ae02-4c4d-8400-ef6a914c3aae.png)

![image](https://user-images.githubusercontent.com/589439/143663347-4ec70e43-da4d-4b97-bd26-b336586bc9d7.png)

## 4. Login to the NGC docker registry:
Use the command 

       docker login nvcr.io 
and enter the following credentials:

       a. Username: "$oauthtoken"
       b. Password: "YOUR_NGC_API_KEY"

 - Where YOUR_NGC_API_KEY corresponds to the key you generated from step 3.

![image](https://user-images.githubusercontent.com/589439/143663405-5323b62f-74a8-409f-80a8-c2c6ad961497.png)

# Installing TLT
The Transfer Learning Toolkit (TLT) is a Python pip package that is hosted on the NVIDIA PyIndex. The package uses the docker restAPI under the hood to interact with the NGC Docker registry to pull and instantiate the underlying docker containers.
## 1. Create new Python virtual environment.
### Python virtualenv setup using virtualenvwrapper  
Install via pip:

       pip3 install virtualenv

![image](https://user-images.githubusercontent.com/589439/143667101-35f5e890-f96d-4a24-8f85-4db1ff95ab8f.png)

       pip3 install virtualenvwrapper
      
![image](https://user-images.githubusercontent.com/589439/143667117-cef7ead6-5ca1-4f93-b759-4caa9c8dca76.png)
