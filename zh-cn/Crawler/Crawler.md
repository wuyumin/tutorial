### 爬取

- 常用 Header 头
  * Host:一般是当前爬取的域名
  * Referer:
  * User-Agent:随机取User-Agent
- 设置代理IP
- 并发执行
- 超时处理

### curl使用代理

curl命令行  
`curl --proxy 127.0.0.1:8888 https://httpbin.org/ip` 默认http协议  
`curl --proxy http://127.0.0.1:8888 https://httpbin.org/ip` http协议  
`curl --proxy https://127.0.0.1:8888 https://httpbin.org/ip` https协议，有些windows系统暂不支持  
`curl --proxy socks5://127.0.0.1:1080 https://httpbin.org/ip` socks5协议  

PHP cURL  
`curl_setopt($ch, CURLOPT_PROXY, '127.0.0.1:8888');`