# Perintah pada Jupyter Lab

### Menjalankan service Jupyter Lab pada host dan port tertentu
```
jupyter lab --port <PORT> --ip <HOST> --allow-root
```

### Impor extension tensorboard pada notebook Jupyter Lab
```
%load_ext tensorboard
```

### Mengaktifkan tensorboard pada notebook
```
tensorboard --logdir <DIREKTORI_LOG_TENSORBOARD> --host <HOST ATAU IP> --port <PORT> 
```
