### Ajax 全局事件

```javascript
<script>
// Ajax 全局事件
$(document).ajaxStart(function(){
    alert('request start!');
})
.ajaxError(function(){
    alert('response error!');
})
.ajaxComplete(function(){
    alert('request complete!');
});
</script>
```

### 针对单个请求

**老版本**
```javascript
<script>
$.ajax({
    url: 'start.json',
    type: 'POST',
    data: {
        CategoryId: CategoryId
    },
    dataType: 'json',
    beforeSend: function(){
        alert('request start!');
    },
    success: function(data){
        alert('response success!');
    },
    error: function(){
        alert('response error!');
    },
    complete: function(){
        alert('request complete!');
    }
});
</script>
```

**新版本**  
从 jQuery 1.5 开始  
.fail()方法取代了的过时的.error()方法  
.done()方法取代了过时的.success()方法  
.always()方法代替了过时的.complete()方法  
```javascript
<script>
$.ajax({
url: 'start.json',
type: 'GET'
})
.done(function(data){
    alert(data.app.summary);
})
.fail(function(error){
    alert('请求失败了！');
});
</script>
```
