---
title: Lync Server 2013：中央管理存储复制状态
description: Lync Server 2013：中央管理存储复制状态。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544358"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存储复制状态

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-01-26_

当管理员将某种类型更改为 Lync Server (时，例如，当管理员创建新的语音策略或更改通讯簿服务器配置设置时) 该更改将记录在中央管理存储中。 反过来，必须将更改复制到运行 Lync Server 服务或服务器角色的所有计算机。

若要复制数据，在中央管理服务器上运行的主复制器 () 会创建更改的配置数据的快照。 然后，将此快照的副本发送到运行 Lync Server 服务或服务器角色的每台计算机。 在这些计算机上，复制代理接收快照并上载已更改的数据。 然后，代理会将报告最新复制状态的邮件发送到主复制器。

Get-CsManagementStoreReplicationStatus cmdlet 使您能够验证组织中的所有 (或所有) 的 Lync Server 计算机的复制状态。

谁可以运行此 cmdlet？ 默认情况下，以下组的成员有权在本地运行 Get-CsManagementStoreReplicationStatus cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。

若要返回此 cmdlet 分配到的所有 RBAC 角色的列表，请 (包括您自己) 创建的任何自定义 RBAC 角色，请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>另请参阅


[Get-csmanagementstorereplicationstatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

