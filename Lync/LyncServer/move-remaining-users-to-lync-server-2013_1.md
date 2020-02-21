---
title: 将其余用户移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ded313a9c46617716bf7c25884dbb0ed9bcce5d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="3e978-102">将其余用户移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e978-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e978-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3e978-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3e978-104">您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序将用户移动到新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="3e978-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="3e978-105">您必须满足某些要求才能确保顺利过渡到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3e978-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="3e978-106">有关完成本主题中的过程的先决条件的详细信息，请参阅[Configure clients for 迁移](configure-clients-for-migration_1.md)。</span><span class="sxs-lookup"><span data-stu-id="3e978-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="3e978-107">有关移动用户的详细步骤，请参阅[第6阶段：将用户移动到试点池](phase-6-move-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="3e978-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e978-108">您不能使用 Active Directory 用户和计算机管理单元或 Microsoft Office 通信服务器 2007 R2 管理工具将用户从旧版环境移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3e978-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e978-p102"><STRONG>Move-CsLegacyUser</STRONG> cmdlet 要求用户名的格式必须正确，并且没有前导或尾随空格。如果某用户帐户包含前导或尾随空格，则不能使用 <STRONG>Move-CsLegacyUser</STRONG> cmdlet 移动它。</span><span class="sxs-lookup"><span data-stu-id="3e978-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="3e978-111">将用户移动到 Lync Server 2013 池时，用户的数据将移动到与新池关联的后端数据库中。</span><span class="sxs-lookup"><span data-stu-id="3e978-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e978-112">这包括由旧用户创建的活动会议。</span><span class="sxs-lookup"><span data-stu-id="3e978-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="3e978-113">例如，如果旧版用户配置了<STRONG>我的会议</STRONG>会议，则在用户移动后，该会议仍将在新的 Lync Server 2013 池中可用。</span><span class="sxs-lookup"><span data-stu-id="3e978-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="3e978-114">访问该会议时仍要使用相同的<STRONG>会议 URL 和会议 ID</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3e978-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="3e978-115">唯一的区别是会议现在托管在 Lync Server 2013 池，而不是 Office 通信服务器 2007 R2 池中。</span><span class="sxs-lookup"><span data-stu-id="3e978-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3e978-116">在 Lync Server 2013 上托管用户不需要同时部署已升级的客户端。</span><span class="sxs-lookup"><span data-stu-id="3e978-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="3e978-117">仅在升级到新客户端软件后，用户才能使用新功能。</span><span class="sxs-lookup"><span data-stu-id="3e978-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="3e978-118">迁移后任务</span><span class="sxs-lookup"><span data-stu-id="3e978-118">Post Migration Task</span></span>

1.  <span data-ttu-id="3e978-119">移动用户后，确保向他们分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="3e978-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="3e978-120">为了确保由驻留在 Lync Server 2013 上的用户组织的会议与托管在 Office 通信服务器 2007 R2 上的联合用户无缝协作，分配给迁移用户的会议策略应允许匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="3e978-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="3e978-121">允许匿名参与者的会议策略**允许参与者邀请**在 lync Server 2013 控制面板中选择的匿名用户，并在 Lync Server 命令行管理程序中的**set-csconferencingpolicy** cmdlet 的输出中将**AllowAnonymousParticipantsInMeetings**设置为**True** 。</span><span class="sxs-lookup"><span data-stu-id="3e978-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="3e978-122">有关使用 Lync Server 命令行管理程序配置会议策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="3e978-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

