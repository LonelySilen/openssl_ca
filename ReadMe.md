基于OpenSSL的证书中心
===================

--------


项目概要
---------

**OpenSSL_CA**使用C++语言编写，开发框架为QT，支持跨平台       
程序使用OpenSSL提供的include文件以及lib库      
目前已完成具备基本操作的1.0版本，正在重写2.0版本

----------


目前情况
-------------

> **已经完成的内容:**

> - 证书请求文件的生成
> - 文件传输功能（内网）
> - 根证书对请求文件签名，验证及撤销发布证书
> - 恢复被撤销的证书

> **现在存在的问题:**

> - V1.0：   
1.  在X509中没有找到相应修改文件路径的函数，在使用中生成的文件都存放在opensslca.exe同级目录下，无法组织合理的文件目录       
2.  生成证书请求文件时，大部分函数返回值没有进行判断或没有合理的返回操作，导致代码健壮性不足，无法获取相应的错误判断，程序崩溃时无法快速定位错误位置
3.  存在函数功能重合，变量定义冗余情况
4.  没有规范代码命名规则，注释不全

> - V2.0：  
1.   在2.0版本中分离了客户端和CA中心服务器，目前只完成了文件传输操作，在传输初始时未实现数字信封
2.  客户端仅对部分输入框进行了正则规范
3.  ...

> **接下来的工作：**

> - 在V1.0的基础上重写V2.0版本
> - 继续完善注释、变量及函数规范
> - 调整界面布局
> - 完成V2.0版本CA服务器

--------

错误排除
-----

> **可能出现的问题**

> - 编译时可能出现的问题
> 