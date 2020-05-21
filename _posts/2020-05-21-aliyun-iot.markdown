---
layout: post
title: MQTT数据上传到阿里云IOT平台无法显示问题
date: 2020-05-21T14:37:44.000Z
categories: update
---
<img src="/images/fulls/ali.jpg" class="fit image">
首先，发送的消息需要时JSON格式，且需要转换成二进制
其次，需要payload里面一定要使用post方法，我用update方法不成功不知道为什么。
第三，需要在设配管理-》平台-》功能定义-》自定义里面添加标识等信息

```json
payload格式
{
  "id": 123243,
  "params": {
    "temperature": 25.6,
    "humidity": 60.3,
    "ch2o": 0.048
  },
  "method": "thing.event.property.post"
}
message = '{"id": 123243,"params": {"Temp": 27.6},"method": "thing.event.property.post"}'.encode('utf-8')
```