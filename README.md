# python-bypass
python利用import和pyinstaller简单免杀

# 准备
cs生成一个python的pyload

![](https://raw.githubusercontent.com/chencicici/images/main/202212041732758.png)


# 免杀开始

将生成的pyload中的shellcode取出来放进shellcodeloader.py中


## import混淆加密打包bypass
现在我们把加载器写成一个函数,再通过一个py文件去调用加载器

最终目录如下:

![](https://raw.githubusercontent.com/chencicici/images/main/202212041744127.png)

然后使用pyinstaller开始打包 --key 对二进制文件进行加密,防止反编译

```bash
pyinstaller -F main.py --key test
```



## x绒

可以看到我们没有对加载器做任何免杀操作,但是依旧免杀,简单实用.测试时间2022.12.4

![](https://raw.githubusercontent.com/chencicici/images/main/202212041749331.png)



## x60 (核晶开启)

![](https://raw.githubusercontent.com/chencicici/images/main/202212041750463.png)



## defender

![](https://raw.githubusercontent.com/chencicici/images/main/202212041751616.png)

# cs执行命令

以上都可以正常上线cs并执行命令

![](https://raw.githubusercontent.com/chencicici/images/main/202212041751869.png)


很简单的bypass方式,效果却出奇的好,师傅们可以在这个基础上再进行混淆加密,分离加载等方式
