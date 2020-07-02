# Overview

This set of instructions should be followed in order to gain access to the DMT Lab's Neuromancer GPU cluster.
Use of the cluster is subject to (only a few) arbitrary rules. If you break them, you may lose access.

# Purpose & Basic Rules

1. The Neuromancer cluster is intended primarily for GPU compute use. As such, you should minimise your work on the system to training and running inference. Other use cases are welcome, but please discuss these with admin for sake of sanity.

2. Please develop and test your code locally.
3. Please use git to move your code to and from the machine.
4. Keep all projects in your home directory and please keep the number of conda environments to a reasonable number (<5)
5. Please use a single GPU, unless otherwise agreed (this will eventually be automated)

# Setup

1. Contact the current admin of the server (alan.dolhasz@bcu.ac.uk) and confirm approval
2. Generate a public and private key pair (use PuttyGen if on Windows)
3. Make sure the *private key* is protected by a password

4. Forward the public key and a chosen username (please keep it identifiable) to the admin and you will receive the IP address 
5. Once you get approval from admin, set up an SSH connection to the server using the IP address, your private key and your chosen username
6. Log into the server.
7. Run the following command on the server to initialise Anaconda for your user:
```
/opt/miniconda3/bin/conda init --all
```
8. *IMPORTANT* Create a conda environment for your project. *DO NOT* use the `base` environment. This is to ensure clean environments are used for any training runs and that the Python environments don't get bloated.
```
conda create -n my_amazing_env_name python=3.7
```
9. Activate your environment `conda activate my_amazing_env_name` and proceed as usual (install packages etc). 

**If you want to use Tensorflow, please install it using the following command:**
```
conda install tensorflow-gpu
```

All environments will be private to you and contained within your user folder. Again, please keep the number of environments limited - they bloat in size pretty quickly, especially if each one has a copy of a large DL library like Tf2.

# TODO (upcoming features):

- Queue system
- GPU allocation (1,2,3)
- Fun stuff
- Benchmarks and multi-user tests
