---
title: BroadcastChannel 实现浏览器tab无刷新通讯
date: 2023-08-22 10:11:55
categories: [前端, js]
---

## 前提须知
1. 使用	`BroadcastChannel` 来实现浏览器tab通讯必须是同源的
2. BroadcastChannel 支持多tab间通讯
3. mdn [链接](https://developer.mozilla.org/zh-CN/docs/Web/API/BroadcastChannel)

## 具体使用
1. 发送方使用
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <div>
    <button style="all: unset" onclick="onSend()">发送</button>
  </div>
  <script>
    /**
     * BroadcastChannel 
     * 接收方和发送发必须是同源的才行进行浏览器tab的通讯
     * 
    */
    const broadcast = new BroadcastChannel('music')
    
    broadcast.onmessage = (e) => {
      console.log(e)
    }
    function onSend() {
      console.log('点击了');
      broadcast.postMessage({
        name: 'music',
        data: '发送的数据'
      })
    }
  </script>
</body>
</html>
```

2. 接收方
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <script>
    const broadcast = new BroadcastChannel('music')
    broadcast.onmessage = ({data}) => {
      console.log('music接受数据了', data)
    }
  </script>
</body>
</html>
```
