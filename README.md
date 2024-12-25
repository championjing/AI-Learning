## Facenet：人脸识别模型在Pytorch当中的实现
---

## 说明
基于 https://github.com/bubbliiiing/facenet-pytorch
## 环境说明
- 原文中说需要pytorch==1.2.0，但没指明python版本，在pypi.org官网上看到pytorch==1.2.0需要python3.7
- pytorch==1.2.0，使用本地安装终于成功 pip install torch-1.2.0-cp37-none-macosx_10_7_x86_64.whl
- vscode 的python debug不再支持python3.8以下版本

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
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install numpy==1.8.2 -i https://pypi.tuna.tsinghua.edu.cn/simple

764  pip install numpy==1.17.0
765  pip install matplotlib==3.1.2
766  pip install opencv_python==4.1.2.30
767  pip install tqdm==4.60.0
768  pip install Pillow==8.2.0
769  pip install h5py==2.10.0
770  pip install scikit-learn
771  pip install tensorboard
772  pip install past
~~~
