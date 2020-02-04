---
title: 启用或禁用 IM 或会议会话的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9782bfa73f30fbefaec0a51d91024b3c40ba55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="62f11-102">在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档</span><span class="sxs-lookup"><span data-stu-id="62f11-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62f11-103">_**主题上次修改时间：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="62f11-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="62f11-104">在 Lync Server 2013 "控制面板" 中，使用存档配置启用和禁用 IM、会议会话的存档。</span><span class="sxs-lookup"><span data-stu-id="62f11-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="62f11-105">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="62f11-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="62f11-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="62f11-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="62f11-107">可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。</span><span class="sxs-lookup"><span data-stu-id="62f11-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="62f11-108">你在部署存档时开始设置存档配置，但你可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="62f11-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="62f11-109">有关如何实现存档配置的详细信息，包括你可以指定哪些选项和存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="62f11-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="62f11-110">若要使用存档，必须配置存档策略以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="62f11-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="62f11-111">默认情况下，不会为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="62f11-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="62f11-112">在任何策略中启用存档之前，应为你的部署指定相应的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="62f11-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="62f11-113">有关启用存档的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="62f11-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="62f11-114">如果你在部署要使用 Microsoft Exchange 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档之后，并且你的所有用户都托管在 Exchange 2013 服务器上，则应删除 SQL Server 数据库配置从拓扑中。</span><span class="sxs-lookup"><span data-stu-id="62f11-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="62f11-115">您必须使用拓扑生成器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="62f11-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="62f11-116">有关详细信息，请参阅在操作文档中<A href="lync-server-2013-changing-archiving-database-options.md">更改 Lync Server 2013 中的存档数据库选项</A>。</span><span class="sxs-lookup"><span data-stu-id="62f11-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="62f11-117">启用或禁用 IM 或会议会话的存档</span><span class="sxs-lookup"><span data-stu-id="62f11-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="62f11-118">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="62f11-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62f11-119">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="62f11-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="62f11-120">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="62f11-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="62f11-121">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="62f11-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="62f11-122">从存档配置列表中选择相应的全局、站点或池策略，单击“**编辑**”，再单击“**显示详细信息**”，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="62f11-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="62f11-123">若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。</span><span class="sxs-lookup"><span data-stu-id="62f11-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="62f11-124">若要同时为 IM 会话和会议启用存档，请单击“**存档 IM 和会议会话**”。</span><span class="sxs-lookup"><span data-stu-id="62f11-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="62f11-125">若要为策略禁用存档，请单击“**禁用存档**”。</span><span class="sxs-lookup"><span data-stu-id="62f11-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="62f11-126">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="62f11-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62f11-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62f11-127">See Also</span></span>


[<span data-ttu-id="62f11-128">管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="62f11-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="62f11-129">在 Lync Server 2013 中配置和分配存档策略</span><span class="sxs-lookup"><span data-stu-id="62f11-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

