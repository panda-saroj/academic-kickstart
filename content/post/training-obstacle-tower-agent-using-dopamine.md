+++
title = "Training Obstacle Tower Agent Using Dopamine" 
date = 2019-05-17T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Saroj Panda"]

#List format.
#0 = Simple
#1 = Detailed
#2 = Stream
list_format = 2

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Abstract"]

#Optional featured image (relative to static/img/ folder).
[header] 
image = "" 
caption = "" 
+++

<body>

<b>Environment:</b> <br>
Linux: Ubuntu 16.04 <br>
Python: 3.6.8

<b>Step 1</b> <br>
Create a conda virtual environment with your virtual environment name(e.g. venv_dopamine) <br>
conda create -n venv_dopamine python=3.6.8 anaconda <br>

<b>Step 2</b> <br>
Activate the virtual environment <br>
conda activate venv_dopamine <br>

<b>Step 3</b> <br>
Move to the virtual environment directory <br>
cd venv_dopamine 

<b>Step 4</b> <br>
Install the Obstacle Tower Environment <br>
git clone https://github.com/Unity-Technologies/obstacle-tower-env

<b>Step 5</b> <br>
cd obstacle-tower-env <br>
pip install ./ <br>
cd ..

<b>Step 6</b> <br>
Download Obstacle Tower Executables <br>
wget https://storage.googleapis.com/obstacle-tower-build/v1.3/obstacletower_v1.3_linux.zip

<b>Step 7</b> <br>
Extract the downloaded Obstacle Tower environment <br>
unzip obstacletower_v1.3_linux.zip

<b>Step 8</b> <br>
Install Dopamine <br>
<b>Step 8.1</b> <br>
Install Dopamine Dependencies <br>
sudo apt update  <br>
sudo apt install cmake zlib1g-dev <br>
pip install absl-py atari-py gin-config gym opencv-python

<b>Step 8.2</b> <br>
Download Dopamine Repository <br>
git clone https://github.com/google/dopamine.git <br>
pip install absl-py atari-py gin-config gym opencv-python tensorflow-gpu

<b>Step 9</b> <br>
Making Dopamine compatible with Obstacle Tower <br>
Install the files that enable Dopamine to interact with the Obstacle Tower files. Download and extract those files. <br>
wget https://storage.googleapis.com/obstacle-tower-build/dopamine/dopamine_otc.zip <br>
unzip dopamine_otc.zip

<b>Step 10</b> <br>
Place unity_lib.py in dopamine/dopamine/discrete_domains <br>
cp dopamine_otc/unity_lib.py dopamine/dopamine/discrete_domains/unity_lib.py

<b>Step 11</b> <br>
Place rainbow_otc.gin in a convenient location, e.g. dopamine/dopamine/agents/rainbow/configs. <br>
cp dopamine_otc/rainbow_otc.gin dopamine/dopamine/agents/rainbow/configs/rainbow_otc.gin

<b>Step 12</b> <br>
rainbow_otc.gin file contains the configuration for training the Rainbow agent in Obstacle Tower Environment Modify it as per your need.

<b>Step 13</b> <br>
Training with Dopamine. Move to the dopamine directory and start the training <br>
cd ./dopamine <br>
python -um dopamine.discrete_domains.train --base_dir=/tmp/dopamine --gin_files='dopamine/agents/rainbow/configs/rainbow_otc.gin'

<b>Step 14</b> <br>
If faced with problem of <b>ImportError: libcublas.so.10.0: cannot open shared object file: No such file or directory</b> <br>
Find whether the file exist or not <br>
locate libcublas.so.10.0

















