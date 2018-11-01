---
title: 已超过此租户的最大并发外壳程序连接数
TOCTitle: 已超过此租户的最大并发外壳程序连接数
ms:assetid: a4c91ffa-fdcc-414c-b941-a0d36c906825
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362832(v=OCS.15)
ms:contentKeyID: 56271189
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 已超过此租户的最大并发外壳程序连接数

 

_**上一次修改主题：** 2015-06-22_

尽管允许每个管理员同时与 Skype for Business Online 租户建立三个连接，但是不允许单个租户同时有超过九个连接。例如，三个管理员分别有三个打开的会话。如果第四个管理员尝试建立连接（导致总共 10 个同时连接），则此尝试将会失败，并出现以下错误消息：

    New-PSSession : [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，并显示以下错误消息:WS-Management 服务无法处理该请求。已超过此租户的最大并发外壳数。请关闭现有外壳或者增加此租户的配额。有关详细信息，请参阅 about_Remote_Troubleshooting 帮助主题.

解决此问题的唯一方法是关闭以前的一个或多个连接。当您完成 Skype for Business Online 会话后，建议您使用 **Remove-PSSession** cmdlet 终止该会话。这可帮助您避免此问题。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

