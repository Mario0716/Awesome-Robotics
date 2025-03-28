# Debug & Error 🔧
Written by Jiayu Song

- Yesterday everything goes well but there are many bugs about CUDA when i want to run the project in the morning.
```
RuntimeError: CUDA unknown error - this may be due to an incorrectly set up environment, e.g. changing env variable CUDA_VISIBLE_DEVICES after program start. Setting the available devices to be zero.
```
Before verifying under command, plz make sure there is no problem about ```torch.cuda.is_available()``` and ```torch.version.cuda``` matches ```nvidia-smi``` 's CUDA Version.
```
sudo apt-get install nvidia-modprobe
```

- when I want to run DP3 project, there is a error
```
libEGL warning: MESA-LOADER: failed to open nouveau: /usr/lib/dri/nouveau_dri.so: cannot open shared object file: No such file or directory (search paths /usr/lib/x86_64-linux-gnu/dri:\$${ORIGIN}/dri:/usr/lib/dri, suffix _dri)

libEGL warning: MESA-LOADER: failed to open nouveau: /usr/lib/dri/nouveau_dri.so: cannot open shared object file: No such file or directory (search paths /usr/lib/x86_64-linux-gnu/dri:\$${ORIGIN}/dri:/usr/lib/dri, suffix _dri)
```
then, I tried the following command
```
 conda install -c conda-forge libstdcxx-ng
```

- Due to my python verison==3.13, there are many packages incompatible with it and I have to compile ```open3d``` by myself, then system had the following error about CMake
```
CMake Error at CMakeLists.txt:1 (cmake_minimum_required):   CMake 3.24 or higher is required.  You are running version 3.22.1
```
u can follow this [link](https://blog.csdn.net/loveric/article/details/142791754) to upgrade your CMake version.

- I spent 5 days in running dp3 in RTX 5080 and I gave up because of the conflict between python version and cuda version, then when I tested that project in the HPC platform, I met this error: 
```
ImportError: libGL.so.1: cannot open shared object file: No such file or directory
```
Test the following command,
```
pip uninstall opencv-python
pip install opencv-python-headless
```
- If u meet this bug, maybe your hugggingface_hub version is higher than 0.26,
```
ImportError: cannot import name 'cached_download' from 'huggingface_hub' (/opt/conda/lib/python3.8/site-packages/huggingface_hub/__init__.py)
```
try to downgrade that version following 
```
pip install huggingface_hub==0.25.2 
```
