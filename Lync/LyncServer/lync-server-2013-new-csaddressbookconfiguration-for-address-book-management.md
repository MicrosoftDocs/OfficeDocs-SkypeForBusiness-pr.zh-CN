---
title: 用于通讯簿管理的 New-CsAddressBookConfiguration
TOCTitle: 用于通讯簿管理的 New-CsAddressBookConfiguration
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429718(v=OCS.15)
ms:contentKeyID: 49313821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 New-CsAddressBookConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 New-CsAddressBookConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

New-CsAddressBookConfiguration cmdlet 会创建新的配置以管理通讯簿的行为。此 cmdlet 特定的功能是定义通讯簿服务是否创建客户端下载文件、是否以及如何使用规范化规则、保留增量文件和压缩增量文件的时间长度、融入新的完全文件创建之前的增量文件大小、创建完全文件通讯簿的时间，以及用户数据库中信息同步的内部内容。

例如：

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[New-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAddressBookConfiguration)

