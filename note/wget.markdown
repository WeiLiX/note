wget下载站点网页  
参考来源:[http://huagelinux.blog.163.com/blog/static/87337083201002063743210/](http://huagelinux.blog.163.com/blog/static/87337083201002063743210/)

2010-01-20 18:37:43|  分类： 必杀技 |字号 订阅
参数：

-r：递归下载，不要单独下载，否则会把所有链接都下下来，包括网站上链接的其他站点；

-p：下载网页显示所需的所有元素，例如图片；

-np：不下载别的站点；

-k：把网页中的链接改为本地链接，这样可方便本地阅读。

       比如我想下载gentoo网站上的英文文档，可输入如下命令：
wget -r -p -np -k http://www.gentoo.org/doc/en/。
-c,  --continue                断点续传下载文件。
 -x,  --force-directories        强制创建目录。
  -A,  --accept=LIST               逗号分隔的可接受的扩展名列表。
