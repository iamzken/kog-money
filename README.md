# kog-money

一个王者荣耀刷金币的小外挂。

## 原理

王者荣耀的冒险模式里有个挑战模式，第一次过关可以获得比较多的金币，后面重新挑战还是会获得少量金币，这不算是bug，只有你不嫌烦手动蛮力也可以刷金币。

> 推荐关卡：陨落的废都 - 魔女回忆

此关卡使用纯输出英雄21秒左右可以打BOSS，30秒左右可以通关，每次重复通关可以获得奖励19金币。在使用脚本刷金币钱建议你手动通关体验一下。此为游戏原理。

简单来说，需要执行以下步骤：

1. 界面打开至挑战关卡：陨落的废都 - 魔女回忆 【点击下一步】
2. 进入阵容调整界面，提前安排好阵容。【点击闯关】
3. 进入挑战界面。【点击右上角-自动-等待挑战结束】
4. 进入挑战完成界面。【点击屏幕继续】
5. 进入关卡奖励界面。【点击再次挑战】
6. 进入阵容调整界面，循环至步骤2。

只要你能模拟屏幕点击就可以完成刷金币的脚本，在安卓模拟界面点击最简单的方式就是使用ADB发送命令，不需要root手机，不需要安装第三方软件，方便快捷。ADB命令点击屏幕坐标[x, y] 可以使用命令：

```
adb shell input tap x y
```

IOS 是否有类似工具和命令，我不清楚，如果有那么实现自动刷金币也很简单。

## 准备

- 本脚本适用于安卓游戏区，需要真实安卓手机。
- 手机需开启USB调试模式，允许电脑调试。
- 电脑需安装好安卓驱动，一般装好豌豆荚或者各种国产管家就可以自动帮你装好。
- 电脑需要有ADB工具集，各种管家会帮你顺便安装。
- ADB工具需要加入环境变量PATH中，方便随时调用。
- 电脑上需要安装Python，当然欢迎你改成别的语言，实现很简单。

专业的开发测试人员，也可以参考我的两篇博客：

- [在 Windows 下搭建 Appium + Android 自动化测试环境](https://betacat.online/posts/2017-05-03/setup-appium-automation-test-environment/)
- [在Mac OSX 上配置Appium+Android自动化测试环境](https://betacat.online/posts/2017-12-10/setup-appium-test-environment-on-mac-osx/)

如果只是为了刷金币，只需要安装好驱动和ADB工具即可。

## 步骤

如果万事具备，那么步骤就非常简单。

1. 用USB连接手机，如果弹出警告，请允许电脑调试手机。
2. 使用命令 `adb devices` 检验adb和手机状态已经就绪。
3. 将游戏打开，挑战到挑战模式，魔女回忆，阵容调整界面。
4. 根据手机性能和分辨率，调整`kog.py`中的各个参数和刷金次数。
5. 运行刷金币命令，手机上可以实时查看到效果。

```
python kog.py
```

注意：

1. 每周金币上限4200，不建议一次刷满，一是会被提醒休息，二是有可能因为各种原因被打断。
2. 铭文，手机性能，英雄选择都会影响通关速度，自己斟酌。

## 声明

本脚本纯属娱乐和平时探索的心得，如果因为违反了游戏规则导致被封号，我概不负责。



