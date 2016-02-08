## 名称
`adjustvb` - 调整 Ubuntu 系统的屏幕亮度和音量大小.           

## 概述             

```bash
adjustvb [-b num] [-i num] [-d num] [-h]	
```

## 选项

**-h**          
&nbsp;&nbsp;&nbsp;查看帮助<br />          
**-b** <u>*brightLevel*</u>         
&nbsp;&nbsp;&nbsp;将屏幕的亮度调整到 <u>*brightLevel*</u> 级别<br />           
**-i** <u>*num*</u>            
&nbsp;&nbsp;&nbsp;将音量增大 <u>*num*</u>%<br />        
**-d** <u>*num*</u>           
&nbsp;&nbsp;&nbsp;将音量减小 <u>*num*</u>%<br />           


## 使用前的一些工作

&nbsp;&nbsp;&nbsp;该程序的运行需要用到系统中的文件 `brightness`，由于不同的机器上该文件的位置不同，为了让该程序能在你的机器上运行，你应该在你的系统的 `/sys/class/backlight/` 目录下查找 `brightness` 文件，并用该文件所在目录的绝对路径替换 `adjustvb` 文件中的 `/paht/to/directory/brightness/in/`,用 `brightness` 文件在你的系统中的绝对路径替换 `adjustvb` 文件中的 `/path/to/brightness`.             
另外，用你的当前用户的密码替换 `adjustvb` 文件中的 `password`.          

修改完毕后，运行如下命令:          

```bash
$ make
```

之后根据提示输入用户密码即可。            

## 示例           

**查看帮助**           

```bash
$ adjustvb -h
```

**调整屏幕亮度** 

```bash
$ adjustvb -b num
```

&nbsp;&nbsp;&nbsp;其中， *num* 是一个整数，其取值范围为 0~*MaxNum*, *MaxNum* 在不同的机器上大小也有不同，你可以在 `/sys/class/backlight/` 目录下寻找 `max_brightness` 文件，其中保存了当前系统的 *MaxNum* 的值.        

**将音量增大5%**

```bash
$ adjustvb -i 5
```

**将音量减小5%**

```bash
$ adjustvb -d 5
```

