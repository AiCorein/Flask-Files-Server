# Flask-Files-Server
## 一、简介
&emsp;&emsp;基于原生前端和 Python Flask 后端的文件服务器，可远程访问、下载和上传文件，可用于某一设备向其他设备开放的文件访问。局域网搭配内网穿透可实现公网访问。<br>
&emsp;&emsp;（2023.04.09 更新：本项目仅推荐在 windows 环境下使用。读取硬盘分区的代码不是跨平台的，在其他系统可能出现未知问题。另外，本项目我没有继续更新的意愿，但如果你遇到了 bug 或者提交 pull requests，我会第一时间响应）


## 二、说明
&emsp;&emsp;最开始是想着，实现电脑不在身边的时候直接访问、操作电脑文件。等到做完了才想起来用 ftp 协议配置也更方便，也更稳定；但既然都做完了(；′⌒`)...也就权当一个练手项目吧。<br>
&emsp;&emsp;使用 http 实现确实麻烦了，但正好也能用最近学的前端知识做一做交互界面。使用 Windows 自带的 ftp 服务或网上的其他 ftp 客户端 UI 也就那样，自己从零设计 ftp 服务客户端又太麻烦了，选择前端 http 实现正好可以满足 UI 这个需求。<br>
&emsp;&emsp;同时不同设备访问只需要浏览器就可以了。~~当然移动端体验可能不太好，因为我没做移动端网页（懒），但是用还是能用的...~~ （2021.09.15 更新：增加了移动端适配，移动端使用体验大幅提升）

## 三、功能
&emsp;&emsp;（1）~~炫酷、人性化使用界面，赏心悦目（划掉）~~<br><br>
&emsp;&emsp;（2）类似 ftp 服务的文件访问、下载和上传功能，没有删除（没这个需求）

## 四、使用
&emsp;&emsp;（1）安装依赖：
```cmd
pip install flask
```
&emsp;&emsp;（2）[app.py](https://github.com/AiCorein/Flask-Files-Server/blob/main/app.py) 中设置 SECRET_KEY 值,关于该值 flask 官方的说明：
>&emsp;&emsp;SECRET_KEY 配置变量是通用密钥，可在 Flask 和多个第三方扩展中使用，如其名所示，加密的强度取决于变量值的随机密度。<br>
>&emsp;&emsp;不同的程序要使用不同的密钥，而且要保证其他人不知道你所用的字符串，其主要作用应该是在各种加密过程中加盐以增加安全性。在实际应用中最好将这个参数存储为系统环境变量。

&emsp;&emsp;&emsp;&emsp;建议通过随机方法获取值，采用系统变量方式存储，然后使用 `os.getenv('SECRET_KEY')` 读取<br><br>
&emsp;&emsp;（3）定义登录用户名和密码：给 [app.py](https://github.com/AiCorein/Flask-Files-Server/blob/main/app.py) 中的 `SPECIFY_UNAME` `SPECIFY_UPWD` 常量赋值<br><br>
&emsp;&emsp;（4）运行 [app.py](https://github.com/AiCorein/Flask-Files-Server/blob/main/app.py)

## 五、演示
[点击前往演示视频](https://www.bilibili.com/video/BV15K4y1g7Yo?share_source=copy_web)
