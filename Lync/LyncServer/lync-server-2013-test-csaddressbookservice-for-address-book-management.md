---
title: 用于通讯簿管理的 Test-CsAddressBookService
TOCTitle: 用于通讯簿管理的 Test-CsAddressBookService
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429720(v=OCS.15)
ms:contentKeyID: 49314035
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Test-CsAddressBookService

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 Test-CsAddressBookService cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 包含许多 cmdlet，可启动综合命令以确认特定的功能是否正常工作。Test-CsAddressBookService 确认定义的用户是否可以从通讯簿 Web 服务连接并请求本地文件。

例如：

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## 另请参阅

#### 其他资源

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

