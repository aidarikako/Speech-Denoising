# Speech Denoising with Deep Feature Losses
## 简介
本项目使用中文人声的数据集，在Speech Denoising with Deep Feature Losses网络的基础上fine-tune，得到对中文音频有更好去噪效果的结果。
## 快速使用
1.下载清华大学的中文语料库[THCHS-30](http://www.openslr.org/18/)中的数据集，或者使用自己的语料数据集。并将其中的音频部分放在./data/trainset_clean文件夹中（注意数据集音频需要wav格式）。

2.运行./data/extract.py来从测试样本中提取你所需的噪声，并保存为xxx.npy格式。

3.运行./data/sox.py，将训练数据集中的音频调整为网络适用的32bit。

4.运行./data/noise.py，创建训练数据集的副本并将提取出的噪声添加到你的副本中作为噪声集。

5.将噪声集的音频全部放入./data/trainset_noisy文件夹中。

6.运行'python senet_train.py -d /data  -o out_folder'，训练模型将会被保存在out_folder文件夹中
## 网络模型
out_folder文件夹中已有使用THCHS-30数据集，学习率为1e-4，运行10个epoch微调后得到的10个网络模型，可以直接使用。
