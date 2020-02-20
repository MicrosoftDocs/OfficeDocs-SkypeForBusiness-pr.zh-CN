---
title: Lync Server 2013： Set-csclientpolicy for Address Book management
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5f8bc13421e07f3127b1669752c96796e533efc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中的通讯簿管理的 Set-csclientpolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Set-CsClientPolicy cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

与 New-CsClientPolicy 类似，通过 Set-CsClientPolicy cmdlet，可以修改已配置的客户端设置。

例如：

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a>请参阅


[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

