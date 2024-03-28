# Synthetic Data in Omniverse from Isaac Sim

Omniverse comes with synthetic data generation samples in Python. These can be found in (home/.local/share/ov/pkg/isaac_sim-2021.2.0/python_samples)

## Offline Dataset Generation
This example will demonstrate how to generate synthetic dataset offline which can be used for training deep neural networks using default values.

From the package root folder (home/.local/share/ov/pkg/isaac_sim-2021.2.0/) run this command to generate synthetic data:

       ./python.sh standalone_examples/replicator/offline_generation.py

These are the arguments we can use:


1. --scenario: Specify the USD stage to load from omniverse server for dataset generation.

1. --num_frames: Number of frames to record.

1. --max_queue_size: Maximum size of queue to store and process synthetic data. If value of this field is less than or equal to zero, the queue size is infinite.

1. --data_dir: Location where data will be output. Default is ./output

1. --writer_mode: Specify output format - npy or kitti. Default is npy.

When KittiWriter is used with the --writer_mode kitti argument, two more arguments become available.

6. --classes: Which classes to write labels for. Defaults to all classes.

7. --train_size: Number of frames for training set. Defaults to 8.
queue size is infinite.

With arguments, the above command looks like:

       ./python.sh standalone_examples/replicator/offline_generation.py --scenario omniverse://<server-name>/Isaac/Samples/Synthetic_Data/Stage/warehouse_with_sensors.usd --num_frames 10 --max_queue_size 500

All output data is stored within (home/.local/share/ov/pkg/isaac_sim-2021.1.1/output)

## Offline Training with TLT
To leverage TLT, we need to have a dataset in the Kitti format. NVIDIA Transfer Learning Toolkit (TLT) is a Python-based AI toolkit for taking purpose-built pretrained AI models and customizing them with your own data.
### Offline Kitti Dataset Generation

for this we add the argument --writer_mode kitti and specify the classes like in this example (not specifying an argument makes it use the default):

       ./python.sh standalone_examples/replicator/offline_generation.py --writer_mode kitti --classes ceiling floor --num_frames 500 --train_size 100

![image](https://user-images.githubusercontent.com/589439/143666365-9cbab570-213f-403b-bdc9-d891025fabac.png)

![image](https://user-images.githubusercontent.com/589439/143666538-47885861-2340-4fca-9507-8a1a66d82fe9.png)

![image](https://user-images.githubusercontent.com/589439/143666560-4a7dd70c-abde-4af8-a1c7-16eab5d99bf3.png)

![omniverse data gen](https://user-images.githubusercontent.com/589439/143667012-183800ff-f197-44a7-9677-d19940a06179.gif)

The python scripts can be extensively modified to generate more customized datasets (code deep dive to come).

 - The output of the synthetic data generation can be found in: `~/.local/share/ov/pkg/isaac_sim-2021.2.0/output`

![image](https://user-images.githubusercontent.com/589439/143666727-f7a06dbc-aba6-410f-8bd5-0aa24ecf38d3.png)

 - The dataset is divided into two folders; A Training and Test Dataset. The training dataset contains **images** and **labels** of the warehouse.

![image](https://user-images.githubusercontent.com/589439/143666820-b12aafdd-f1e1-4c46-889c-34af1c9ca929.png)

![image](https://user-images.githubusercontent.com/589439/143666829-813f9715-3a2d-49f1-9124-5a690681accc.png)

![image](https://user-images.githubusercontent.com/589439/143666852-90d659de-01a0-4685-bf36-42868e1c77d9.png)

![image](https://user-images.githubusercontent.com/589439/143666866-5896317b-1255-4e67-abe7-5f3ff03be288.png)

 - The test dataset contains only **images**.

![image](https://user-images.githubusercontent.com/589439/143666874-a453b635-63e6-44e0-94c1-7127e1c7f729.png)

![omniversepicgen](https://user-images.githubusercontent.com/589439/143667064-d0136cd5-9b3e-4b5d-987f-c013ff08d401.gif)



