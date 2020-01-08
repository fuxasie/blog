---
title: "Python获取sms图床链接"
tags:
- 代码
- 文章

---

首先，需要的模块：
```python
import requests
import json#加载json模块
```
然后是源码：
```python
# 获取sms的图床链接
def getimgurl (imgurl):
    img=requests.get(imgurl).content#访问url图片网址，存字节型数据
    img= {'smfile': (imgurl, img)}#上传文件包格式
    img=requests.post("https://sm.ms/api/v2/upload/",files=img ).text#上传图片得到json
    img=json.loads(img)#json转为字典型数据
    try:
        return img["images"]
    except KeyError:
        try:
            return img["data"]["url"]
        except KeyError:#这个异常是为传入的图片网址不为空所导致到异常加的
            pass
```

