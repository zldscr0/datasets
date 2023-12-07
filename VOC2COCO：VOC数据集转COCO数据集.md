### VOC2COCO：VOC数据集转COCO数据集

##### 参考资料

https://mmdetection.readthedocs.io/zh-cn/latest/user_guides/useful_tools.html#id17



##### 数据集下载

https://opendatalab.com/OpenDataLab/PASCAL_VOC2007/tree/main?source=OpenMMLab%20GitHub

1.把raw文件夹下的这三个文件夹下载下来

![image-20231207154156421](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20231207154156421.png)



2.解压三个文件夹

```bash
tar -xvf VOCdevkit_08-Jun-2007.tar
tar -xvf VOCtest_06-Nov-2007.tar
tar -xvf VOCtrainval_06-Nov-2007.tar
```

然后三个压缩包里的东西都会被解压到一个`VOCdevkit`文件夹中



3.运行代码

```
python tools/dataset_converters/pascal_voc.py ${DEVKIT_PATH} [-h] [-o ${OUT_DIR}]
```

例：

```bash
python tools/dataset_converters/pascal_voc.py /data/bzx_yjy/VOC2007/VOCdevkit -o .
```

默认的转换格式是pkl，改成coco或者在命令行里加一个 `--out-format coco`

![image-20231207154630610](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20231207154630610.png)

DEVKIT_PATH换成VOCdevkit文件夹所在地址



4.生成的voc07_train.json等json文件放在一个annotations里

图片在`VOCdevkit/VOC2007/JPEGImages`中

可以再用一些脚本把图片放到train、test、val里，也可以改一下读取图片的地址，统一换到`JPEGImages`中即可。

