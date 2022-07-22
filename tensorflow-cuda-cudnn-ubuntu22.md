# How to install tensorflow, cuda and cudnn in Ubuntu 22.04

1. Update and Upgrade

```bash
sudo apt-get update
sudo apt-get upgrade
```

2. Check out the latest available drivers

```bash
ubuntu-drivers devices
```

```
humberto@legio-germanica:~/Documents$ ubuntu-drivers devices
== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
modalias : pci:v000010DEd00002191sv000017AAsd00003FFCbc03sc00i00
vendor   : NVIDIA Corporation
model    : TU116M [GeForce GTX 1660 Ti Mobile]
manual_install: True
driver   : nvidia-driver-515-server - distro non-free
driver   : nvidia-driver-450-server - distro non-free
driver   : nvidia-driver-470 - distro non-free
driver   : nvidia-driver-470-server - distro non-free
driver   : nvidia-driver-510 - distro non-free
driver   : nvidia-driver-515 - distro non-free recommended
driver   : nvidia-driver-418-server - distro non-free
driver   : nvidia-driver-510-server - distro non-free
driver   : xserver-xorg-video-nouveau - distro free builtin
```

If the latest driver is `nvidia-driver-515` then we should install it:

```bash
sudo apt-get install nvidia-driver-515
```

3. Reboot

```bash
sudo reboot
```

4. Check if the driver is installed

```bash
nvidia-smi
```

5. Install python3


```bash
sudo apt-get install python3-pip
sudo apt-get install python3-dev
```

6. Install Virtual Environments

```bash
sudo apt-get install python3-venv
```

7. Install cuda toolkit and cudnn

```bash
sudo apt-get install -y nvidia-cuda-toolkit
sudo apt-get install -y nvidia-cudnn
```

8. Install Tensorflow

```bash
mkdir tensorflow
cd tensorflow
python3 -m venv tensorvenv
cd tensorvenv
cd bin
source activate
```

9. Upgrade pip and install tensorflow

```bash
pip install --upgrade pip
pip install --upgrade tensorflow
```

10. Test the environment

```python
import tensorflow as tf

print(tf.version.VERSION)
```
