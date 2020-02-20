---
title: 将其余用户移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b95ad3ba755839090cb74a174789c71b16d9eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>将其余用户移动到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序将用户移动到新的 Lync Server 2013 部署。 您必须满足某些要求才能确保顺利过渡到 Lync Server 2013。 有关完成本主题中的过程的先决条件的详细信息，请参阅[Configure clients for 迁移](configure-clients-for-migration.md)。 有关移动用户的详细步骤，请参阅[第4阶段：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)。

<div>


> [!IMPORTANT]  
> 您不能使用 Active Directory 用户和计算机管理单元或 Lync Server 2010 管理工具将用户从旧版环境移动到 Lync Server 2013。



</div>

将用户移动到 Lync Server 2013 池时，用户的数据将移动到与新池关联的后端数据库中。

<div>


> [!IMPORTANT]  
> 这包括由旧用户创建的活动会议。 例如，如果旧版用户配置了<STRONG>我的会议</STRONG>会议，则在用户移动后，新的 Lync Server 2013 池中仍将提供该会议。 访问该会议时仍要使用相同的<STRONG>会议 URL 和会议 ID</STRONG>。 唯一的区别是会议现在托管在 Lync Server 2013 池中，而不是在 Lync Server 2010 池中。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 上托管用户不需要同时部署已升级的客户端。 仅在升级到新客户端软件后，用户才能使用新功能。



</div>

<div>

## <a name="post-migration-task"></a>迁移后任务

1.  移动用户后，确保向他们分配会议策略。

2.  为了确保由驻留在 Lync Server 2013 上的用户组织的会议与驻留在 Lync Server 2010 上的联合用户无缝协作，分配给迁移用户的会议策略应允许匿名参与者。

3.  允许匿名参与者的会议策略**允许参与者邀请**在 lync Server 2013 控制面板中选择的匿名用户，并在 Lync Server 命令行管理程序中的**set-csconferencingpolicy** cmdlet 的输出中将**AllowAnonymousParticipantsInMeetings**设置为**True** 。

4.  有关使用 Lync Server 命令行管理程序配置会议策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

