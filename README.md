# axios
axios学习

### ajax库
jquery ajax库
```js
  $.ajax({
    success(data) {
      // data 标识服务器端响应的数据
    }
  })
```
1. 特点：
   1. 异步请求
   2. 接收数据采用回调函数的方式
2. 弊端：
   1. jquery库庞大，占用内存资源多
   2. 多个异步请求有可能产生回调地狱的问题

### axios库
1. 特点
   1. 既能运行在nodejs环境中，又能在浏览器端室友
   2. 基于promise的网络请求库，能够解决回调地狱的问题
   3. axios可以集成在 vue一级react等框架中室友
   4. 内存占用较小

### json-server
#### 数据模拟服务器，通过 json-server 提供json数据
   使用json-server
   ```js
    // 1. 全局安装
    npm install json-server

    // 2. 创建db.json文件
    {
      "posts": [
        {
          "id": 1,
          "title": "json-server",
          "author": "typicode"
        }
      ],
      "comments": [
        {
          "id": 1,
          "body": "some comment",
          "postId": 1
        }
      ],
      "profile": {
        "name": "typicode"
      }
    }

    // 3. 启动json-server
    // npx json-server data.json文件
    npx json-server data.json

    // 4. 启动后，访问到json数据 http://localhost:3000/posts

    
   ```
#### 改变端口号
  修改默认的端口号，改为指定端口号
  `npx json-server data.json --port 1314`
  访问到json数据 http://localhost:1314/posts

#### json-server 的特点
  1. json-server 支持restful 风格的api
    所谓的 restful 风格就是 通过不同的请求方式，对数据进行增上改查等不同的操作
    
    get：表示检索
      ```js
        检索全部数据：http://localhost:1314/stus
        通过id检索一条数据：http://localhost:1314/stus/1001
        通过条件检索多条数据：http://localhost:1314/stus?age=20
      ```
    post：表示新增操作
    ```js
    ```
    delete：删除操作
    put 请求：修改操作
      字段重组，只保留请求发送的字段 请求没有发送的字段，会删除
    patch 请求：修改操作
      只修改请求的字段，没有请求的字段，会保留不会修改
    
  2. 2
