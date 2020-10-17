---
title: Lync Server 2013：用于通讯簿管理的 New-CsWebServiceConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63d6bfeed8b005c3498a2fd0cfcf2201d0d45c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531795"
---
# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中的通讯簿管理 New-CsWebServiceConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 New-CsWebServiceConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

New-CsWebServiceConfiguration cmdlet 为组织中的 Web 服务定义新配置。Web 服务配置的作用域只能是站点级别或服务级别。无法在全局级别创建新的 Web 服务配置。对于通讯簿，尤其值得关注的是 EnableGroupExansion 属性。如果设置为 True，Web 服务可以响应组扩展的请求。

例如：

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>请参阅


[新 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

