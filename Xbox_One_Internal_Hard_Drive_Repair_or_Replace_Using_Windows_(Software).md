# Xbox One X 内置硬盘更换指南 软件部分

## 必备文件及设备

1. Xbox One系统[OSU1.zip](http://www.xbox.com/xboxone/osu1)
2. 硬盘准备工具[xboxonehdd-master-8.zip](https://gbatemp.net/download/xbox-one-windows-and-linux-internal-hard-drive-partitioning-script.34239/download?version=35869)
3. Xbox One X开机动画[bootanim.dat](https://drive.google.com/open?id=1BKcee5bhNLugNkGsMjTV6kS1C5YxCW5H)
4. Xbox One X，必须运行正式版系统，不能是预览版系统
5. 运行Windows操作系统的计算机
6. 替换硬盘，容量为512G/1T/2T，不能为非标准容量
7. 容量大于等于8G的空白U盘
8. USB移动硬盘盒
9. 网线

## 准备工作

1. 参考[Xbox One X 内置硬盘更换指南 硬件部分](https://zh.ifixit.com/Guide/Xbox+One+X+%E5%86%85%E7%BD%AE%E7%A1%AC%E7%9B%98%E6%9B%B4%E6%8D%A2%E6%8C%87%E5%8D%97/124893)，将Xbox One X拆开并取出原装机械硬盘

2. 制作Xbox One系统恢复U盘

   > 1. 将U盘格式化为NTFS格式
   > 2. 用解压工具（如7-zip）将Xbox One系统[OSU1.zip](http://www.xbox.com/xboxone/osu1)解压至U盘根目录
   > 3. 弹出U盘

3. 用解压工具（如7-zip）将硬盘准备工具[xboxonehdd-master-8.zip](https://gbatemp.net/download/xbox-one-windows-and-linux-internal-hard-drive-partitioning-script.34239/download?version=35869)解压至桌面

4. 将Windows系统显示语言设为英文（以中文版Windows 10为例）

   > 1. 打开“所有设置”——“时间和语言”
   > 2. 单击“语言”——“添加语言”——“英语（美国）”——“下一步”
   > 3. 选中全部选项（**必选**“安装语言包并设置为我的Windows显示语言”），单击“安装”
   > 4. 打开“控制面板”——“区域”
   > 5. 单击“管理”——“更改系统区域设置”
   > 6. 将“当前系统区域设置”为“英语（美国）”，单击确认
   > 7. 重新启动计算机

5. 移除连接至计算机的全部外置磁盘，确保驱动器号`H:`，`I:`，`J:`，`K:`，`L:`，`U:`，`V:`，`W:`，`X:`，`Y:`**未**被占用

6. 将替换硬盘装入移动硬盘盒，用USB线连接至计算机

## 处理替换硬盘

1. **以管理员身份运行**命令提示符

2. 执行

   ```
   cd %USERPROFILE%\Desktop\xboxonehdd-master\win
   ```

3. 执行

   ```
   .\create_xbox_drive.bat
   ```

4. 根据屏幕提示，键入任意键

5. 根据屏幕提示，键入`a`

   > 提示：如果之前没有将Windows系统显示语言设为英文，此处将报错
   >
   > ```
   > * No USB/SATA drives found *
   > ```

6. 根据屏幕提示，键入替换硬盘的磁盘编号

7. 根据屏幕提示，键入`Y`，确认擦除替换硬盘上的全部信息

8. 根据屏幕提示，选择分区方案

   > - 替换硬盘容量为500G，键入`a`
   > - 替换硬盘容量为1T，键入`b`
   > - 替换硬盘容量为2T，键入`c`

9. 等待程序运行完毕，核查屏幕输出，必须与下表提供数据相同，否则失败

   > - 替换硬盘容量为500GB
   >
   >   | GUID                                   | Dev  | Size      | Name              |
   >   | -------------------------------------- | ---- | --------- | ----------------- |
   >   | `A2344BDB-D6DE-4766-9EB5-4109A12228E5` |      |           | `(500GB)`         |
   >   | `B3727DA5-A3AC-4B3D-9FD6-2EA54441011B` | `U:` | `41 GB`   | `Temp Content`    |
   >   | `869BB5E0-3356-4BE6-85F7-29323A675CC7` | `V:` | `365 GB`  | `User Content`    |
   >   | `C90D7A47-CCB9-4CBA-8C66-0459F6B85724` | `W:` | `40 GB`   | `System Support`  |
   >   | `9A056AD7-32ED-4141-AEB1-AFB9BD5565DC` | `X:` | `12 GB`   | `System Update`   |
   >   | `24B2197C-9D01-45F9-A8E1-DBBCFA161EB2` | `Y:` | `7168 MB` | `System Update 2` |
   >
   > - 替换硬盘容量为1TB
   >
   >   | GUID                                   | Dev  | Size      | Name              |
   >   | -------------------------------------- | ---- | --------- | ----------------- |
   >   | `25E8A1B2-0B2A-4474-93FA-35B847D97EE5` |      |           | `(1TB)`           |
   >   | `B3727DA5-A3AC-4B3D-9FD6-2EA54441011B` | `U:` | `41 GB`   | `Temp Content`    |
   >   | `869BB5E0-3356-4BE6-85F7-29323A675CC7` | `V:` | `781 GB`  | `User Content`    |
   >   | `C90D7A47-CCB9-4CBA-8C66-0459F6B85724` | `W:` | `40 GB`   | `System Support`  |
   >   | `9A056AD7-32ED-4141-AEB1-AFB9BD5565DC` | `X:` | `12 GB`   | `System Update`   |
   >   | `24B2197C-9D01-45F9-A8E1-DBBCFA161EB2` | `Y:` | `7168 MB` | `System Update 2` |
   >
   > - 替换硬盘容量为2TB
   >
   >   | GUID                                   | Dev  | Size      | Name              |
   >   | -------------------------------------- | ---- | --------- | ----------------- |
   >   | `5B114955-4A1C-45C4-86DC-D95070008139` |      |           | `(2TB)`           |
   >   | `B3727DA5-A3AC-4B3D-9FD6-2EA54441011B` | `U:` | `41 GB`   | `Temp Content`    |
   >   | `869BB5E0-3356-4BE6-85F7-29323A675CC7` | `V:` | `1662 GB` | `User Content`    |
   >   | `C90D7A47-CCB9-4CBA-8C66-0459F6B85724` | `W:` | `40 GB`   | `System Support`  |
   >   | `9A056AD7-32ED-4141-AEB1-AFB9BD5565DC` | `X:` | `12 GB`   | `System Update`   |
   >   | `24B2197C-9D01-45F9-A8E1-DBBCFA161EB2` | `Y:` | `7168 MB` | `System Update 2` |
   >
   
10. 如无错误，则替换硬盘处理成功

## 恢复Xbox One系统

1. 将替换硬盘连接至Xbox One X，此时不能组装其它部件
2. 接通电源，开机（使用主机开关或手柄西瓜键均可）
3. 看到“System Error: E106 00000009 80070002”错误提示后，用手柄方向键（不是摇杆）选择“Troubleshoot”——“Reset this Xbox”——“Remove everything”并按“A”，重启Xbox One X，约60秒
4. 看到“System Error: E106 00000009 80070003”错误提示后，用手柄方向键（不是摇杆）选择“Troubleshoot”，此时“Offline system update”为灰色
5. 通过后置USB接口将Xbox One系统恢复U盘连接至Xbox One X，此时“Offline system update”变为黑色，用手柄方向键（不是摇杆）选择“Offline system update”并按“A”，等待系统恢复完成
6. 系统恢复成功并自动重启后，进入Xbox One X首次开机激活程序（国行机为中文界面）。用网线将Xbox One X接入网络，按屏幕提示激活系统
7. 激活成功后，完全关机Xbox One X，切断电源，取出替换硬盘
8. 将替换硬盘连接至计算机，将Xbox One X开机动画[bootanim.dat](https://drive.google.com/open?id=1BKcee5bhNLugNkGsMjTV6kS1C5YxCW5H)复制到分区“X:\System Update\A”和“X:\System Update\B”目录中
9. 弹出替换硬盘并再次将其连接至Xbox One X，通电开机
10. 看到启动动画并启动无误后，切断电源，并参考[Xbox One X 内置硬盘更换指南 硬件部分](https://zh.ifixit.com/Guide/Xbox+One+X+%E5%86%85%E7%BD%AE%E7%A1%AC%E7%9B%98%E6%9B%B4%E6%8D%A2%E6%8C%87%E5%8D%97/124893)，组装Xbox One X。至此，全流程结束