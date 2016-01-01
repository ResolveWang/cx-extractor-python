
#网页正文抽取工具
##1. 用途
  本工具用于抽取网页中的正文，常见的网页通常分为两种。第一种是类似于门户网站的首页，这种网页是导航页面，有很多的超链接和文章标题，这种网页本身并没有实质内容，因此这里不考虑这种网页。第二种是有实质性内容的网页，例如新闻的页面，这里实现的效果就是对网页进行处理，剔除其中的html标签、超链接、脚本代码等内容，抽取出网页的正文。
##2. 原理
##3. 接口及其使用方法
使用时导入cx_extractor_python类，并且新建cx_extractor_python类的对象。获取html页面的方式有两种，第一种是从url中获取网页，使用getHtml方法；第二种是从已经有的网页文件中读取网页，使用readHtml方法。读取网页之后，调用filter_tags方法对网页进行预处理，这个方法可以剔除网页中的html标签和js脚本等。网页预处理之后，调用getText方法就可以得到网页的正文。示例代码如下所示：

```
from crawler.cx_extractor_Python import  cx_extractor_Python
cx = cx_extractor_Python()
# test_html = cx.readHtml("E:\\Documents\\123.html")
test_html = cx.getHtml('http://news.163.com/16/0101/10/BC84MRHS00014AED.html')
content = cx.filter_tags(test_html)
s = cx.getText(content)
print(s)
```
##4. 测试结果
