# TRautoRace
开源的跑online自动化跑图脚本

[![][black-shield]][black]&nbsp;&nbsp;&nbsp;
[![][black-shield2]][black2]

[black]: https://discord.gg/JVH4QNYMXK
[black-shield]: https://img.shields.io/badge/DISCORD-JOIN-black.svg?style=for-the-badge&labelColor=gray

[black2]: https://im.qq.com
[black-shield2]: https://img.shields.io/badge/QQ_GROUP-718945618-black.svg?style=for-the-badge&labelColor=gray

# 功能
- 基于 [pyautogui](https://pypi.org/project/PyAutoGUI/0.9.53/) 的识图自动化脚本
- 游戏窗口自动前置
- 自动化跑图（极速拼图/超速隧道）
- 房间长时间未开始时自动退出房间
- 处于大厅时自动创建房间（超速隧道）
- [图像预处理](/###能100%自动过验证码吗？) + [ddddocr](https://github.com/sml2h3/ddddocr) = **自动识别验证码**
- 自动化重启游戏（可自定义）
- 根据配置文本自定义游戏键位
- 暂停运行热键: ``ctrl`` + ``f12``

# 如何使用发行版
1. 下载发行版[``TRautoRace.exe``](https://github.com/hiroshi-ya/TRautoRace/releases)
2. 下载或自行创建配置文件[``autoPWD.txt``](https://github.com/hiroshi-ya/TRautoRace/releases)
3. 确保``TRautoRace.exe``和``autoPWD.txt``处于同一文件夹下
4. **参考[配置指南](#配置指南)编辑**``autoPWD.txt``
5. **参考[注意事项](#注意事项)**
6. 以管理员身份（系統管理員身分）运行``TRautoRace.exe``
7. 解放双手

# 配置指南
``autoPWD.txt``格式如下：
```
account   = 
password  = 
forward   = 
backward  = 
leftward  = 
rightward = 
jump      = 
item      = 
item2     = 
item3     = 
sprint    = 
runtime   = 
```
- ``account = ``  后方输入你的游戏账号（可选，默认为不启用重启功能）
- ``password = `` 后方输入你的账号密码（可选，默认为不启用重启功能）
- ``forward = `` 后方输入你的前进按键（默认为``up``）
- ``backward = `` 后方输入你的后退按键（默认为``down``）
- ``leftward = `` 后方输入你的后退按键（默认为``left``）
- ``rightward = `` 后方输入你的后退按键（默认为``right``）
- ``jump = `` 后方输入你的跳跃按键（默认为``ctrl``）
- ``item = `` 后方输入你的道具按键（默认为``shift``）
- ``item2 = `` 后方输入你的道具2按键（默认为``a``）
- ``item3 = `` 后方输入你的道具3按键（默认为``s``）
- ``sprint = `` 后方输入你的冲刺按键（默认为``z``）
- ``runtime = `` 后方输入脚本连续运行时长（单位为“秒”，默认为``21600``秒，即6小时）

### 注意：
- 文本文档中的空格都将被忽略，所以不需要对齐每一行
- 请确保不要修改（``account``等）关键词，修改关键词将导致配置失败
- 请确保不要去掉等号``=``
- 无效输入（如``4000+``、``@``、``XiGuSiMa``等）会被忽略并保持为默认设置
- 键位设置可以留空，留空即为默认设置
- 账号密码可以留空，留空即不开启脚本自动重启功能
- 按键配置中字母无视大小写（大写字母会被自动缩成小写）
- 多余的配置（如``eventMap``）不会被识别

# 注意事项
- **不支持 1024×768 游戏分辨率** ，其余分辨率（全屏/窗口化）皆可
- **游戏画面缩放会导致脚本识图不成功。** 请确保游戏画面没有被系统缩放
- 本程序会自动将游戏窗口前置，如需暂停脚本请按``ctrl`` + ``f12`` 激活暂停。跑图过程中暂停会有些许延迟。重启过程中激活暂停只会待重启过程结束后才会开始暂停
- 如不想每次都点右键选管理员，可以：
  1. 右键``TRautoRace.exe``
  2. 属性（內容）
  3. 兼容性（相容性）
  4. 勾选``以管理员身份运行此程序``（``以系统管理員的身分執行此程式``）
  5. 确定，以后双击启动``TRautoRace.exe``即可
- **启用重启功能必须将游戏目录添加至环境变量（環境變數）：**
  1. Windows设置（設定）
  2. 系统
  3. 系统信息（系統資訊）
  4. 高级系统设置（進階系統設定）
  5. 高级（進階） -> 环境变量（環境變數）
  6. 在用户（使用者）变量或系统变量里寻找到``Path``变量（没有就自己新建一个``Path``）
  7. 编辑
  8. 新建，输入游戏启动器``talesrunner.exe``所在的目录（比如游戏处在``D:\TalesRunner\talesrunner.exe``的话就输入``D:\TalesRunner``）
  9. 确定 -> 确定 -> 确定
  10. 保存后，按下``win`` + ``r``，或者右键开始键 -> ``运行``（``執行``）
  11. 输入``talesrunner``并回车，可正常启动游戏启动器即设置成功
- **启用重启功能需禁用软件启动时的那个提示：**
  1. 开始菜单搜索``uac``
  2. 更改用户账户控制设置（變更使用者賬戶控制設定）
  3. 从不通知（不要通知）
  4. 确定

# 常见问题
> ### Win7能用吗？

大概率不行，因为高版本python不支持Win7了。你可以自行下载程序看是否可以打开。如果报错或无法运行，需要你自行解决。
***
> ### 32位系统能运行吗？

没测试过，可能不行。4202年了还在用32位系统？
***
> ### 你这脚本怎么这么占空间啊？

Python打包就是这样的，已经用upx压缩过了，嫌大你可以自己搭环境然后用Python运行源码
***
> ### 有毒吗？

开源的，你说呢？
***
> ### 用这玩意会被封号吗？

没有被EAC检测的可能。本程序不读取也不修改游戏客户端数据，亦不拦截/修改/伪造/发送网络封包，仅靠屏幕像素数据对关键图案进行识别。键鼠操作通过``DirectInput``键码以及调用Windows自带的``win32 API``实现，人畜无害。 ${\textbf{\color{red}但不排除}}$ 戏谷钓鱼执法，人肉探房的可能。 ${\textbf{\color{red}也不排除}}$ 戏谷人工查看后台游戏数据，根据游戏数据的异常状况（比如一天跑了700多盘极速拼图）进行封禁。本程序对人肉探房/钓鱼执法无保护性措施，仅能自定义连续运行时长。对于一天最多能挂多少小时没有准确的说法，建议不要超过8个小时。本程序作者不对账号安全负责，不保证一定不会被封号。 ${\textbf{\color{red}风险自负}}$ 。
***
> ### 为什么必须要以管理员身份启动你的程序？

因为必须获取管理员权限才能让脚本实行游戏内键鼠操作。
***
> ### 能100%自动过验证码吗？

作者本人测试没有碰到过连续三次验证失败的情况，但是碍于测试时长的问题，目前不能保证验证过程100%不会卡壳。作者通过预处理+多数票以最大可能确保能自动通过验证，连续三次输错的情况非常非常低， ${\textbf{\color{red}但不保证能永不出错}}$ ，望悉知。

预处理效果图：
|处理前|处理后|
|---|---|
| ![pre90](YZMdemo/prtscTest.png) | ![after90](YZMdemo/prtscTestB.png) |
| ![pre83](YZMdemo/test.png) | ![after83](YZMdemo/testB.png) |
***
> ### 运行时可以关掉屏幕的电源吗？

应该是可以的，但是请确保电脑不会息屏。另外，笔记本电脑在合上盖子后会强制息屏，所以在没有外接显示器的情况下大概是不能合上盖子的。
***
> ### 我担心在你的发行版脚本里输入账号密码不安全。

你可以选择不输入账密，不启用自动重启功能。
***
> ### 我想问的问题你这里没有解答。怎样向你反馈问题？

提issue，或者在discord频道交流。欢迎任何PR，也欢迎fork（请遵守GNU GPL v3.0）。请注意：**本人后续维护此脚本的可能性几乎为零**。

# Python解释环境

如果你想要自己用Python运行``autoRace.py``，以下是我环境的部分包：
```
ddddocr = 1.4.8 # require onnxruntime
global-hotkeys = 0.1.6
keyboard = 0.13.5
opencv-python = 4.8.1.78
playsound = 1.2.2
pyautogui = 0.9.53 # don't use later versions
pydirectinput = 1.0.4
pygetwindow = 0.0.9
numpy = 1.26.0
pillow = 9.5.0 # don't use later versions
pyinstaller = 6.0.0 # for packing exe
```
打包使用 [pyinstaller](https://pypi.org/project/pyinstaller/) 、[upx](https://upx.github.io/) 以及 [Enigma Virtual Box](https://enigmaprotector.com/en/aboutvb.html)。
