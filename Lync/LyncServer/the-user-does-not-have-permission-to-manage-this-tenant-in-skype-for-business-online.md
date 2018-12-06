---
title: 用户没有管理此帐户的权限
TOCTitle: 用户没有管理此帐户的权限
ms:assetid: 714ccf81-9451-4585-b62d-979f2a606315
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362812(v=OCS.15)
ms:contentKeyID: 56271151
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用户没有管理此帐户的权限

 

_**上一次修改主题：** 2015-06-22_

除非您是“租户管理员”组的成员，否则您无法与 Skype for Business Online 建立远程 Windows PowerShell 连接。如果您不是，您的连接尝试将会失败，您将收到以下错误消息：

    New-PSSession : [admin.vdomain.com] 处理远程服务器 admin.vdomain.com 中的数据失败，并显示以下错误消息:用户"user@foo.com"不具有管理此租户的权限。可通过将用户分配给合适的 RBAC 角色来授予权限。有关详细信息，请参阅 about_Remote_Troubleshooting 帮助主题.

如果您认为您是或应该是“租户管理员”组的成员，您需要联系 Office 365 支持人员。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

