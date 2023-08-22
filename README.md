### 启动项目
```js
# 启动本地服务
hexo server 

# 生成静态文件
hexo -g

# 部署
hexo deploy

# 清除缓存文件 (db.json) 和已生成的静态文件 (public)。
hexo clean
```

选项	描述
-d, --deploy	文件生成后立即部署网站<br> 
-w, --watch	监视文件变动<br> 
-b, --bail	生成过程中如果发生任何未处理的异常则抛出异<br> 
-f, --force	强制重新生成文件<br> 
Hexo 引入了差分机制，如果 public 目录存在，那么 hexo g 只会重新生成改动的文件。
使用该参数的效果接近 hexo clean && hexo generate
-c, --concurrency	最大同时生成文件的数量，默认无限制