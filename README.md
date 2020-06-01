# jav-standard-tool 简称javsdt

# longxiao作者为生活所迫，已经跑路...
# 这是我接手后重新修复的版本，仅保证javbus_youma、javbus_wuma正常运行，不定期修复

简介：收集jav元数据，并规范本地文件（夹）的格式，收集女优头像，为emby、kodi、jellyfin、极影派等影片管理软件铺路。

## 1、【其他开发者】运行环境：

python3.7.6 发行版是pyinstaller打包的exe  
pip install requests  
pip install Pillow  
pip install baidu-aip  
pip install pysocks  
pip install [cloudscraper](https://github.com/VeNoMouS/cloudscraper)  
几个jav的py都是独立执行的，加了很多很多注释，希望能理解其中踩过的坑。

## 2、工作流程：

    （1）用户选择文件夹，遍历路径下的所有文件。  
    （2）文件是jav，取车牌号，到javXXX网站搜索影片找到对应网页。  
    （3）获取网页源码找出“标题”“导演”“发行日期”等信息和DVD封面url。  
    （4）重命名影片文件。  
    （5）重命名文件夹或建立独立文件夹。  
    （6）保存信息写入nfo。   
    （7）下载封面url作fanart.jpg，裁剪右半边作poster.jpg。   
    （8）移动文件夹，完成归类。  

## 3、目标效果：

![image](https://github.com/javsdt/images/blob/master/jav/javsdt/readme/%E7%9B%AE%E6%A0%87%E6%95%88%E6%9E%9C1.png?raw=false)  
![image](https://github.com/javsdt/images/blob/master/jav/javsdt/readme/%E7%9B%AE%E6%A0%87%E6%95%88%E6%9E%9C2.png?raw=false)  
![image](https://github.com/javsdt/images/blob/master/jav/javsdt/readme/%E7%9B%AE%E6%A0%87%E6%95%88%E6%9E%9C3.jpg?raw=false)

## 4、ini中的用户设置：

![image](https://github.com/javsdt/images/blob/master/jav/javsdt/readme/ini%E8%AE%BE%E7%BD%AE.PNG?raw=false)

## 5、其他说明：

（1）不需要赞助；  
（2）允许对软件进行任何形式的转载；  
（3）代码及软件使用“MIT许可证”，他人可以修改代码、发布分支，允许闭源、商业化，但造成后果与本作者无关。

## 6、打包命令：

常用参数 含义
-i 或 -icon 生成icon
-F 创建一个绑定的可执行文件
-w 使用窗口，无控制台
-C 使用控制台，无窗口
-D 创建一个包含可执行文件的单文件夹包(默认情况下)
-n 文件名
-w test
pyinstaller -F -D -n JAVbUS有码.py

pyinstaller -F -n 【有码】javbus .\javbus_youma.py
pyinstaller -F -n 【无码】javbus .\javbus_wuma.py
pyinstaller -F -n 【ini】重新创建ini .\ini_create.py
