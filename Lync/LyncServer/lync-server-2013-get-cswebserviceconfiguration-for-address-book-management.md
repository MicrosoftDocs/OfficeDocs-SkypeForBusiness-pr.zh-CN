---
title: 用于通讯簿管理的 Get-CsWebServiceConfiguration
TOCTitle: 用于通讯簿管理的 Get-CsWebServiceConfiguration
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429692(v=OCS.15)
ms:contentKeyID: 49311958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Get-CsWebServiceConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsWebServiceConfiguration cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Get-CsWebServiceConfiguration 可返回有关组织中当前使用的 Web 服务配置的信息。对于通讯簿服务，值得关注的是通讯组列表扩展功能的状态。如果 EnableGroupExpansion 属性为 True，则您的组织当前允许组扩展。

例如：

    Get-CsWebServiceConfiguration -Identity site:Redmond

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

