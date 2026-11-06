
# 1 烧写运营商数据

1. 开机上电连接电脑
2. 解压CO_data_SIM89**_7.1_SS_20180718.rar
3. `cd  CO_data_SIM89**_7.1_SS_20180718`
4. 
```
adb reboot bootloader
fastboot erase modemst1
fastboot erase modemst2
fastboot erase fsg
fastboot flash fsg fs_image.tar.gz.mbn.img
fastboot reboot
```


# 2 QCN烧录和备份方法

1. 安装QPST工具
![](Attachment/QCN&fsg&WIFI%20bin导入导出/QCN&fsg&WIFI%20bin导入导出2.png)

2. 烧录qcn， 在“开始->所有程序->QPST->QPST Configuration ->Start Clients”
然后选择相应的选线开始烧录qcn
![](Attachment/QCN&fsg&WIFI%20bin导入导出/QCN&fsg&WIFI%20bin导入导出3.png)
![](Attachment/QCN&fsg&WIFI%20bin导入导出/QCN&fsg&WIFI%20bin导入导出1.png)


3. 备份qcn，在“开始->所有程序->QPST->QPST Configuration ->Start Clients”
选择相应的选线开始备份
![[Attachment/QCN&fsg&WIFI bin导入导出/QCN&fsg&WIFI bin导入导出.png]]


# 3 WIFI bin导入导出

1. WIFI bin导入。上电开机连接电脑，执行以下命令烧录（WCNSS_qcom_wlan_nv.bin文件放到当前目录）
```
adb root
adb remount
adb push .\WCNSS_qcom_wlan_nv.bin /persist/
```

2. WIFI bin导出。上电开机连接电脑，执行以下命令拉出到当前目录
```
adb root
adb remount
adb pull  /persist/
```
