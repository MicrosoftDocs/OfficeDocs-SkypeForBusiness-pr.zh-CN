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
ms.openlocfilehash: 43be496d0fea280374358b1967ee899ad67624b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="9efb0-102">将其余用户移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9efb0-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9efb0-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="9efb0-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="9efb0-104">您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序将用户移动到新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="9efb0-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="9efb0-105">您必须满足某些要求才能确保顺利过渡到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9efb0-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="9efb0-106">有关完成本主题中的过程的先决条件的详细信息，请参阅[Configure clients for 迁移](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="9efb0-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="9efb0-107">有关移动用户的详细步骤，请参阅[第4阶段：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="9efb0-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9efb0-108">您不能使用 Active Directory 用户和计算机管理单元或 Lync Server 2010 管理工具将用户从旧版环境移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9efb0-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="9efb0-109">将用户移动到 Lync Server 2013 池时，用户的数据将移动到与新池关联的后端数据库中。</span><span class="sxs-lookup"><span data-stu-id="9efb0-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9efb0-110">这包括由旧用户创建的活动会议。</span><span class="sxs-lookup"><span data-stu-id="9efb0-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="9efb0-111">例如，如果旧版用户配置了<STRONG>我的会议</STRONG>会议，则在用户移动后，新的 Lync Server 2013 池中仍将提供该会议。</span><span class="sxs-lookup"><span data-stu-id="9efb0-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="9efb0-112">访问该会议时仍要使用相同的<STRONG>会议 URL 和会议 ID</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9efb0-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="9efb0-113">唯一的区别是会议现在托管在 Lync Server 2013 池中，而不是在 Lync Server 2010 池中。</span><span class="sxs-lookup"><span data-stu-id="9efb0-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9efb0-114">在 Lync Server 2013 上托管用户不需要同时部署已升级的客户端。</span><span class="sxs-lookup"><span data-stu-id="9efb0-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="9efb0-115">仅在升级到新客户端软件后，用户才能使用新功能。</span><span class="sxs-lookup"><span data-stu-id="9efb0-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="9efb0-116">迁移后任务</span><span class="sxs-lookup"><span data-stu-id="9efb0-116">Post Migration Task</span></span>

1.  <span data-ttu-id="9efb0-117">移动用户后，确保向他们分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="9efb0-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="9efb0-118">为了确保由驻留在 Lync Server 2013 上的用户组织的会议与驻留在 Lync Server 2010 上的联合用户无缝协作，分配给迁移用户的会议策略应允许匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="9efb0-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="9efb0-119">允许匿名参与者的会议策略**允许参与者邀请**在 lync Server 2013 控制面板中选择的匿名用户，并在 Lync Server 命令行管理程序中的**set-csconferencingpolicy** cmdlet 的输出中将**AllowAnonymousParticipantsInMeetings**设置为**True** 。</span><span class="sxs-lookup"><span data-stu-id="9efb0-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="9efb0-120">有关使用 Lync Server 命令行管理程序配置会议策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="9efb0-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

