---
title: 已超过此用户的并发外壳程序的最大数目
TOCTitle: 已超过此用户的并发外壳程序的最大数目
ms:assetid: b309efe8-a214-41ea-a345-93e6a36e0cb1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362837(v=OCS.15)
ms:contentKeyID: 56271193
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 已超过此用户的并发外壳程序的最大数目

 

_**上一次修改主题：** 2015-06-22_

每个管理员允许最多同时与 Skype for Business Online 建立三个远程连接。如果您有三个远程 Windows PowerShell 连接正在运行，建立第四个同时连接的任何尝试都将失败，并出现以下错误消息：

    New-PSSession : [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，并显示以下错误消息:WS-Management 服务无法处理该请求。已超过此用户的最大并发外壳数。请关闭现有外壳或者增加此用户的配额。有关详细信息，请参阅 about_Remote_Troubleshooting 帮助主题。

解决此问题的唯一方法是关闭以前的一个或多个连接。当您完成 Skype for Business Online 会话后，建议您使用 **Remove-PSSession** cmdlet 终止该会话。这可帮助您避免此问题。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

