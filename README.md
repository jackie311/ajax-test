# Ajax

### `Create Object`

    var request;
    if (window.XMLHttpRequest) { 
      request = new XMLHttpRequest(); 
    } else {</br>
      request = new ActiveXObject('Microsoft.XMLHTTP');
    }


### `Send Request`

    request.open(method, url, async);
    reqeust.send(string);
    
#### Example:

    request.open('GET','get.php');
    request.send();
    
    request.open('POST','post.php');
    request.send();
    
    request.open('POST', 'create.php', true);
    request.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
    request.send('name=James&gender=male');
    
### `Response`
    
    request.responseText: 获得字符串格式的相应数据
    request.status: 以数字形式返回HTTP状态码
    request.statusText: 以文本形式返回HTTP状态码
    request.getAllResponseHeader(): 获取响应包头
    request.getResponseHeader() 查询包头参数
    
    request.readyState
      0: 请求未初始化， open()还没有被调用
      1：服务器链接， open()已经被调用
      2：请求接收， 也就是已经接受到头部信息
      3：请求处理， 接收到响应文本体
      4：请求响应完成
      
#### Example
     request.onreadystatechange = function() {
      if (request.readyState === 4 && request.status === 200) {
        //doing something here
      }
     }
