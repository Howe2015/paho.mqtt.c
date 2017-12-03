readme
====================
一、功能
---------------------
	
> 向服务器(Server)的某一主题(Topic)推送(Pub)一个信息(Payload)</br>
>服务器ip：wuhaotao.cn</br>
>服务器端口:1883</br>
>Topic:test</br>
>Payload: Hello World!
二、步骤
----------------------
#1.编译dll文件
>进入 paho.mqtt.c\Windows Build 目录，通过vs2017打开解决方案，右键所需工程，进行生成；
#2.新建工程
>将1.中生成的dll文件放入工程目录，同时将 paho.mqtt.c\src 目录下的.h文件复制进工程目录；
>修改main文件，加入以下代码；

    /* C++调用C生成的dll库需要以下代码 */
    extern "C" {
    #include "include\MQTTClient.h"
    #include "include\MQTTClientPersistence.h"
    #include "include\MQTTAsync.h"
    #include "include\OsWrapper.h"
    }
	/* 静态加载库 */
    #pragma comment(lib,"paho-mqtt3a.lib")
>将lib等文件的目录加入到项目属性中
>![](https://i.imgur.com/kASzZN9.jpg)
#3.编译工程
>如果不出意外，应该不会编译出错。