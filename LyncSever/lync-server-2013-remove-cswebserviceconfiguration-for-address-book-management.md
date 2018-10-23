---
title: 用于通讯簿管理的 Remove-CsWebServiceConfiguration
TOCTitle: 用于通讯簿管理的 Remove-CsWebServiceConfiguration
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429713(v=OCS.15)
ms:contentKeyID: 49313610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Remove-CsWebServiceConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Remove-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

通过 Remove-CsWebServiceConfiguration cmdlet，管理员可以删除之前创建的 Web 服务配置。该 cmdlet 无法删除全局 Web 服务配置。

例如：

    Remove-CsWebServiceConfiguration -Identity site:Redmond

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

