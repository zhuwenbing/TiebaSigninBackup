<div align="center"> 
<h1 align="center">贴吧签到助手</h1>
<img src="https://img.shields.io/github/issues/ShadowDumb/TiebaSignInBackup?color=green">
<img src="https://img.shields.io/github/stars/ShadowDumb/TiebaSignInBackup?color=yellow">
<img src="https://img.shields.io/github/forks/ShadowDumb/TiebaSignInBackup?color=orange">
<img src="https://img.shields.io/github/license/ShadowDumb/TiebaSignInBackup?color=ff69b4">
<img src="https://img.shields.io/github/languages/code-size/ShadowDumb/TiebaSignInBackup?color=blueviolet">
</div>

# 简介

用的是手机端的接口，签到经验更多，用户只需要填写`BDUSS`即可，每日自动帮你签到，最多支持`200`个贴吧签到。

这是一个克隆的仓库，克隆地址：[https://github.com/LuoSue/TiebaSignIn-1](https://github.com/LuoSue/TiebaSignIn-1)

本仓库的最初版本已经删除，原作者是：https://github.com/srcrs

# 功能

+ 贴吧签到(最多支持 200 个)

+ 支持推送运行结果至微信(通过 server 酱)

# 使用方法

## 1.fork本项目

## 2.获取BDUSS

在网页中登录上贴吧，然后按下`F12`打开调试模式，在`cookie`中找到`BDUSS`，并复制其`Value`值。

![](./assets/获取BDUSS.gif)

## 3.将BDUSS添加到仓库的Secrets中

Name | Value
-|-
BDUSS | xxxxxxxxxxx

将上一步骤获取到的`BDUSS`粘贴到`Secrets`中

![](./assets/添加BDUSS.gif)

## 4.开启actions

默认`actions`是处于禁止的状态，需要手动开启。

![](./assets/开启actions.gif)

## 5.第一次运行actions

+ 自己提交一次`push`。

将`run.txt`中的`flag`由`0`改为`1`

```patch
- flag: 0
+ flag: 1
```

![](./assets/运行结果.gif)

## 成功了

为了避免漏签，每天会自动签到两次，时间分别为`00:30`和`12:30`，由于GitHub Action的时间和北京时间的时差原因，实际签到时间会晚8小时。

## 添加server酱推送

需在Secrets中添加[server酱](http://sc.ftqq.com/)的`SCKEY`，格式如下

Name | Value
-|-
SCKEY | xxxxxxxxxx

## 2022-02-10

+ 捉几个虫子

+ 把签到频率从原版的每天只签到一次改为每天签到两次，防止漏签

+ 再次说明一下，我不是这个项目的原作者，我也不会负责该项目的后续开发

## 2020-11-01

+ 代码重构

+ 修改签到策略

大大提高一次运行，贴吧签到的成功率，基本很少的贴吧会签到失败。

+ 去除多用户的支持

+ 增加支持server酱推送，可以推送至微信

## 2020-10-19

~~增加支持多账户签到，每个账号的`BDUSS`使用`&&`分割，具体格式如下。~~
