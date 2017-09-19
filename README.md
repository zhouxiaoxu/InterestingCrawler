# wexinFriendInfo

## 抓取QQ空间说说内容并进行分析

###爬虫文件

###QQZoneShuoshuo.py
- python版本：3.6
- 已经抓取到的信息有：

> 1. 所有说说信息
> 2. 每条说说的详细信息（比1中的信息更全面，1中数据只显示每条说说的前10个评论）  
> 3. 每条说说的点赞人列表

- 存储方式：

> 目前实现了两种存储方式:  
> 1. 存储到json文件中   
> 2. 存储到redis数据库中  
> 如果安装了redis，建议存储到redis中  
> 关于redis的安装和配置，请自行搜索  

- 运行环境：
  
> 建议使用PyCharm打开，  
> 在PyCharm中根据import的报错可以自动安装相应模块  
> selenium需要与chrome driver结合使用,可以查看这篇博客：  
> [selenium之 chromedriver与chrome版本映射表（更新至v2.32）](http://blog.csdn.net/huilan_same/article/details/51896672)

- 运行方式  

> 替换class spider中self.__username与self.__password为自己的QQ号密码
> 运行

### 数据分析
### drawWordCloud.py
- 注意：由于wordCloud这个库只支持python2，所以这个文件需要在python2 环境下运行
- 已经实现的分析有：

> 1. 平均每条说说的点赞人数  
> 2. 说说点赞的总人数
> 3. 点赞最多的人物排名和点赞数
> 4. 评论最多的人物排名和评论数
> 5. 所有说说的内容分析（分词使用的是jieba）
> 6. 所有评论的内容分析
- 运行结果：生成词云图
- 运行结果例图：

![Image](https://github.com/Maicius/wexinFriendInfo/blob/master/QQZone/final2.jpg)
![Image2](https://github.com/Maicius/wexinFriendInfo/blob/master/QQZone/comment.jpg)
![Image3](https://github.com/Maicius/wexinFriendInfo/blob/master/QQZone/comment_content.jpg)
![Image](https://github.com/Maicius/wexinFriendInfo/blob/master/QQZone/agree.jpg)

## 抓取微信好友信息
- 好友列表里所有好友，删除了公众号信息

### 爬虫文件
###  ReadWechatFrinedsInfo.py
- python版本： 3.6  
- 抓取到的信息格式如下：

>（用户名被加密过）   
{
"Uin": 0,  
"UserName": "@01535fb7d3f2626efda79395a24a281106c2094e987efb41b243337d9f4fbf46",  
"NickName": "HCG",  
"HeadImgUrl": "/cgi-bin/mmwebwx-bin/webwxgeticon?seq=659005699&username=@01535fb7d3f2626efda79395a24a281106c2094e987efb41b243337d9f4fbf46&skey=@crypt_731e3859_a77aa23f9d062c6d5c5fa3634412924a",  
"ContactFlag": 3,  
"MemberCount": 0,  
"MemberList": [],  
"RemarkName": "",  
"HideInputBarFlag": 0,  
"Sex": 1,  
"Signature": "",  
"VerifyFlag": 0,  
"OwnerUin": 0,  
"PYInitial": "HCG",  
"PYQuanPin": "HCG",  
"RemarkPYInitial": "",  
"RemarkPYQuanPin": "",  
"StarFriend": 0,  
"AppAccountFlag": 0,  
"Statues": 0,  
"AttrStatus":  36961,  
"Province": "广东",  
"City": "佛山",  
"Alias": "",  
"SnsFlag": 17,  
"UniFriend": 0,  
"DisplayName": "",  
"ChatRoomId": 0,  
"KeyWord": "",  
"EncryChatRoomId": "",  
"IsOwner": 0  
}

- 此外还下载了所有好友的头像

- 运行方式：

> 根据import 安装相应包，直接运行，扫二维码完成网页登录

