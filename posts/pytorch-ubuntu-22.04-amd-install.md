# Pytorch Install for Ubuntu 22.04 with AMD ROCm 5.3
#### February 22, 2023

I have some AMD Radeon VII GPUs that I wanted to try and do some Machine Learning (ML) on using Pytorch.  This post discusses the steps I took to install Pytorch on Ubuntu 22.04 using AMD ROCm 5.3.

### Pytorch and AMD ROCm Versions

First, you __need__ to make sure you have the correct versions of both ROCm and Pytorch.  That is, for a certain version of Pytorch there are only certain versions of ROCm that are supported and vice versa.

To know which version of Pytorch and ROCm you need you will need to do two things.

### Pytorch Start Locally and `amdgpu-install`

Go to [Pytorch Start Locally](https://pytorch.org/get-started/locally/) and select the software setup of your system using the animated bars.  This will show you the command you need to execute for installing Pytorch.  Go ahead and write this down as you will be needing it later.  As of this writing you can either choose the stable version of Pytorch or the nightly build.  At first when I was doing this, I chose the stable version.  However, this only gave ROCm 5.2, which was no longer supported via [`amdgpu-install`](https://repo.radeon.com/amdgpu-install/).  A quick aside, `amdgpu-install` is a package you install on Ubuntu that you can then use from the command line to install different packages and drivers from AMD.  Now back to the task at hand, luckily the nightly build of Pytorch supported ROCm 5.3 and there was a version 5.3 of `amdgpu-install` available.  YMMV but hopefully you can find versions that are available and work for you.

### Installing amdgpu-install and ROCm 5.3

Now that you know which version of Pytorch, `amdgpu-install` and ROCm you will need, go and download the `amdgpu-install` debian package.  For me this was:
```
    amdgpu-install_5.3.50300-1_all.deb
```

Install this package either with the software installer application or on the command line:
```
    sudo dpkg -i amdgpu-install_5.3.50300-1_all.deb
```

Then execute:
```
    amdgpu-install --list-usecase
```
which will list the options you can pass to the command for the types of packages that you want to install.

For me this ended up being:
```
    sudo amdgpu-install --usecase=rocm,hip,mllib,mlsdk --no-dkms
```
This command will then download and install the associated drivers and packages.

You will also need to add the user to the groups `video` and `render` as so:

```
    sudo usermod -a -G video $LOGNAME
    sudo usermod -a -G render $LOGNAME
```

Then, opening up another terminal type:

```
    rocminfo
```
and you should get appropriate output showing that your AMD GPU is recognized.  If not, try rebooting.


### Installing Pytorch

Now that command you wrote down from above will be executed.  For me this was:
```
    pip3 install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/rocm5.3
```

Now, test that Pytorch was installed correctly by opening a python terminal:

```python
    import torch
    torch.cuda.is_available()
    torch.cuda.get_device_name(torch.cuda.current_device())
```
which should display the name of your GPU.  Also, don't worry about the name `cuda` above as apparently this now applies to both NVIDIA and AMD GPUs.

This wraps up this quick blog post and hope that it was of some benefit to you.