---
title: 用于通讯簿管理的 Get-CsAddressBookConfiguration
TOCTitle: 用于通讯簿管理的 Get-CsAddressBookConfiguration
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429721(v=OCS.15)
ms:contentKeyID: 49314088
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Get-CsAddressBookConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsAddressBookConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Get-CsAddressBookConfiguration cmdlet 返回有关已存在的配置的信息。

例如：

    Get-CsAddressBookConfiguration -Identity site:Redmond

通过组合 Get-CsAddressBookConfiguration 和 Set-CsAddressBookConfiguration 的功能，管理员可以定义要修改的配置，然后应用修改。例如，对与以下组合：

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

返回所有站点中的所有配置，并为配置中的 RunTimeOfDay 应用值 23:00。

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

