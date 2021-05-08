# Matebook-x-pro-2019-Hackintosh-newest 黑苹果

  
readme in other language：  
[中文🇨🇳](https://github.com/ske1996/Matebook-x-pro-2019-Hackintosh-newest) | [English🇬🇧](readme-en.md)   
     

**在华为的MateBook系列笔记本上做到基本完美的稳定运行MacOS**     
  

```diff
A newest Hackintosh build works for 2019 version of Matebook x pro
```  

**⭐️如果你不会安装，需要安装服务，可以解决PM981问题** [点击进入我的淘宝店铺](https://item.taobao.com/item.htm?spm=a2oq0.12575281.0.0.45e51debf0yJ4n&ft=t&id=638314994173)  



姐妹项目:  
[MateBook 13/14 OpenCore 黑苹果](https://github.com/ske1996/matebook-13-2019-oc-efi)  
[Matebook-D14/D15-2020-OpenCore 黑苹果 hackintosh  ](https://github.com/ske1996/Matebook-D14-2020-hackintosh)  
  

如果你遇到了什么问题（与安装无关的），有可能在这里找到答案：[issues](https://github.com/ske1996/matebook-13-2019-oc-efi/issues)  

我没有这个设备，有些小伙伴帮我测试了这个，如果你遇到了什么问题欢迎留下issue  

**请在这个网页的最右上角帮我点颗小星星⭐️哟**  

## 更新日志（⚠️一定先看这个）  
<details>  
<summary>点击以查看详细信息</summary>  
  

- 20210508:  
oc版本为0.6.5，微调缓冲帧以及boot-args，尝试优化drm以及sidecar问题。    

- 20210503:  
oc版本为0.6.5，efi不区分Catalina和BigSur   


</details>


## 正常可用的部件：
  
**以下的【蓝牙】【WIFI】【HDMI】的文字可点击后查看详情**  

 
 
<details>  
<summary>1.蓝牙</summary>   
  
驱动作者[@zxystd](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)  
1. 华为的蓝牙鼠标不可用！！！  
2. 苹果的妙控2可用   
3. 亲眼所见，微软设计师鼠标可用[淘宝链接](https://detail.tmall.com/item.htm?id=575557854943&spm=a1z09.2.0.0.119c2e8dUqx3iI&_u=bkg3nm2911&sku_properties=5919063:6536025)  
4. 亲眼所见，型号为thinkpad 0a36193（SMB）的蓝牙鼠标可用，购买选“蓝牙无线激光”，[京东链接-移动端](https://item.m.jd.com/product/748175.html?utm_campaign=t_1001328990)  
5. Airpods可以用，但是你得配对一次，我们又不是白苹果，不能开盖就用  
6. 以下几个蓝牙鼠标根据群友测试说可用，但是我没亲眼所见，要是买了发现不能用别怪我  
----雷柏m200g/刺鳞树蝰/罗技m336/微软sculpt/英菲克/飞利浦spk7355  

</details>   

  
<details>  
<summary>2.WIFI</summary>  
  
1. 使用了Z大的最新AirportItlwm的wifi驱动，跟heliport说拜拜啦  


2. 驱动作者[@zxystd](https://github.com/OpenIntelWireless/itlwm)  

3. Airdrop和无线的随航不可用，随航需要插线用，handoff可用但有时不太稳定，可以用apple watch解锁mac，但是有时不稳定  
4. Wi-Fi觉得不好使的去上面我写出来的作者的repo里更新驱动
5. Wi-Fi连接要尽可能的去连5ghz的
6. 从Windows切换过来MacOS发现wifi没法用就关机，10s后再开机

</details>   

3.睡眠正常

4.HDMI    
     
5.触摸板正常

6.电源管理

7.核显

8.CPU变频

9.USB定制

10.键盘快捷键正常  

11.声卡扬声器正常  
  
## 无法正常工作的部件：  

   

1. 独显

2. 指纹  

3. 电池的显示似乎有些问题。 
 

## 有关安装：  



⚠️事前准备：f2进bios，调成中文，然后关闭一切带有“安全”的东西，保存，退出  

[![Download](https://img.shields.io/badge/OpenCore%20EFI-下载-blue)](https://github.com/ske1996/Matebook-x-pro-2019-Hackintosh-newest/releases)  

镜像下载链接：https://blog.daliansky.net/  

OC官方教程:https://dortania.github.io/OpenCore-Install-Guide/  
  


**⭐️如果你不会安装，需要安装服务，** [点击进入我的淘宝店铺](https://item.taobao.com/item.htm?spm=a2oq0.12575281.0.0.45e51debf0yJ4n&ft=t&id=638314994173)  




## 安装后：  

**以下的文字可点击后查看详情**  


<details>  
<summary>⚠️注意事项</summary>  
⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️  
  
1. 不要用oc引导windows，因为你弄不好你的正版软件许可证就全没了  
直接oc的选择系统界面里通过ctrl+回车选择mac的引导磁盘  
设置mac为默认引导磁盘，关闭config里的showpicker  
引导windows的话在windows下用easyuefi在原生的uefi bootloader中创建一个windows boot manager的入口，这个操作在上面贴出来的视频教程里有  
然后开机后按f12选windows即可  
我在[这个issue](https://github.com/ske1996/matebook-13-2019-oc-efi/issues/87)里写明了为什么  
oc的图形化os选择页面无用的理由也同上  
因为你不用oc去引导windows并且直接省略选择页面，所以图形化的oc界面也就没用  



2. 一定要先改三码再用，具体的教程自己百度  

3. icloud中的查找我的mac不要打开  

4. 安全与隐私中的文件保险箱不要打开  

5. 再任何系统，任何OS下都要杜绝热启动，意思是重启的话一律先选关机再用开机键开机  
无论是单个系统下的重启需求或者是想要重启切换系统，都不要选重启选项，一律先选关机再用开机键开机  
不然有可能会导致蓝牙，触控板，Wi-Fi失灵问题。  

6. 如果你出现睡眠无法唤醒or唤醒黑屏问题，参考：[#108issue](https://github.com/ske1996/matebook-13-2019-oc-efi/issues/108)  


</details>  

<details>  
<summary>开启安装所有来源的应用（为了运行一些必要的脚本以及一些“你懂得”软件）</summary>   
·······················································  
  
在【终端】中输入以下内容回车并输密码（密码不明文显示）  

```
sudo spctl --master-disable
```

</details>  

<details>  
<summary>安装ComboJack实现耳机耳麦切换，改进电流声。（修复耳机接口）</summary>   
  
参考： 

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/audiojack.png?raw=true)



在这里下载由Heporis制作的ComboJack.

https://github.com/randomprofilename/ComboJack


终端运行下面路径的脚本
```bash
ComboJack_Installer/install.sh
```
  
</details>

  
  
  
  
<details>  
<summary>解锁CFG</summary>  

⚠️关于解锁cfg后能做到什么？  
完美的电源管理  
CPU完美变频  
完美睡眠（我个人经验：睡眠6H只掉了1%的电）  

⚠️如因以下教程修改导致的一切后果，本人不予承担责任，下载本repo中任何一个文件视为同意以上条款  


以下教程来自：  
https://zhuanlan.zhihu.com/p/121655468

先去华为官网升级bios至1.28

然后找偏移地址就不用做了，我告诉你，就是0x3E  

【⚠️千万不要用oc去引导ru！！】懂得人自然懂，收起那个想法，老老实实按我下面写的来  

如因以下教程修改导致的一切后果，本人不予承担责任，下载本repo中任何一个文件视为同意以上条款  

- U盘准备阶段：  
（大小无所谓）  

1.先准备一个u盘，格式化为fat32  
2.u盘里创建文件夹：EFI  
3.打开EFI文件夹，在里面创建文件夹BOOT  
4.复制[cfgunlock.zip(点击下载)](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/cfgunlock.zip)里面的bootx64.efi进U盘的EFI/BOOT下  
5.关机后开机按F12使用这个U盘去引导，然后进入修改bios底层阶段  

- 以下为修改bios底层阶段：  
1. 进入后 ‘alt’ + ’=‘ 切换进 ACPI Variable  
2. 用pageup/pagedown/上下方向键找到 CPUSetup  
3. 回车进入然后用上下左右方向键找到对应的地址（也就是0x3e，那么就是纵坐标03，横坐标0e的位置）  
![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/RU.jpg?raw=true)  
4. 一看，确实是0x01，那么回车，输入0 就可以看到它变成了0  
5. 使用'crtl' + 'w' 来保存 保存的时候屏幕上会直接显示update written 的，这说明已经写入了  
6. 使用'alt' + 'q' 来退出，然后即可回到引导进入系统了，CFG已经解锁  

修改完成后可以再用那个u盘引导启动一次，查看是否修改成功  

</details> 


<details>  
<summary>修改dvmt至64mb</summary>  
    
  ⚠️关于修改dvmt后能做到什么？  
  可以hdmi/dp输出4k60p的信号了  
  
  

⚠️如因以下教程修改导致的一切后果，本人不予承担责任，下载本repo中任何一个文件视为同意以上条款  
- U盘准备阶段：  
（大小无所谓）  

1.先准备一个u盘，格式化为fat32  
2.u盘里创建文件夹：EFI  
3.打开EFI文件夹，在里面创建文件夹BOOT  
4.复制[cfgunlock.zip(点击下载)](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/cfgunlock.zip)里面的bootx64.efi进U盘的EFI/BOOT下  
5.关机后开机按F12使用这个U盘去引导，然后进入修改bios底层阶段  

- 以下为修改bios底层阶段：  
1. 进入后 ‘alt’ + ’=‘ 切换进 ACPI Variable  
2. 用pageup/pagedown/上下方向键找到 SaSetup  
3. 进入SaSetup后，然后用crtl加pagedown翻到下一页找到左侧横坐标0100，如下图所示，注意左侧横坐标第一项就是0100  
![image](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/%E6%9D%82%E9%A1%B9/dvmt64.bmp)  
4. 横坐标0100纵坐标07改成02，横坐标0100纵坐标08改成03（就是我圈出来的位置修改的跟上图一样就行了）  
5. Crtl加w保存就行了  


修改完成后可以再用那个u盘引导启动一次，查看是否修改成功  

最后记得用[propertree](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/ProperTree.zip)去修改一下config，移除里面缓冲帧的“framebuffer-fbmem”，“framebuffer-stolenmem”，“framebuffer-unifiedmem”这三个条目。  
  
  
[本教程灵感来源@laozhiang](https://github.com/laozhiang)  
  


</details>   

      

<details>  
<summary>解决window与macos时间不同步/显示不正确</summary>  
  
  
  
在windows下面WIN+x 选择管理员模式进入CMD  
  
  执行以下命令：  
  
```bash
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```  
</details>   
  
   

<details>  
<summary>关于如何在黑苹果下玩游戏（打破平台/硬件限制，黑苹果也能玩所有PC游戏）</summary>  
    
  
  
  
 ⚠️在注册的时候填写邀请码：DBZNT3EC  
！！可以白嫖3小时！！
  
       
      
我自己用的一个云电脑服务  
挺好用的能玩游戏（包括3A） 
也就是说在matebook的黑苹果上也可以无硬件限制的玩任何游戏了  
直接4K全画质的开  
没啥延迟，就跟在本地玩一样  
我自己用的，推荐使用这个，这样在mac玩游戏也解决了  
  
⚠️在注册的时候填写邀请码：DBZNT3EC  
！！可以白嫖3小时！！
  
  
  
[点击进入它的官网](https://www.haixingcloud.com/#/Home)  
  


</details>   


<details>  
<summary>关于我认为的一些可以给你更好体验的软件</summary>  
  
  
  
1. Mos：保证鼠标的顺畅滑动，以及滚轮方向的调整 官网：[https://mos.caldis.me/](https://mos.caldis.me/)  
2. Rectangle:还给你windows的拖动分屏逻辑 官网：[https://rectangleapp.com/](https://rectangleapp.com/)  
3. Stats：状态栏监控插件 主页：[https://github.com/exelban/stats](https://github.com/exelban/stats)  
4. Keka：强大好用的压缩软件 官网：[https://www.keka.io/en/](https://www.keka.io/en/)  
5. IINA：万能播放器 官网：[https://iina.io/](https://iina.io/)  
6. Motrix：万能下载器 官网：[https://motrix.app/](https://motrix.app/)  
7. Hackintool：黑苹果的瑞士军刀 主页：[https://github.com/headkaze/Hackintool](https://github.com/headkaze/Hackintool)  
8. Propertree：我最推荐的config编辑软件 主页：[https://github.com/corpnewt/ProperTree](https://github.com/corpnewt/ProperTree)  
9. Wormhole：mac上的huawei share,治好了我的颈椎病，上班狗的福音 官网：[https://er.run/](https://er.run/)  
10. 超级右键：恢复windows的右键新建txt，新建word/excel等操作 官网:[https://www.better365.cn/](https://www.better365.cn/)  


</details>  

## 如果想打赏小的，请选择一个你喜欢的方式打赏五块钱，谢谢！
  
  ⭐️打赏附言请留下自己的github的ID，用于公示感谢  
  

  
[看不到图片请点击](http://m.qpic.cn/psc?/V51Uqo3Z3KmDDj0bhEZH0ySaLy25K537/ruAMsa53pVQWN7FLK88i5vhyua0NyktT47EDwPAfhtuBceWLK5.5V40I*6lQE5rORR7qbWTf9Eovur4ifsHKECewZxvEqi.ZfhaQ4ObpAl8!/b&bo=DQWcAw0FnAMBCS4!&rf=viewer_4)  



![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/payment.jpeg?raw=true)  



  
[看不到图片请点击](http://m.qpic.cn/psc?/V51Uqo3Z3KmDDj0bhEZH0ySaLy25K537/ruAMsa53pVQWN7FLK88i5vhyua0NyktT47EDwPAfhtuBceWLK5.5V40I*6lQE5rORR7qbWTf9Eovur4ifsHKECewZxvEqi.ZfhaQ4ObpAl8!/b&bo=DQWcAw0FnAMBCS4!&rf=viewer_4)  

    
    
  
 

## 协议：  
本repo采用MIT License，允许个人使用为目的的更改，但是如果你根据本项目的任何文件制作并公开了其他发行版，需提前联系并取得我的同意，本repo的任何文件禁止任何商业目的以及任何以获取利润为目的的使用，本人拥有以采取法律行动进行维权的一切权利。  



## 感谢：

- [@intel](https://www.intel.com/content/www/us/en/homepage.html) 感谢10年一管牙膏（AMD,YES!）

- [@apple](https://www.apple.com/) 感谢创造出macos

- [@zxystd](https://github.com/OpenIntelWireless/itlwm) 感谢创造出wifi以及蓝牙的驱动

- [@cnpog](https://github.com/cnpog/Matebook-X-Pro-2019) 修改自这个项目，他列举的问题都解决了 

- [@Zero-zer0](https://github.com/Zero-zer0) 参考了他的热键修复方法 十分感谢

