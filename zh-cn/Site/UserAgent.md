### 常用User Agent检测

微信：含有`MicroMessenger`

QQ：含有`QQ/`

支付宝：含有`AlipayClient`

### 代码实现

JS代码
```javascript
var ua = window.navigator.userAgent;
/(?:MicroMessenger)/.test(ua);
```

PHP代码
```php
$ua = $_SERVER['HTTP_USER_AGENT'];
strpos($ua, 'MicroMessenger');
```
