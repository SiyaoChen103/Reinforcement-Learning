
#Reinforcement Learning -- ML For Decision Making

## 1、下载问题
### a、代码下载
**问：up主，可以给我发一份代码吗，代码在哪里下载啊？ 
答：Github上的地址就在视频简介里。复制一下就能进去下载了。**

**问：up主，为什么我下载的代码提示压缩包损坏？
答：重新去Github下载。**


### b、 权值下载
**问：up主，为什么我下载的代码里面，model_data下面没有.pth或者.h5文件？ 
答：我一般会把权值上传到Github和百度网盘，在GITHUB的README里面就能找到。**

### c、 数据集下载
**问：up主，XXXX数据集在哪里下载啊？
答：一般数据集的下载地址我会放在README里面，基本上都有，没有的话请及时联系我添加，直接发github的issue即可**。

## 2、环境配置问题
### a、现在库中所用的环境
**pytorch代码对应的pytorch版本为1.2，博客地址对应**[https://blog.csdn.net/weixin_44791964/article/details/106037141](https://blog.csdn.net/weixin_44791964/article/details/106037141)。

**keras代码对应的tensorflow版本为1.13.2，keras版本是2.1.5，博客地址对应**[https://blog.csdn.net/weixin_44791964/article/details/104702142](https://blog.csdn.net/weixin_44791964/article/details/104702142)。

**tf2代码对应的tensorflow版本为2.2.0，无需安装keras，博客地址对应**[https://blog.csdn.net/weixin_44791964/article/details/109161493](https://blog.csdn.net/weixin_44791964/article/details/109161493)。

**问：你的代码某某某版本的tensorflow和pytorch能用嘛？
答：最好按照我推荐的配置，配置教程也有！其它版本的我没有试过！可能出现问题但是一般问题不大。仅需要改少量代码即可。**

### b、30系列显卡环境配置
30系显卡由于框架更新不可使用上述环境配置教程。
当前我已经测试的可以用的30显卡配置如下：
**pytorch代码对应的pytorch版本为1.7.0，cuda为11.0，cudnn为8.0.5**。

**keras代码无法在win10下配置cuda11，在ubuntu下可以百度查询一下，配置tensorflow版本为1.15.4，keras版本是2.1.5或者2.3.1（少量函数接口不同，代码可能还需要少量调整。）**

**tf2代码对应的tensorflow版本为2.4.0，cuda为11.0，cudnn为8.0.5**。

### c、GPU利用问题与环境使用问题
**问：为什么我安装了tensorflow-gpu但是却没用利用GPU进行训练呢？
答：确认tensorflow-gpu已经装好，利用pip list查看tensorflow版本，然后查看任务管理器或者利用nvidia命令看看是否使用了gpu进行训练，任务管理器的话要看显存使用情况。**

**问：up主，我好像没有在用gpu进行训练啊，怎么看是不是用了GPU进行训练？
答：查看是否使用GPU进行训练一般使用NVIDIA在命令行的查看命令，如果要看任务管理器的话，请看性能部分GPU的显存是否利用，或者查看任务管理器的Cuda，而非Copy。**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201013234241524.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDc5MTk2NA==,size_16,color_FFFFFF,t_70#pic_center)

**问：up主，为什么我按照你的环境配置后还是不能使用？
答：请把你的GPU、CUDA、CUDNN、TF版本以及PYTORCH版本B站私聊告诉我。**

**问：出现如下错误**

#### 2）、预测时shape不匹配问题
**问：为什么我运行predict.py会提示我说shape不匹配呀。
在Pytorch里面是这样的：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200722171631901.png)
在Keras里面是这样的：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200722171523380.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDc5MTk2NA==,size_16,color_FFFFFF,t_70)
**答：原因主要有仨：
1、在ssd、FasterRCNN里面，可能是train.py里面的num_classes没改。
2、model_path没改。
3、classes_path没改。
请检查清楚了！确定自己所用的model_path和classes_path是对应的！训练的时候用到的num_classes或者classes_path也需要检查！**

### r、部署问题
我没有具体部署到手机等设备上过，所以很多部署问题我并不了解……

## 4、语义分割库问题汇总
### a、shape不匹配问题
#### 1）、训练时shape不匹配问题
**问：up主，为什么运行train.py会提示shape不匹配啊？
答：在keras环境中，因为你训练的种类和原始的种类不同，网络结构会变化，所以最尾部的shape会有少量不匹配。**

#### 2）、预测时shape不匹配问题
**问：为什么我运行predict.py会提示我说shape不匹配呀。
在Pytorch里面是这样的：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200722171631901.png)
在Keras里面是这样的：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200722171523380.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDc5MTk2NA==,size_16,color_FFFFFF,t_70)
**答：原因主要有二：
1、train.py里面的num_classes没改。
2、预测时num_classes没改。
请检查清楚！训练和预测的时候用到的num_classes都需要检查！**

### b、显存不足问题
**问：为什么我运行train.py下面的命令行闪的贼快，还提示OOM啥的？ 
答：这是在keras中出现的，爆显存了，可以改小batch_size。**
