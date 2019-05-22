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

<b>Environment:</b>
Linux: Ubuntu 16.04
Python: 3.6.8

<b>Step 1</b>
Create a conda virtual environment with your virtual environment name(e.g. venv_dopamine)
conda create -n venv_dopamine python=3.6.8 anaconda

<b>Step 2</b>
Activate the virtual environment
conda activate venv_dopamine

<b>Step 3</b>
Move to the virtual environment directory
cd venv_dopamine

<b>Step 4</b>
Install the Obstacle Tower Environment
git clone https://github.com/Unity-Technologies/obstacle-tower-env

<b>Step 5</b>
cd obstacle-tower-env
pip install ./ 
cd ..

<b>Step 6</b>
Download Obstacle Tower Executables
wget https://storage.googleapis.com/obstacle-tower-build/v1.3/obstacletower_v1.3_linux.zip

<b>Step 7</b>
Extract the downloaded Obstacle Tower environment
unzip obstacletower_v1.3_linux.zip

<b>Step 8</b>
Install Dopamine
<b>Step 8.1</b>
Install Dopamine Dependencies
sudo apt update 
sudo apt install cmake zlib1g-dev
pip install absl-py atari-py gin-config gym opencv-python

<b>Step 8.2</b>
Download Dopamine Repository
git clone https://github.com/google/dopamine.git
pip install absl-py atari-py gin-config gym opencv-python tensorflow-gpu

<b>Step 9</b>
Making Dopamine compatible with Obstacle Tower
Install the files that enable Dopamine to interact with the Obstacle Tower files. Download and extract those files.
wget https://storage.googleapis.com/obstacle-tower-build/dopamine/dopamine_otc.zip
unzip dopamine_otc.zip

<b>Step 10</b>
Place unity_lib.py in dopamine/dopamine/discrete_domains
cp dopamine_otc/unity_lib.py dopamine/dopamine/discrete_domains/unity_lib.py

<b>Step 11</b>
Place rainbow_otc.gin in a convenient location, e.g. dopamine/dopamine/agents/rainbow/configs.
cp dopamine_otc/rainbow_otc.gin dopamine/dopamine/agents/rainbow/configs/rainbow_otc.gin

<b>Step 12</b>
rainbow_otc.gin file contains the configuration for training the Rainbow agent in Obstacle Tower Environment Modify it as per your need.

<b>Step 13</b>
Training with Dopamine. Move to the dopamine directory and start the training
cd ./dopamine
python -um dopamine.discrete_domains.train --base_dir=/tmp/dopamine --gin_files='dopamine/agents/rainbow/configs/rainbow_otc.gin'

<b>Step 14</b>
If faced with problem of <b>ImportError: libcublas.so.10.0: cannot open shared object file: No such file or directory</b>
Find whether the file exist or not
locate libcublas.so.10.0

















