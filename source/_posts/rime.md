---
title: rime
categories:
  - 技术
tags:
  - 输入法
keywords: 中英文切换键 中英文切换 Windows10
description: Windows10 更换中英文切换键
abbrlink: 4affc799
date: 2021-06-13 14:41:10
---

**使用输入法**： RIME 小狼嚎

**特点** : 高度自定义，提示有点蠢



**使用方法**：

​	1、切换简体方案： ctrl + ` 选择 明（囧月-似乎读明）月拼音-简体

​	2、点击任务栏，右击输入法，点击用户文件夹

​	3、从biuld文件夹里复制 default.yaml 、luna_pinyin_simp.schema.yaml（明月拼音所对应的配置文件） 到 Rime文件夹

​	4、打开 default.yaml  （Shift_L: noop）  Shift_L 设置为 noop，这样输入法就会忽略 左 shift

​	5、下面对应行加入    - {accept: "Control+space", toggle: ascii_mode, when: always} 用ctrl + 空格来切换，其他的也可以

​	6、windows 已经有这个快捷键了，所以还得取消一下，控制面板-> 时钟语言和区域->语言->左侧高级->更改语言热键，将里面的冲突按键修改成其他按键

​	7、配置已经修改好了，右击输入法，重新部署

完成

 