# think-qrcode
The ThinkPHP5.1 qrcode
二维码生成 SDK
## 安装

### 一、执行命令安装
```
composer require nanziok/think-qrcode
```

或者

### 二、require安装

##### thinkphp5.1 安装
```
"require": {
        "nanziok/think-qrcode":"2.*"
},
```

或者
###  三、autoload psr-4标准安装
```
   a) 进入vendor/nanziok目录 (没有dh2y目录 mkdir dh2y)
   b) git clone 
   c) 修改 git clone下来的项目名称为think-qrcode
   d) 添加下面配置
   "autoload": {
        "psr-4": {
            "nanziok\\qrcode\\": "vendor/nanziok/think-qrcode/src"
        }
    },
    e) php composer.phar update
```


## 使用
#### 添加配置文件
```
return [
    'cache_dir' => 'uploads'.DS.'qrcode',           //缓存地址
    'background'=> 'static/image/icon_cover.png'    //背景图
];
```

#### 使用方法
```
$code = new QRcode();
$code_path =  $code->png($register_url)         //生成二维码
    ->logo('static/image/avatar-m.jpg')         //生成logo二维码
    ->background(180,500)                       //给二维码加上背景
    ->text($role,20,['center',740],'#ff4351')   //添加文字水印
    ->text($nick_name,20,['center',780],'#000000')
    ->getPath();                                //获取二维码生成的地址

```

     


