---
title: 用于通讯簿管理的 New-CsClientPolicy
TOCTitle: 用于通讯簿管理的 New-CsClientPolicy
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429726(v=OCS.15)
ms:contentKeyID: 49314669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 New-CsClientPolicy

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 New-CsClientPolicy cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

New-CsClientPolicy cmdlet 针对为客户端使用 Lync Server 2013 中提供的功能定义了大量设置。对于通讯簿服务，参数 AddressBookAvailability 很重要。此参数会直接影响可用于客户端的选项，具有三个可能的选项：

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

在定义此参数时，便确定了客户端访问通讯簿的方式。如果定义此参数，必须定义以上选项之一。如果不修改此设置，则仍将使用默认值 WebSearchAndFileDownload。

例如：

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## 另请参阅

#### 其他资源

[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)

