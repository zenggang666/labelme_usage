# labelme_usage
## 一.labelme的安装
### 1.win10下安装labelme
#### 先安装anaconda，创建虚拟环境
1. conda create --name=labelme_env python=3.7
2. conda activte labelme_env
3. conda install labelme
4. labelme
#### 打开labelme后使用open dir打开要标注的图片文件夹
1. 逐一进行标注并选择要保存到哪个文件夹
2. 标注每张完后对应默认生成一个json格式文件
3. 将所有json文件存放到一个空的文件夹
#### 将json文件转化成图片来生成数据集
``` python
import os
path = 'yourt json file path'
file_list = os.listdir(path)
os.system('conda activate labelme_env')
for file in file_list:
    os.system('D:\\anaconda3\envs\pytorch\Scripts\labelme_json_to_dataset.exe {}'.format(os.path.join(path,file)))
```
#### 转化完成后，每个json文件对应生成一个文件夹，这个文件夹下有4个文件：
1. 原图
2. info.yaml
3. 生成彩色的mask，这是生成的label图片
4. label_viz图片，mask在原图上的叠加显示效果

