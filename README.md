# capston_eye_for_blind
Capston project eye for blind run in both google colab and Jarvis lab


Jarvis:

CUDA setup done with CUDA 11.8 and CuDNN 8.6 

https://developer.nvidia.com/rdp/cudnn-archive

CUDA Toolkit Installer	
Installation Instructions:
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64/cuda-ubuntu2404.pin
sudo mv cuda-ubuntu2404.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.6.3/local_installers/cuda-repo-ubuntu2404-12-6-local_12.6.3-560.35.05-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2404-12-6-local_12.6.3-560.35.05-1_amd64.deb
sudo cp /var/cuda-repo-ubuntu2404-12-6-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-6



root@9c6ab9c8ab15:~/eyeforblind# dpkg -i cudnn-local-repo-ubuntu2204-8.6.0.163_1.0-1_amd64.deb
Selecting previously unselected package cudnn-local-repo-ubuntu2204-8.6.0.163.
(Reading database ... 46832 files and directories currently installed.)
Preparing to unpack cudnn-local-repo-ubuntu2204-8.6.0.163_1.0-1_amd64.deb ...
Unpacking cudnn-local-repo-ubuntu2204-8.6.0.163 (1.0-1) ...
Setting up cudnn-local-repo-ubuntu2204-8.6.0.163 (1.0-1) ...

The public cudnn-local-repo-ubuntu2204-8.6.0.163 GPG key does not appear to be installed.
To install the key, run this command:
sudo cp /var/cudnn-local-repo-ubuntu2204-8.6.0.163/cudnn-local-FAED14DD-keyring.gpg /usr/share/keyrings/

root@9c6ab9c8ab15:~/eyeforblind# cp /var/cudnn-local-repo-ubuntu2204-8.6.0.163/cudnn-local-FAED14DD-keyring.gpg /usr/share/keyrings/
root@9c6ab9c8ab15:~/eyeforblind# apt-get update
Get:1 file:/var/cudnn-local-repo-ubuntu2204-8.6.0.163  InRelease [1575 B]
Get:1 file:/var/cudnn-local-repo-ubuntu2204-8.6.0.163  InRelease [1575 B]
Get:2 file:/var/cudnn-local-repo-ubuntu2204-8.6.0.163  Packages [944 B]                                
Hit:3 http://archive.ubuntu.com/ubuntu focal InRelease                                                                           
Get:4 http://security.ubuntu.com/ubuntu focal-security InRelease [128 kB]                              
Get:5 http://archive.ubuntu.com/ubuntu focal-updates InRelease [128 kB]
Get:6 http://security.ubuntu.com/ubuntu focal-security/universe amd64 Packages [1277 kB]
Get:7 http://archive.ubuntu.com/ubuntu focal-backports InRelease [128 kB]
Get:8 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [4575 kB]
Get:9 http://security.ubuntu.com/ubuntu focal-security/restricted amd64 Packages [4137 kB]
Get:10 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [4107 kB]
Get:11 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [1568 kB]     
Get:12 http://archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [4299 kB]  
Get:13 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [30.9 kB]   
Get:14 http://archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [33.5 kB]      
Get:15 http://archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [28.6 kB]
Get:16 http://archive.ubuntu.com/ubuntu focal-backports/main amd64 Packages [55.2 kB]
Fetched 20.5 MB in 5s (4464 kB/s)                           
Reading package lists... Done
root@9c6ab9c8ab15:~/eyeforblind# apt-get install libcudnn8 libcudnn8-dev libcudnn8-doc
Reading package lists... Done
Building dependency tree       
Reading state information... Done
E: Unable to locate package libcudnn8-doc
root@9c6ab9c8ab15:~/eyeforblind# apt-get install libcudnn8 libcudnn8-dev 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages will be upgraded:
  libcudnn8 libcudnn8-dev
2 upgraded, 0 newly installed, 0 to remove and 185 not upgraded.
Need to get 0 B/883 MB of archives.
After this operation, 338 MB disk space will be freed.
Get:1 file:/var/cudnn-local-repo-ubuntu2204-8.6.0.163  libcudnn8-dev 8.6.0.163-1+cuda11.8 [437 MB]
Get:2 file:/var/cudnn-local-repo-ubuntu2204-8.6.0.163  libcudnn8 8.6.0.163-1+cuda11.8 [446 MB]                                                                                
debconf: unable to initialize frontend: Dialog                                                                                                                                
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 76, <> line 2.)
debconf: falling back to frontend: Readline
(Reading database ... 46848 files and directories currently installed.)
Preparing to unpack .../libcudnn8-dev_8.6.0.163-1+cuda11.8_amd64.deb ...
update-alternatives: removing manually selected alternative - switching libcudnn to auto mode
Unpacking libcudnn8-dev (8.6.0.163-1+cuda11.8) over (8.3.2.44-1+cuda11.5) ...
Preparing to unpack .../libcudnn8_8.6.0.163-1+cuda11.8_amd64.deb ...
Unpacking libcudnn8 (8.6.0.163-1+cuda11.8) over (8.3.2.44-1+cuda11.5) ...
Setting up libcudnn8 (8.6.0.163-1+cuda11.8) ...
Setting up libcudnn8-dev (8.6.0.163-1+cuda11.8) ...
update-alternatives: using /usr/include/x86_64-linux-gnu/cudnn_v8.h to provide /usr/include/cudnn.h (libcudnn) in auto mode
root@9c6ab9c8ab15:~/eyeforblind# dpkg -l | grep libcudnn
ii  libcudnn8                              8.6.0.163-1+cuda11.8              amd64        cuDNN runtime libraries
ii  libcudnn8-dev                          8.6.0.163-1+cuda11.8              amd64        cuDNN development libraries and headers
root@9c6ab9c8ab15:~/eyeforblind# nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2021 NVIDIA Corporation
Built on Fri_Dec_17_18:16:03_PST_2021
Cuda compilation tools, release 11.6, V11.6.55
Build cuda_11.6.r11.6/compiler.30794723_0
root@9c6ab9c8ab15:~/eyeforblind# 



Enhanced image captioning project by including Data Augmentation, Batch Normalization, and other performance improvements directly into your notebook/script.

1. Data Augmentation
We'll add image augmentations such as flipping, rotating, zooming, and brightness adjustments. These augmentations can be applied during the data preprocessing stage.

2. Batch Normalization
Batch Normalization will be added to stabilize and speed up training, typically after the dense or GRU layers in the encoder and decoder.

3. Performance Improvements
Optimizer Adjustment: Use Adam with learning rate schedules.
Regularization: Dropout layers in the decoder.
Image Normalization: Normalize image pixel values for stability.
Modified Code Sections
Data Augmentation
Include data augmentation in the preprocessing pipeline:
