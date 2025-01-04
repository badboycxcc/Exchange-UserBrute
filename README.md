# Exchange-UserBrute
Exchange  用户名爆破

## 使用方法
**参数**
```
Usage of ./ExchangeUserBrute-linux-arm64:
  -b int
        爆破类型, 1 延时爆破 2 Cookie爆破  (default 1)
  -email string
        邮箱后缀, Cookie爆破必要参数
  -name string
        用户名
  -t int
        线程数 (default 5)
  -u string
        目标URL
  -uf string
        用户名列表文件
```



**单个验证**
```
ExchangeUserBrute -u https://main.test.com -name Administrator
```
<img width="882" alt="截屏2024-09-21 上午10 08 08" src="https://github.com/user-attachments/assets/e682ca54-3366-4360-8256-530528f29b85">


**批量验证**
```
ExchangeUserBrute -u https://main.test.com -uf user.txt 
```
<img width="799" alt="截屏2024-09-21 上午10 04 25" src="https://github.com/user-attachments/assets/1e193f4c-79df-4d35-af7b-66f5edd1e4a2">

**Cookie爆破方法批量验证，速度更快**
```
ExchangeUserBrute -u https://main.test.com -uf user.txt -b 2 -email test.com 
```

> 方法参考
![image](https://github.com/user-attachments/assets/df361729-32fd-4532-8b48-bc21b8e8cb8a)


**延时爆破与Cookie爆破优缺点**  
```
延时爆破
	- 速度较慢
	- 准确率不高
	- 验证域用户

Cookie 爆破
	- 速度更快
	- 准确度更高
	- 只能验证邮箱
```

延时爆破和Cookie 爆破结果不一致 
```
延时爆破验证的是域用户，但部署每个域用户都会开启邮箱账号。
```


## 更新日志
```
2025-01-04 v1.1 T00ls 专版
	[+] 设置终端测色输出
	[+] 增加邮箱验证方法，速度更快。
	
2024-07-30 v1.0
	[u] 第一步版本
```

## 原理及参考项目
- https://github.com/rapid7/metasploit-framework/blob/master/modules/auxiliary/scanner/msmail/onprem_enum.go
