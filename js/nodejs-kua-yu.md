---
description: Access-Control-Allow-Origin
---

# Nodejs跨域

### 1、代码控制跨域访问

```text
//设置跨域访问  
app.all('*', function(req, res, next) {  
    res.header("Access-Control-Allow-Origin", "*");  
    res.header("Access-Control-Allow-Headers", "X-Requested-With");  
    res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS");  
    res.header("X-Powered-By",' 3.2.1')  
    res.header("Content-Type", "application/json;charset=utf-8");  
    next();  
}); 
```

### 2、使用cors模块来解决跨域

```text
npm install  cores
```

在app.js中，设置相关属性

```text
var cors = require('cors');
app.use(cors({
    origin:['http://localhost:3000'],
    methods:['GET','POST'],
    alloweHeaders:['Conten-Type', 'Authorization']
}));
```

