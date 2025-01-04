# Exchange-UserBrute
Exchange  用户名爆破

## 使用方法  
![image](./截屏2025-01-04%20下午12.24.02.png)  
 
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



**延时爆破方法：验证单个域用户**
```
ExchangeUserBrute -u https://main.test.com -name Administrator
```
![image](./截屏2025-01-04%20下午12.26.12.png)    



**延时爆破方法：批量验证域用户**
```
ExchangeUserBrute -u https://main.test.com -uf user.txt 
```
![image](./截屏2025-01-04%20下午12.25.06.png)      


**Cookie 爆破方法：验证单个邮箱**
```
ExchangeUserBrute -u https://main.test.com -name Administrator -b 2 -email test.com 
```
![image](./截屏2025-01-04%20下午12.26.39.png)     


**Cookie 爆破方法：批量验证邮箱**
```
ExchangeUserBrute -u https://main.test.com -uf user.txt  -b 2 -email test.com 
```
![image](./截屏2025-01-04%20下午12.27.25.png)     


> Cookie 爆破方法参考

![image](https://github.com/user-attachments/assets/df361729-32fd-4532-8b48-bc21b8e8cb8a)


**延时爆破与Cookie 爆破优缺点**    
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


**延时爆破与Cookie 爆破时间对比**
延时爆破：30个用户，用时27.31秒  
![image](./截屏2025-01-04%20下午12.32.00.png)   

Cookie 爆破：30个用户，用时4.47秒  
![image](./截屏2025-01-04%20下午12.32.19.png)   


**延时爆破和Cookie 爆破结果不一致问题**  
```
延时爆破验证的是域用户，但部署每个域用户都会开启邮箱账号。
```


## 更新日志
```
2025-01-04 v1.1 T00ls 专版
	[+] 设置终端测色输出
	[+] 增加邮箱验证方法，速度更快。
	
2024-09-21 v1.0
	[u] 第一个版本
```

## 原理及参考项目
- https://github.com/rapid7/metasploit-framework/blob/master/modules/auxiliary/scanner/msmail/onprem_enum.go
