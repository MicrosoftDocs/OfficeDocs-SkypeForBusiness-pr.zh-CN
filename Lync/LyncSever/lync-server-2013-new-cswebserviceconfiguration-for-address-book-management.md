---
title: 用于通讯簿管理的 New-CsWebServiceConfiguration
TOCTitle: 用于通讯簿管理的 New-CsWebServiceConfiguration
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429703(v=OCS.15)
ms:contentKeyID: 49312748
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 New-CsWebServiceConfiguration

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 New-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

New-CsWebServiceConfiguration cmdlet 为组织中的 Web 服务定义新配置。Web 服务配置的作用域只能是站点级别或服务级别。无法在全局级别创建新的 Web 服务配置。对于通讯簿，尤其值得关注的是 EnableGroupExansion 属性。如果设置为 True，Web 服务可以响应组扩展的请求。

例如：

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[New-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsWebServiceConfiguration)

