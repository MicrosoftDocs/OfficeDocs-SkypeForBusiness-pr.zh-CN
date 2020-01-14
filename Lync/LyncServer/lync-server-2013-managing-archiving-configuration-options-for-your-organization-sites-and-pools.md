---
title: Lync Server 2013：管理你的组织、网站和池的存档配置选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d27ea110c345be8963c5b3be3fa8b761e1b3727
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="c3325-102">管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="c3325-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3325-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3325-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3325-104">在 Lync Server 2013 "控制面板" 中，使用存档配置来指定如何实施存档。</span><span class="sxs-lookup"><span data-stu-id="c3325-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="c3325-105">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="c3325-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="c3325-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="c3325-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c3325-107">可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。</span><span class="sxs-lookup"><span data-stu-id="c3325-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="c3325-108">你在部署存档时开始设置存档配置，但你可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="c3325-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="c3325-109">在 Lync Server 2013 "控制面板" 中，可以使用 "**存档和监视**" 组的 "**存档配置**" 页来管理全局级别、网站级别和池级别的配置。</span><span class="sxs-lookup"><span data-stu-id="c3325-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="c3325-110">有关如何实现存档配置的详细信息（包括你可以指定哪些选项以及存档配置的层次结构），请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="c3325-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3325-111">若要使用存档，必须配置存档策略，以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的所有用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="c3325-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="c3325-112">默认情况下，不会为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="c3325-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="c3325-113">如果使用 Microsoft Exchange 集成，则必须启用和配置 Exchange 2013 以支持驻留在 Exchange 2013 上的所有用户的邮箱放置在原地保留中的所有用户的存档。</span><span class="sxs-lookup"><span data-stu-id="c3325-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="c3325-114">在启用存档之前，你应该为你的部署指定适当的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="c3325-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="c3325-115">有关启用存档的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="c3325-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c3325-116">**使用 Windows PowerShell cmdlet 查看存档配置信息**</span><span class="sxs-lookup"><span data-stu-id="c3325-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="c3325-117">你可以使用 Windows PowerShell 和**CsArchivingConfiguration** Cmdlet 查看存档配置信息。</span><span class="sxs-lookup"><span data-stu-id="c3325-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="c3325-118">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3325-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c3325-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="c3325-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c3325-120">在 Lync Server Management Shell 中，使用以下命令查看有关所有存档配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="c3325-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3325-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="c3325-121">In This Section</span></span>

  - [<span data-ttu-id="c3325-122">在 Lync Server 2013 中创建存档配置以管理特定网站或池的存档</span><span class="sxs-lookup"><span data-stu-id="c3325-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="c3325-123">在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档</span><span class="sxs-lookup"><span data-stu-id="c3325-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="c3325-124">在 Lync Server 2013 中启用或禁用已存档数据的清除</span><span class="sxs-lookup"><span data-stu-id="c3325-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="c3325-125">启用或禁用 Lync Server 2013 中的关键模式，以阻止或允许 IM 和网络会议会话（如果存档失败）</span><span class="sxs-lookup"><span data-stu-id="c3325-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="c3325-126">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="c3325-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="c3325-127">启用或禁用 Lync Server 2013 与 Exchange 存储的集成</span><span class="sxs-lookup"><span data-stu-id="c3325-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="c3325-128">在 Lync Server 2013 中删除存档配置</span><span class="sxs-lookup"><span data-stu-id="c3325-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3325-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3325-129">See Also</span></span>


[<span data-ttu-id="c3325-130">管理 Lync Server 2013 存档</span><span class="sxs-lookup"><span data-stu-id="c3325-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

