
## Franka Research 3 FCI Equipment

Written by Jiayu Song

System: **Ubuntu 22.04 Pro** for realtime kernel （Very Important!!!）

About FP3 FCI, follow the official documentation: [English](https://frankaemika.github.io/docs/), [中文](https://www.franka.cn/FCI/overview.html)

- ubuntu realtime kernel does not support nvidia gpu driver but we still have to use gpu driver and realtime kernel at the same time, so we will meet this problem:
```
(base) rlcl@eit709:~$ nvidia-smi
NVIDIA-SMI has failed because it couldn't communicate with the NVIDIA driver. Make sure that the latest NVIDIA driver is installed and running.
```

Use this command to re-install gpu driver (change <gpu_driver> to your dirver file):
```
sudo bash <gpu_driver>.run IGNORE_PREEMPT_RT_PRESENCE=1
```
