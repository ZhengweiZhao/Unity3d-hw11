# 3D Game Programming & Design：AR/MR 技术

# AR/MR 技术概述

 - **增强现实（Argumented Reality (AR)）**

>是一种将真实世界信息和虚拟世界信息“无缝”集成的新技术，是把原本在现实世界的一定时间空间范围内很难体验到的实体信息(视觉信息,声音,味道,触觉等),通过电脑等科学技术，模拟仿真后再叠加，将虚拟的信息应用到真实世界，被人类感官所感知，从而达到超越现实的感官体验。

 - **混合现实(Mixed reality (MR))**

>有时被称为超现实（hybrid reality），是真实和虚拟世界的合并，产生新的可视化环境，物理和数字对象实时共存且在其中交互。混合现实不仅发生在物理世界或虚拟世界中，而是融合了现实和虚拟现实，通过身临其境的技术包含增强现实和增强虚拟。

 - **VR，AR，MR的区别**

	VR，玩家可以通过各种交互技术进入虚拟世界，与虚拟世界事物交互。

	AR，把虚拟世界的物体叠加在现实世界的影像或视频中的物体上，玩家在现实的背景上与虚拟世界物体互动。

	MR，将现实世界事物实时在虚拟世界中重构，这些现实物体、虚拟物体与玩家三者互动。

# 作业要求
1、 图片识别与建模

2、 虚拟按键小游戏
# 图片识别与建模
## Vuforia使用指南
首先打开 [Vuforia官网](https://developer.vuforia.com/)注册，然后在绑定的邮箱上确认一下，就可以回到vuforia主页上登录了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223163556716.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223163825723.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
然后进入Develop->License Manager页面，点击Get Development Key创建证书。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223163922943.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223164044105.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
然后点击进入TargetManager页面，创建数据库，选择默认的device类型。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223164152405.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)Vuforia要求将特定识别的目标提前上传至数据库进行特征提取。目标有多种类型，此处选择image，以对单幅图像进行识别，插入你选择的背景图片即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223182812816.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
下载目标特征数据并作为资源导入unity项目。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019122318285034.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
## 在Unity3d中建模并实现虚拟按钮
然后在unity3d中创建一个新项目。

选择Vuforia AR支持：Edit—>Project Settings—>Player—>XR Settings—>Vuforia AR Supported，会自动导入所需的包
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191223184543500.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
删除原本的main camera，然后在game object中添加vuforia engine的AR camera。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090619400.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
在他的inspector中选择open vuforia engine configuration，然后将licence拷贝进去。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090631723.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
拷贝licence（从vufoia中创建的licence点击复制即可）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090640724.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
inport在vuforia中创建的数据库中的target所导出的包文件。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090709627.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
创建一个Image Target，然后在他里面创建一个cube和virtual button，在virtual button下创建plane用于点击，最终结构如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090723180.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
在image target中导入设置好的数据库中的target
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090734367.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
cube只需要改大小和位置就可以了，设置如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090742355.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
然后对virtual button的设置也是调整位置和大小即可，注意需要让virtual button和plane位置重叠，且在背景图内。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090758867.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)
因为期末了没有太多时间所以这里我设计的游戏效果比较简单，就只是点击按钮cube就会换颜色，颜色设置成了红黄蓝三种，代码很简单，拖到image target就可以了。
```javascript
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using System;
using Vuforia;

public class NewBehaviourScript : MonoBehaviour, IVirtualButtonEventHandler
{
    public VirtualButtonBehaviour[] vbs;
    public GameObject cube;
    public GameObject button;
    public Color[] colors;
    public int index;

    void Start()
    {
        vbs = GetComponentsInChildren<VirtualButtonBehaviour>();
        for (int i = 0; i < vbs.Length; i++)
        {
            vbs[i].RegisterEventHandler(this);
        }
        colors = new Color[3];
        index = 0;

        colors[0] = Color.red;
        colors[1] = Color.yellow;
        colors[2] = Color.blue;
      
        cube = GameObject.Find("ImageTarget/Cube");
        button = GameObject.Find("ImageTarget/VirtualButton/Plane");
    }
    public void OnButtonPressed(VirtualButtonBehaviour vb)
    {
        button.GetComponent<Renderer>().material.color = Color.red;
        if (index == 3)
            index = 0;
        cube.GetComponent<Renderer>().material.color = colors[index++];
    }
    public void OnButtonReleased(VirtualButtonBehaviour vb)
    {
        button.GetComponent<Renderer>().material.color = Color.red;
    }
}

```
## 运行效果
点击运行，然后把手机中对应的背景图打开放在摄像头面前，就会出现cube和virtual button了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191225090917350.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MDM3NzY5MQ==,size_16,color_FFFFFF,t_70)





- 最后

[视频链接](https://pan.baidu.com/s/15SfoHrG5P1G93Pk3xaaZ6A)

