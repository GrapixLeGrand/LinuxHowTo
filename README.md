# Driver managing over Ubuntu
## Check setup
Type the following in a terminal:

```
nvidia-smi
```

If some sh*t like bellow shows up this means that the GPU and drivers are recognized

```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 460.91.03    Driver Version: 460.91.03    CUDA Version: 11.2     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  GeForce GTX 1050    Off  | 00000000:01:00.0 Off |                  N/A |
| N/A   52C    P0    N/A /  N/A |    343MiB /  4042MiB |      3%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A      1819      G   /usr/lib/xorg/Xorg                 45MiB |
|    0   N/A  N/A      2480      G   /usr/lib/xorg/Xorg                123MiB |
|    0   N/A  N/A      2653      G   /usr/bin/gnome-shell               92MiB |
|    0   N/A  N/A      3052      G   ...AAAAAAAAA= --shared-files       26MiB |
|    0   N/A  N/A      3265      G   ...AAAAAAAAA= --shared-files       45MiB |
+-----------------------------------------------------------------------------+

```

Else if you get an error message you'll need to figure out things


