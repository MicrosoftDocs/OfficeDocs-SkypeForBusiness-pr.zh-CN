---
title: Lync Server 2013：中央管理存储复制状态
TOCTitle: 中央管理存储复制状态
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn720926(v=OCS.15)
ms:contentKeyID: 62246698
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的中央管理存储复制状态

 

_**上一次修改主题：** 2015-01-26_

当管理员对 Lync Server 进行某种更改（例如，管理员创建新的语音策略或更改通讯簿服务器配置设置）时，该更改会记录在中央管理存储中。反过来，还必须将该更改复制到运行 Lync Server 服务或服务器角色的所有计算机。

要复制数据，主复制程序（在中央管理服务器上运行）会为所更改的配置数据创建一个快照。此快照的副本随后将发送到运行 Lync Server 服务或服务器角色的每台计算机。在这些计算机上，复制代理将接收快照并上载所更改的数据。然后，代理会向主复制程序发送一条消息，报告最新的复制状态。

通过 Get-CsManagementStoreReplicationStatus cmdlet，可以验证组织中任何（或所有）Lync Server 计算机的复制状态。

谁可以运行此 cmdlet？默认情况下，以下各组的成员有权在本地运行 Get-CsManagementStoreReplicationStatus cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。

要返回分配了此 cmdlet 的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

## 另请参阅

#### 其他资源

[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsManagementStoreReplicationStatus)

