# Exchange-UserBrute
验证用户是否存在与Exchange 

## 使用方法
**参数**
```
Usage of ./Exchange-UserBrute:
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
Brute -u https://main.test.com -name Administrator
```
<img width="882" alt="截屏2024-09-21 上午10 08 08" src="https://github.com/user-attachments/assets/e682ca54-3366-4360-8256-530528f29b85">


**批量验证**
```
Brute -u https://main.test.com -uf user.txt 
```
<img width="799" alt="截屏2024-09-21 上午10 04 25" src="https://github.com/user-attachments/assets/1e193f4c-79df-4d35-af7b-66f5edd1e4a2">



## MD5
```
e65bfbc9bc3d35daaeaaadd93352a3bc  Exchange-UserBrute-Linux
fb3a9d98e78ddb8f31944aa3731f9d41  Exchange-UserBrute-Mac
567e2d79ebabcb1d3a3a3612f0b68014  Exchange-UserBrute-Win.exe
```


## 原理及参考项目
- https://github.com/rapid7/metasploit-framework/blob/master/modules/auxiliary/scanner/msmail/onprem_enum.go
