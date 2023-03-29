# nnUNet_test

# 1）什么是abstractmethod和staticmethod? 

abstractmethod和staticmethod都是装饰器。abstractmethod表示抽象方法，一般用在继承类中，父类只定义抽象接口，继承的子类必须要实现抽象方法。staticmethod表示静态方法，在类中的普通方法需要依赖类的实例化对象来调用，而静态方法可以直接通过类调用。

# 2）以nnUNet为例介绍abstractmethod和staticmethod

## abstractmethod
![abstract](https://github.com/chuxiang93/nnUNet_test/blob/main/src/abstract.png)
如图read_images方法是类BaseReaderWriter的一个抽象方法，目的是实现数据读取功能，但是没有具体实现代码，由继承BaseReaderWriter的子类根据要读取的数据类型具体实现相对应数据读取代码。

## staticmethod
![static](https://github.com/chuxiang93/nnUNet_test/blob/main/src/static.png)
如图collect_foreground_intensities方法是类DatasetFingerprintExtractor的一个静态方法，这个方法功能是收集数据集前景信息，是一个独立的函数方法，可以放在任何模块里。这里作为一个静态方法可以不需要实例化类即可调用，我们完全可以在用户代码里任何位置独立调用该方法，而不需要管类的实例化参数是什么。


# 3）使用nnUNet跑Medical Segmentation Decathlon数据里的Task004任务
## 模型链接
nnUNetv2训练好的模型链接：[checkpoint](https://github.com/chuxiang93/nnUNet_test/blob/main/model/checkpoint_best.pth)

## 分割结果
![002_image](https://github.com/chuxiang93/nnUNet_test/blob/main/src/002_image.png)
![002_label](https://github.com/chuxiang93/nnUNet_test/blob/main/src/002_label.png)

