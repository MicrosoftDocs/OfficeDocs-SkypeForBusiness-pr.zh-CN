---
title: 无法连接到 Live ID 服务器
TOCTitle: 无法连接到 Live ID 服务器
ms:assetid: 701af721-dd6a-4f48-96f9-94e89c644201
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362811(v=OCS.15)
ms:contentKeyID: 56271167
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 无法连接到 Live ID 服务器

 

_**上一次修改主题：** 2015-06-22_

您的连接尝试可能失败并出现以下错误消息通常有三大原因：

    Get-CsWebTicket : 无法连接 live id 服务器。确保代理已启用或者计算机与 live id 服务器建立了网络连接。

通常，此错误意味着 Microsoft Online Services 登录助手未运行。您可以通过从 Windows PowerShell 提示符处运行以下命令来验证此服务的状态：

    Get-Service "msoidsvc"

如果该服务未运行，请使用此命令启动该服务：

    Start-Service "msoidsvc"

如果该服务正在运行，您的计算机与 Microsoft Live ID 身份验证服务器之间可能会出现网络连接问题。要进行检查，请打开 Internet Explorer 并导航至 <https://login.microsoftonline.com/>。尝试从这里登录到 Office 365。如果登录失败，您可能会遇到网络连接问题。

不常见的是，Microsoft Live ID 身份验证服务器的连接 URI 已配置为错误的值。如果您已确定登录助手正在运行，并且您未遇到网络连接问题，则这可能是一个问题。在这种情况下，请联系 Office 365 支持人员。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)

