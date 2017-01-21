# taobao-php-sdk
[alidayu](https://api.alidayu.com/docs/api_list.htm?spm=a3142.7629065.4.3.tyeDs8&cid=20711) 

## Demo

```
<?php
header("Content-type: text/html; charset=utf-8");
include "TopSdk.php";
 
//将下载到的SDK里面的TopClient.php的$gatewayUrl的值改为沙箱地址:http://gw.api.tbsandbox.com/router/rest
//正式环境时需要将该地址设置为：http://gw.api.taobao.com/router/rest
 
$c = new TopClient;
$c->appkey = "test"; // 可替换为您的沙箱环境应用的AppKey
$c->secretKey = "test"; // 可替换为您的沙箱环境应用的AppSecret
$sessionkey= "test";  // 必须替换为沙箱账号授权得到的真实有效SessionKey
 
$req = new SellerItemGetRequest;
$req->setFields("num_iid,title,nick,price,approve_status,sku");
$req->setNumIid("123456789");
$rsp = $c->execute($req,$sessionkey);
 
echo "api result:";
print_r($rsp);
?>
```
