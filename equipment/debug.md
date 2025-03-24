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
