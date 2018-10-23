---
title: 用于通讯簿管理的 Set-CsWebServiceConfiguration
TOCTitle: 用于通讯簿管理的 Set-CsWebServiceConfiguration
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429709(v=OCS.15)
ms:contentKeyID: 49313346
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Set-CsWebServiceConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Set-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

通过 Set-CsWebServiceConfiguration cmdlet，管理员可以重新定义 Web 服务配置中的现有属性。

例如：

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

