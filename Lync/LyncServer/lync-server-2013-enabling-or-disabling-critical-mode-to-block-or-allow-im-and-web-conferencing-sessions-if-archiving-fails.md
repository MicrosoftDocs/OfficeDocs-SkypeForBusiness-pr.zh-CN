---
title: 'Lync Server 2013: 启用或禁用关键模式, 以阻止或允许 IM 和网络会议会话 (如果存档失败)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="f97f9-102">启用或禁用 Lync Server 2013 中的关键模式, 以阻止或允许 IM 和网络会议会话 (如果存档失败)</span><span class="sxs-lookup"><span data-stu-id="f97f9-102">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f97f9-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f97f9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f97f9-104">在 Lync Server 2013 "控制面板" 中, 使用存档配置启用和禁用关键模式。</span><span class="sxs-lookup"><span data-stu-id="f97f9-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="f97f9-105">这包括以下存档配置:</span><span class="sxs-lookup"><span data-stu-id="f97f9-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f97f9-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="f97f9-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f97f9-107">可创建和使用的可选网站级和池级配置, 用于指定如何为特定网站或池实现存档。</span><span class="sxs-lookup"><span data-stu-id="f97f9-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f97f9-108">你在部署存档时开始设置存档配置, 但你可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="f97f9-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f97f9-109">有关如何实现存档配置的详细信息, 包括你可以指定哪些选项和存档配置的层次结构, 请参阅规划文档、部署中的[Lync Server 2013 中的存档工作原理](lync-server-2013-how-archiving-works.md)文档或操作文档。</span><span class="sxs-lookup"><span data-stu-id="f97f9-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f97f9-110">若要使用存档, 必须配置存档策略以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="f97f9-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="f97f9-111">默认情况下, 不会为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="f97f9-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f97f9-112">在任何策略中启用存档之前, 应为你的部署指定相应的存档配置, 并根据需要为特定的网站和池指定相应的存档配置, 如本节所述。</span><span class="sxs-lookup"><span data-stu-id="f97f9-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f97f9-113">有关启用存档的详细信息, 请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="f97f9-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f97f9-114">如果你在部署要使用 Exchange Server 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档后确定你想要使用 Exchange Server 集成, 并且你的所有用户都在 Exchange 2013 服务器上托管, 则应删除 SQL Server 数据库配置你的拓扑。</span><span class="sxs-lookup"><span data-stu-id="f97f9-114">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="f97f9-115">您必须使用拓扑生成器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f97f9-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="f97f9-116">有关详细信息, 请参阅在操作文档中<A href="lync-server-2013-changing-archiving-database-options.md">更改 Lync Server 2013 中的存档数据库选项</A>。</span><span class="sxs-lookup"><span data-stu-id="f97f9-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="f97f9-117">启用或禁用阻止即时消息和网络会议会话 (如果存档失败)</span><span class="sxs-lookup"><span data-stu-id="f97f9-117">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="f97f9-118">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f97f9-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f97f9-119">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f97f9-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f97f9-120">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f97f9-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f97f9-121">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f97f9-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="f97f9-122">单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f97f9-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="f97f9-123">要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="f97f9-123">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="f97f9-124">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f97f9-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f97f9-125">使用 Windows PowerShell Cmdlet 启用和禁用关键模式</span><span class="sxs-lookup"><span data-stu-id="f97f9-125">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f97f9-126">你可以使用**CsArchivingConfiguration** cmdlet 启用或禁用关键模式。</span><span class="sxs-lookup"><span data-stu-id="f97f9-126">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="f97f9-127">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f97f9-127">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f97f9-128">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="f97f9-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="f97f9-129">启用关键模式</span><span class="sxs-lookup"><span data-stu-id="f97f9-129">To enable critical mode</span></span>

  - <span data-ttu-id="f97f9-130">若要启用关键模式, 请将 BlockOnArchiveFailure 属性的值设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="f97f9-130">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="f97f9-131">例如：</span><span class="sxs-lookup"><span data-stu-id="f97f9-131">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="f97f9-132">禁用关键模式</span><span class="sxs-lookup"><span data-stu-id="f97f9-132">To disable critical mode</span></span>

  - <span data-ttu-id="f97f9-133">若要禁用关键模式, 请将 BlockOnArchiveFailure 属性的值设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="f97f9-133">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="f97f9-134">例如：</span><span class="sxs-lookup"><span data-stu-id="f97f9-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="f97f9-135">有关详细信息, 请参阅[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f97f9-135">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f97f9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f97f9-136">See Also</span></span>


[<span data-ttu-id="f97f9-137">在 Lync Server 2013 中更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="f97f9-137">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="f97f9-138">在 Lync Server 2013 中存档的工作方式</span><span class="sxs-lookup"><span data-stu-id="f97f9-138">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="f97f9-139">管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="f97f9-139">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

