## Facenet：人脸识别模型在Pytorch当中的实现
---

## 说明
基于 https://github.com/bubbliiiing/facenet-pytorch
## 环境说明
- 原文中说需要pytorch==1.2.0，但没指明python版本，在pypi.org官网上看到pytorch==1.2.0需要 python3.7 ,
- pytorch==1.2.0，使用本地安装终于成功 pip install torch-1.2.0-cp37-none-macosx_10_7_x86_64.whl, 此依赖没有windows版本
- vscode 的python debug不再支持python3.8以下版本
- win下的vscode 不支持wls系统中的python，因为只接受.exe的文件，可使用pychrom
- 经验证，py3.7会影响post模块不能安装，必须3.7一下版本，所以选py3.6
- 确实post模块，通过安装pip install future==1.0.0 解决

## 操作步骤
1. 在datasets文件夹下新建一个文件夹，将一类图片放入
2. 使用txt_annotation.py生成txt文件,形如：
~~~
1;D:\Code\space-my\AI-Learning\datasets\guanjun\01.JPG
2;D:\Code\space-my\AI-Learning\datasets\youshan\1.png
~~~
3. 运行train.py

## 使用的命令
~~~
如果是windows则在wls的conda中执行

pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
pip install torch==1.2.0
764  pip install numpy==1.17.0
765  pip install matplotlib==3.1.2
766  pip install opencv_python==4.1.2.30
767  pip install tqdm==4.60.0
768  pip install Pillow==8.2.0
769  pip install h5py==2.10.0
770  pip install scikit-learn
pip install protobuf==3.19.0
pip install future==1.0.0
~~~
## 调试记录
正确安装依赖后，运行train.py报错
~~~
Traceback (most recent call last):
  File "/mnt/d/Code/space-my/AI-Learning/train.py", line 263, in <module>
    LFWDataset(dir=lfw_dir_path, pairs_path=lfw_pairs_path, image_size=input_shape), batch_size=32, shuffle=False) if lfw_eval_flag else None
  File "/mnt/d/Code/space-my/AI-Learning/utils/dataloader.py", line 153, in __init__
    super(LFWDataset, self).__init__(dir,transform)
  File "/home/champ/miniconda3/envs/AI-Learning-linux-36/lib/python3.6/site-packages/torchvision/datasets/folder.py", line 209, in __init__
    is_valid_file=is_valid_file)
  File "/home/champ/miniconda3/envs/AI-Learning-linux-36/lib/python3.6/site-packages/torchvision/datasets/folder.py", line 97, in __init__
    "Supported extensions are: " + ",".join(extensions)))
RuntimeError: Found 0 files in subfolders of: lfw
Supported extensions are: .jpg,.jpeg,.png,.ppm,.bmp,.pgm,.tif,.tiff,.webp
ERROR conda.cli.main_run:execute(125): `conda run python /mnt/d/Code/space-my/AI-Learning/train.py` failed. (See above for error)
~~~
