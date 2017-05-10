## 名称
`adjustvb` - 调整 Ubuntu 系统的屏幕亮度和音量大小.           

## 概述             

```bash
adjustvb [-b num] [-i num] [-d num] [-g] [-h]	
```

## 适用系统

Ubuntu 14.04, Ubuntu 16.04 等系统

## 选项

**-h**          
&nbsp;&nbsp;&nbsp;查看帮助<br />          
**-g**          
&nbsp;&nbsp;&nbsp;获取当前的 <u>*brightLevel*</u> 值, 即屏幕亮度值<br />          
**-b** <u>*brightLevel*</u>         
&nbsp;&nbsp;&nbsp;将屏幕的亮度调整到 <u>*brightLevel*</u> 级别       
&nbsp;&nbsp;&nbsp;<u>*brightLevel*</u> 的值是从0开始的正整数，其最大值可以查看系统中的
 **/sys/class/backlight/intel_backlight/max_brightness** 文件

**-i** <u>*num*</u>            
&nbsp;&nbsp;&nbsp;将音量增大 <u>*num*</u>%<br />        
**-d** <u>*num*</u>           
&nbsp;&nbsp;&nbsp;将音量减小 <u>*num*</u>%<br />           

## 安装

运行如下命令:          

```bash
$ make
```

## 示例           

**查看帮助**           

```bash
$ adjustvb -h
```

**调整屏幕亮度** 

```bash
$ adjustvb -b num
```

其中， *num* 是一个整数，其取值范围为 0~*MaxNum*, *MaxNum* 在不同的机器上大小也有不同，你可以查看 **/sys/class/backlight/intel_backlight/max_brightness** 文件，其中保存了当前系统的 *MaxNum* 的值.        

**将音量增大5%**

```bash
$ adjustvb -i 5
```

**将音量减小5%**

```bash
$ adjustvb -d 5
```

**获取当前屏幕的亮度值**     

```bash
$ adjustvb -g
```
