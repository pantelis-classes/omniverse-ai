# Installing running detectnet_v2 in a jupyter notebook

## Setup File Structures.

 - Run these commands to create the correct file structure.

        cd ~

        mkdir tao

        mv cv_samples_v1.2.0/ tao
        
        cd tao/cv_samples_v1.2.0/
        
        rm -r detectnet_v2

![image](https://user-images.githubusercontent.com/589439/143797815-904b6033-f5db-43ac-a736-d653d4d19cfe.png)

![image](https://user-images.githubusercontent.com/589439/143797903-cd33e342-e45d-44ca-a8ac-6efb6d2cd18f.png)

 - Download the detectnet_v2.zip from this <a href="https://github.com/pantelis-classes/omniverse-ai/raw/main/detectnet_v2.zip">link</a>.

![image](https://user-images.githubusercontent.com/589439/143727479-6828fc05-4672-4c60-8a21-f1fe6e97d0ea.png)

 - Run this command to move the .zip from your downloads folder to your detectnet_v2 folder.

        mv ~/Downloads/detectnet_v2.zip ~/tao/cv_samples_v1.2.0/

![image](https://user-images.githubusercontent.com/589439/143798005-a702ed00-5971-4ece-b60a-d05e14fa09b9.png)

 - Run this command to unzip the folder.

        unzip ~/tao/cv_samples_v1.2.0/detectnet_v2.zip -d detectnet_v2

![image](https://user-images.githubusercontent.com/589439/143798404-ae066e4a-d573-4144-a1ec-b5410db9efb7.png)

![image](https://user-images.githubusercontent.com/589439/143798434-9d14756d-2bdb-4f68-88cb-0e5610562034.png)

 - Run this command to copy your dataset to the TAO folder. (You generated this dataset in this <a href="https://github.com/pantelis-classes/omniverse-ai/wiki/Synthetic-Data-Generation-(Python-API)#offline-training-with-tlt">wiki page</a>.)

        cp -r ~/.local/share/ov/pkg/isaac_sim-2021.2.0/output/testing/ ~/tao/cv_samples_v1.2.0/detectnet_v2/workspace/tao-experiment/data/

        cp -r ~/.local/share/ov/pkg/isaac_sim-2021.2.0/output/training/ ~/tao/cv_samples_v1.2.0/detectnet_v2/workspace/tao-experiment/data/

![image](https://user-images.githubusercontent.com/589439/143798514-be064b8e-18e9-4f21-97b2-ef72820190a8.png)

![image](https://user-images.githubusercontent.com/589439/143798539-d7555c9c-87c3-4037-819a-ee32aca9fa44.png)

 - Navigate to Home -> cv_samples_v1.2.0 -> detectnet_v2

 - Open the detectnet_v2.ipynb file.

![image](https://user-images.githubusercontent.com/589439/143729232-16e479b2-527e-4b0f-94b0-e43bd08cfba8.png)

 - Scroll down to section "0. Set up env variables and map drives" (Ctrl + F)

 ![image](https://user-images.githubusercontent.com/589439/143729413-dffdd2dc-d0cb-40aa-8b0f-fd567b2a527c.png)

 - Replace "diego" with your username. (TIP: whoami in BASH)

 ![image](https://user-images.githubusercontent.com/589439/143729441-e43fde75-76ed-489d-acef-56fea5ddf539.png)

 ![image](https://user-images.githubusercontent.com/589439/143729521-c7b0fc38-baf0-4701-9032-dba324497f5e.png)