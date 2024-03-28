# Object Detection using TAO DetectNet_v2

 - Transfer learning is the process of transferring learned features from one application to another. It is a commonly used training technique where you use a model trained on one task and re-train to use it on a different task. 

 - Train Adapt Optimize (TAO) Toolkit  is a simple and easy-to-use Python based AI toolkit for taking purpose-built AI models and customizing them with users' own data.

## How to use the notebook.

 - Please refer to the actual jupyter notebook to have more in-depth explanations of the code.

 - Each Cell will run some lines of code. Start from the top of the notebook and run each cell by click the play button or using **shift + enter**.

![image](https://user-images.githubusercontent.com/589439/143809035-2ae69802-7929-47a6-a445-12b571cacd14.png)

 - Some of the cells may take a long time to complete. Please do not skip cells and wait for the output to finish.

## 0. Set up env variables and map drives

![image](https://user-images.githubusercontent.com/589439/143808844-e4244060-5842-41e2-868d-7a75c57a3c21.png)

![image](https://user-images.githubusercontent.com/589439/143809423-cea91ff5-916f-4c03-b7c3-e4eb625756a4.png)

 - We set up the env variables by linking paths, setting number of GPUs, and choosing an encoding style.

## 1. Install the TAO launcher

 - This step should have been already completed in the previous wiki pages. Please refer to this <a href="https://github.com/pantelis-classes/omniverse-ai/wiki/TAO-(NVIDIA-Train,-Adapt,-and-Optimize)#login-to-the-ngc-docker-registry">link</a>.

![image](https://user-images.githubusercontent.com/589439/143809877-6e766d73-ff1c-405f-bd6f-600a58736b25.png)

## 2. Prepare dataset and pre-trained model

![image](https://user-images.githubusercontent.com/589439/143809929-1e119a3b-0239-4144-bece-a1d9aa7d51bf.png)

![image](https://user-images.githubusercontent.com/589439/143809965-7997fd22-e172-4360-af13-8c0d65b83f4e.png)

![image](https://user-images.githubusercontent.com/589439/143809992-3a41471a-dd02-4a3e-acea-96b7a7c3a674.png)

![image](https://user-images.githubusercontent.com/589439/143810068-5f175928-4e4d-4820-8b14-067a31b35cd6.png)

![image](https://user-images.githubusercontent.com/589439/143810077-6bfb77d3-4643-4129-a8c4-0b4fbf196b43.png)

![image](https://user-images.githubusercontent.com/589439/143810093-f8508bb1-5728-4010-b87b-21f4aed74e73.png)

![image](https://user-images.githubusercontent.com/589439/143810115-c88787cb-3cae-433a-93c8-712a25db0c78.png)

## 3. Provide training specification

![image](https://user-images.githubusercontent.com/589439/143810872-231209ca-eb71-4bd2-930d-3527fbaaace0.png)

## 4. Run TAO training

![image](https://user-images.githubusercontent.com/589439/143810896-a9875ab8-b9ab-4ced-ad49-c47ea321a052.png)

## 5. Evaluate the trained model

![image](https://user-images.githubusercontent.com/589439/143811275-488e15be-15bd-4341-8392-834cd68bbcad.png)



## 6. Prune the trained model

![image](https://user-images.githubusercontent.com/589439/143810915-c9428405-1f00-462d-8a80-2d1467c95e7b.png)

## 7. Retrain the pruned model

![image](https://user-images.githubusercontent.com/589439/143810942-972f34b4-b7a4-4532-9e8d-6f6bcc01ac9f.png)

![image](https://user-images.githubusercontent.com/589439/143810970-69367200-b71e-481f-b813-3d447e154bb3.png)

## 8. Evaluate the retrained model

![image](https://user-images.githubusercontent.com/589439/143811255-0b946589-2679-4747-b514-3b91ac2259cd.png)


## 9. Visualize inferences

![image](https://user-images.githubusercontent.com/589439/143811032-4adc40ef-fa0e-4596-88b5-2a24610cdaf3.png)

![image](https://user-images.githubusercontent.com/589439/143811081-edaa58f5-d3e6-40c6-9dab-f19e547d090e.png)