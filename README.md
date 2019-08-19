# sina_pics_downloader
## 已经过期，估计没法导出了2019.8
新浪相册导出小应用
2019年5月22日 zd200572  写评论
最近网易和新浪相继宣布停止相册服务，不得不说一个时代过去了，相册，已经成为曾经的大门户网站放弃的弃子，博客，也不会太远了。相比网易的相册同步软件可以实现一键下载，新浪竟然只给一个包含全部相册网址的xml文件，不得不说，真没有大公司风范，至少花一点时间来个脚本，让大家一键下载成zip吧，这对于相册有大几百张的人来说简直是一种煎熬，当然，稍微整理一下放在可以批量下载的软件里下载也不错，一张张保存就要崩溃了。于是，我决定做一个。虽然，估计需要的人是少数。

获取xml文件
打开http://control.blog.sina.com.cn/riaapi/photoblog/photo_down.html ，选择导出博客图片的链接，保存就得到一个xml文件。
比如我的，放几行在这：

<?xml version="1.0" encoding="UTF-8"?>
<PhotoList>
  <name_默认专辑>
    <pic_0>http://s7.sinaimg.cn/orignal/001mNzgy6V5HgLZkyd6&amp;690</pic_0>
先说说我的处理过程
我写了个python小脚本批量下载这些图片，基于python3的，代码放在这，很简单的几行。

python3代码
遇到了点墙，主要是python3和python2的区别导致的，经过搜索后解决了。ps.python3需要导入urllib.request并且用也这样用。


然后，下载cxfreeze，打包
pip install cx_Freeze
然后找到这个库的绝对路径，一般是Python安装路径下面的Scripts文件夹（比如：D:\Python34\Scripts），然后打开cmd/powershell来直接调用。

D:\Python34\Scripts\cxfreeze get_pics.py 
然后就生成的可用的程序，在dist文件夹可以找到get_pics.exe的可执行文件。

使用方法
下载地址：
我已经把脚本打包成了zip，下载下来解压后，将 博客相册图片列表.xml放入解压后的文件夹双击即可运行，默认6s下载一张图片，欢迎使用。
友情提醒，官方说明，相册导出功能开放到2019年7月31日24时，请及时进行内容导出。

还有另一个**替代选择**，另一大哥搞的小应用：http://t.cn/EK5qYzu
