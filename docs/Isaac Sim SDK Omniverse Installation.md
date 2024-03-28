## Prerequisites
 
Ubuntu 18.04 LTS required 

Nvidia drivers 470 or higher

### Installing Nvidia Drivers on Ubuntu 18.04 LTS

       sudo apt-add-repository -r ppa:graphics-drivers/ppa

![image](https://user-images.githubusercontent.com/589439/143662835-6d5624b2-b78d-4ff2-acc3-efadc64d58a2.png)

       sudo apt update

![image](https://user-images.githubusercontent.com/589439/143662852-f99e89cc-1c28-4039-8c25-95c470de171f.png)

       sudo apt remove nvidia*

![image](https://user-images.githubusercontent.com/589439/143662863-5dbc78c5-c175-495e-bd36-5b214557774c.png)

![image](https://user-images.githubusercontent.com/589439/143662877-cd6abe58-973f-4da1-ac1c-9fe5d28a5853.png)

       sudo apt autoremove

![image](https://user-images.githubusercontent.com/589439/143662895-53e3155b-e8bf-498b-9bb3-4cbe39e1354a.png)

![image](https://user-images.githubusercontent.com/589439/143662915-70024577-3531-46da-8f6e-ea2d8d230e8a.png)

       sudo ubuntu-drivers autoinstall

![image](https://user-images.githubusercontent.com/589439/143662959-6b21b9f4-5462-4b9d-9a29-083fad49eafe.png)

       sudo apt install nvidia-driver-470

![image](https://user-images.githubusercontent.com/589439/143662965-5e05ee0d-a48f-4161-a086-ab03bf6854bf.png)

 - Restart your PC.

 - Run nvidia-smi to make sure you are on the latest nvidia drivers for Isaac.

       nvidia-smi

![image](https://user-images.githubusercontent.com/589439/143663079-a9503fd4-75f1-4bb0-bfd8-ada3bd9fa2ec.png)

## Omniverse and Isaac Sim installation (executable)

### 1. Create nvidia developer account. This is required to access some of the downloads as well as obtaining API keys for Nvidia NGC

 - Go to this <a href="https://developer.nvidia.com/developer-program">link</a> and create an account.

![image](https://user-images.githubusercontent.com/589439/143655734-92f93f94-723b-4a03-aee3-9004ebdfa931.png)

 - Fill out your NVIDIA profile.

![image](https://user-images.githubusercontent.com/589439/143655803-423dddd8-398e-49e0-839f-d96a5e655441.png)

### 2. Go to this <a href="https://www.nvidia.com/en-us/omniverse/">omniverse link</a> and download Omniverse and install.

![image](https://user-images.githubusercontent.com/589439/143158851-a4f7a00b-4f25-40e0-ae2e-2fba3edef08e.png)

 - Fill out the form.

![image](https://user-images.githubusercontent.com/589439/143158880-17506781-abc2-4188-aca3-4546dcb475f9.png)

 - Click the download link for Linux.

![image](https://user-images.githubusercontent.com/589439/143158912-97fb24ad-8b49-432e-a3d7-4badb0977714.png)

 - Download and save the AppImage file to your ~/Downloads folder.

![image](https://user-images.githubusercontent.com/589439/143158967-afad1831-822f-4440-9a4b-9248c909007d.png)

 - Run these commands to execute the AppImage.

       cd ~/Downloads

       ls      

       chmod +x omniverse-launcher-linux.AppImage

       ./omniverse-launcher-linux.AppImage

![image](https://user-images.githubusercontent.com/589439/143656306-85f1aefd-a6a8-4f07-a2e9-b7153ff175ce.png)

       
### 3. Login to Omniverse to install Isaac Sim 2021.

 - Login with your NVIDIA credentials.

![image](https://user-images.githubusercontent.com/589439/143160948-90380e23-e8cc-42b3-8933-4d88c5c9bc90.png)

 - Accept the terms of agreement.

![image](https://user-images.githubusercontent.com/589439/143161008-59913f3c-cfde-4c9f-93d4-609dc0346469.png)

 - Click continue. (default paths)

![image](https://user-images.githubusercontent.com/589439/143161046-21afc550-6bf7-450c-b023-3296de59d7b4.png)

 - Install cache.

![image](https://user-images.githubusercontent.com/589439/143161192-9936a489-e81d-4ccc-a2e0-caf120ce92c4.png)

### 4. Installing Isaac through Omniverse.

 - Click the Exchange tab in Omniverse.

![image](https://user-images.githubusercontent.com/589439/143165080-9daa5e96-99c0-4e60-9a40-ff4f77944311.png)

 - Search for Isaac and Click Isaac Sim.

![image](https://user-images.githubusercontent.com/589439/143165387-659a75bf-ba62-49e4-9bab-320b0da9eeb1.png)

 - Click install.

![image](https://user-images.githubusercontent.com/589439/143165778-75f9cbea-b93b-4c0a-9661-269ec0e643f5.png)

### 5. Go to the nucleus tab and create a nucleus local server to run the Omniverse Isaac Sim Samples.

 - Create your local nucleus account by clicking the Nucleus tab in Omniverse.

 - Click Add Local Nucleus Service.

![image](https://user-images.githubusercontent.com/589439/143163402-c38ef3e5-64a8-437f-8a4c-7f978b37e40b.png)

 - Click Next. (Default Path)

![image](https://user-images.githubusercontent.com/589439/143163446-5fa6c2bc-6437-4239-bcd7-5be8f9159de7.png)

 - Create Administrator Account.

 - Go to this <a href="https://developer.nvidia.com/nvidia-isaac-sim-assets-20211">link</a> and download the Isaac Sim Assets.

![image](https://user-images.githubusercontent.com/589439/143163494-95fba91c-12b3-4228-ae21-39ce639d66b4.png)

 - Unzip the by going to your downloads folder and right clicking isaac-sim-assets-2021.1.1.zip and choosing "extract here".

![image](https://user-images.githubusercontent.com/589439/143657912-d33c71f8-1965-4ca2-b06c-3d0790ffd1e4.png)

 - Log into the Nucleus Service with the credentials you created.

![image](https://user-images.githubusercontent.com/589439/143163725-d7b1a5ae-2391-4da0-9a70-f58ce063eb38.png)

 - Create an Isaac Folder. (Right click localhost)

![image](https://user-images.githubusercontent.com/589439/143164075-7cfacb0b-a2e2-4e29-a63f-85316f585a5e.png)

![image](https://user-images.githubusercontent.com/589439/143164125-851ba73c-0cc8-4555-b5d8-769d54625d8d.png)

![image](https://user-images.githubusercontent.com/589439/143657335-7499d95b-d4e0-44bd-88f9-87f4d73a9de9.png)

 - Drag and drop the the files in the isaac-sim-assets-2021.1.1. folder into the Isaac folder in Omniverse. (NOT THE .ZIP; THE FILES IN THE FOLDER THAT WAS CREATED WHEN YOU EXTRACTED IT).

![image](https://user-images.githubusercontent.com/589439/143666284-5ff41514-5c89-4cc7-afa0-b17ed9003b61.png)

 - Click upload.

![image](https://user-images.githubusercontent.com/589439/143657451-f9792fd1-e085-4850-a5b5-1ccbe9d4d4e5.png)

![image](https://user-images.githubusercontent.com/589439/143666323-eb172e58-d0cb-4228-af31-f9f7daf43d19.png)

### 6. Now launch Isaac Sim from the Library Omniverse tab within Omniverse.

 - Click Launch in the Library Tab of Omniverse.

![image](https://user-images.githubusercontent.com/589439/143657605-6b09b104-698d-4eba-b5f7-e027eee033eb.png)

 - Click Start with the default settings with "Issac Sim" selected.

![image](https://user-images.githubusercontent.com/589439/143657653-c3d31131-1da7-4919-b7dd-8a9555c4aba6.png)

 - Once Isaac Sim has finished loading, login to localhost with the browser window that opened.

![image](https://user-images.githubusercontent.com/589439/143658289-5d6ed582-e15f-4ca7-b3dd-b7cd1d37a2fb.png)

![image](https://user-images.githubusercontent.com/589439/143658399-7538b399-a050-4468-842f-32cfe782bf80.png)

From here we can launch the Isaac Sim application. Currently there is no way to generate KITTI formated output synthetic data (which is required for Nvidia's transfer learning) from the domain randomizer within the application itself.

For this we need to use Omniverse's built in python environment. 

## Python API Installation

1. Using the Linux command line interface (terminal), go to the packages root folder (home/.local/share/ov/pkg/isaac_sim-2021.2.0/).

       cd ~/.local/share/ov/pkg/isaac_sim-2021.2.0/

       ls

![image](https://user-images.githubusercontent.com/589439/143659975-91da9c57-e9c0-4c41-a208-c02010656a83.png)

2. Run the following command to get all the required dependencies:

       ./python.sh -m pip install -r requirements.txt

![image](https://user-images.githubusercontent.com/589439/143660049-8e2288b8-14c4-4503-a4d4-56fb45574849.png)
