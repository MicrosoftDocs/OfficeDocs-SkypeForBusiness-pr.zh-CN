---
title: 连接到租户的能力被禁用
TOCTitle: 连接到租户的能力被禁用
ms:assetid: 7365d31b-173e-4339-b0a3-98ab73a9558f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362820(v=OCS.15)
ms:contentKeyID: 56271160
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 连接到租户的能力被禁用

 

_**上一次修改主题：** 2015-06-22_

要使用 Windows PowerShell 以便管理 Skype for Business Online，您的租户的 Windows PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为 True。如果不是，您的连接将会失败，您将收到以下错误消息：

    New-PSSession : [admin.vdomain.com] 处理远程服务器 admin.vdomain.com 中的数据失败，并显示以下错误消息:使用远程 PowerShell 会话连接到此租户的能力已被禁用。请联系 Lync 帮助以检查此租户的租户 Powershell 策略。有关详细信息，请参阅 about_Remote_Troubleshooting 帮助主题.

如果看到此错误消息，您需要联系 Office 365 支持人员并被启用远程 Windows PowerShell 访问。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

