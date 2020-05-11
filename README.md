# OneIndex-mod
Onedrive Directory Index mod

## 功能：
不占用服务器空间，不走服务器流量，  直接列出 OneDrive 目录，文件直链下载。  

## mod特点
1.采用最新down/oneindex,萌化默认主题
2.无需手动设置定时任务，后台每10分钟自动刷新
3.docker全自动搭建
4.新增导航栏+支持修改背景图

## 本站Demo
[https://cloud.baiyue.one](https://cloud.baiyue.one)  

## 安装运行

#### 必要条件：
OneDrive 账号 如需5T云盘，[点击传送门](https://mall.baiyue.one/product/11.html) 

## docker安装
首先安装docker【已安装的可跳过】

```
docker version > /dev/null || curl -fsSL get.docker.com | bash 
service docker restart 
systemctl enable docker  #设置开机自启
```
之后执行安装命令
```
docker run -d -p 8181:80 --restart=always baiyuetribe/oneindex
```
完成后输入http://ip:8181 按提示操作即可。如需域名访问，请参考结尾。

<img width="658" alt="image" src="https://raw.githubusercontent.com/donwa/oneindex/files/images/install.gif">  


最终效果：
![](https://ww1.sinaimg.cn/large/007i4MEmgy1g1h9f6wh8sj31gy0ps1kx.jpg)
## 特殊文件实现功能  
` README.md `、`HEAD.md` 、 `.password`特殊文件使用  

可以参考[https://github.com/donwa/oneindex/tree/files](https://github.com/donwa/oneindex/tree/files)  

**在文件夹底部添加说明:**  
>在 OneDrive 的文件夹中添加` README.md `文件，使用 Markdown 语法。  

**加密文件夹:**  
>在 OneDrive 的文件夹中添加`.password`文件，填入密码，密码不能为空。  

**直接输出网页:**  
>在 OneDrive 的文件夹中添加`index.html` 文件，程序会直接输出网页而不列目录。  
>配合 文件展示设置-直接输出 效果更佳。  


**上传文件:**  

推荐使用系统自带的OneDrive程序客户端或者使用RaiDrive进行文件的修改、上传、删除操作。

## 域名访问
**方法一：宝塔反代**
先进入宝塔面板，点击左侧网站，添加站点，完成后进入网站设置，点击反向代理，目标`URL`填入`http://127.0.0.1:代理端口`（*代理端口*就是docker应用的外接接口），再启用反向代理即可。如果想启用`SSL` ，就直接在站点配置即可。

![](https://ww1.sinaimg.cn/large/007i4MEmgy1g04u3wlh5oj30kx0htaci.jpg)

**方法二：caddy反代（没有宝塔时的策略）**

设置较为麻烦，请参考：https://www.moerats.com/archives/422/

**文章来源** ：[佰阅部落](https://baiyue.one/archives/457.html)