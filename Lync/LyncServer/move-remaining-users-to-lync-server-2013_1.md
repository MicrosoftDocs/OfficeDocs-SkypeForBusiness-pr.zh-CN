---
title: 将其余用户移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>将其余用户移动到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-26_

你可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序将用户移动到新的 Lync Server 2013 部署。 必须满足某些要求才能确保顺利切换到 Lync Server 2013。 有关完成本主题中的过程的先决条件的详细信息, 请参阅[为迁移配置客户端](configure-clients-for-migration_1.md)。 有关移动用户的详细步骤, 请参阅[第6阶段: 将用户移动到试验池](phase-6-move-users-to-the-pilot-pool.md)。

<div>


> [!IMPORTANT]  
> 无法使用 Active Directory 用户和计算机管理单元或 Microsoft Office 通信服务器 2007 R2 管理工具将用户从旧版环境移动到 Lync Server 2013。



</div>

<div>


> [!IMPORTANT]  
> <STRONG>CsLegacyUser</STRONG> cmdlet 要求用户名格式正确, 并且不包含前导空格或尾随空格。 如果用户帐户包含前导空格或尾随空格, 则不能使用<STRONG>CsLegacyUser</STRONG> cmdlet 移动该帐户。



</div>

将用户移动到 Lync Server 2013 池时, 用户的数据将移动到与新池关联的后端数据库。

<div>


> [!IMPORTANT]  
> 这包括由旧版用户创建的活动会议。 例如, 如果旧版用户配置了<STRONG>"我的会议</STRONG>" 会议, 则在用户移动后, 该会议仍将在新的 Lync Server 2013 池中可用。 访问该会议的详细信息仍将是相同的<STRONG>会议 URL 和会议 ID</STRONG>。 唯一的区别是会议现在托管在 Lync Server 2013 池中, 而不是 Office 通信服务器 2007 R2 池中。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 上托管用户不需要同时部署已升级的客户端。 仅当用户升级到新的客户端软件时, 才可使用新功能。



</div>

<div>

## <a name="post-migration-task"></a>发布迁移任务

1.  移动用户后, 请验证分配给他们的会议策略。

2.  为确保驻留在 Lync Server 2013 上的用户组织的会议与托管在 Office 通信服务器 2007 R2 上的联合用户无缝协作, 分配给已迁移用户的会议策略应允许匿名参与者。

3.  允许匿名参与者的会议策略允许**参与者邀请**Lync Server 2013 控制面板中选定的匿名用户, 并在 "输出" 中将**AllowAnonymousParticipantsInMeetings**设置为**True**Lync Server 命令行管理程序中的**CsConferencingPolicy** cmdlet。

4.  有关使用 Lync Server 命令行管理器配置会议策略的详细信息, 请参阅 Lync Server Management Shell 文档中的[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

