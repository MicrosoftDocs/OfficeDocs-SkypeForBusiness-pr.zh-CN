---
title: Lync Server 2013：管理组织、网站和池的存档配置选项
description: Lync Server 2013：管理组织、网站和池的存档配置选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576618"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="76006-103">在 Lync Server 2013 中管理组织、网站和池的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="76006-103">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76006-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="76006-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="76006-105">在 Lync Server 2013 控制面板中，可以使用存档配置来指定如何实施存档。</span><span class="sxs-lookup"><span data-stu-id="76006-105">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="76006-106">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="76006-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="76006-107">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="76006-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="76006-108">您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。</span><span class="sxs-lookup"><span data-stu-id="76006-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="76006-109">存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。</span><span class="sxs-lookup"><span data-stu-id="76006-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="76006-110">在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档配置**" 页来管理全局级别、站点级别和池级别的配置。</span><span class="sxs-lookup"><span data-stu-id="76006-110">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="76006-111">有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="76006-111">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76006-112">若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的所有用户都启用存档。</span><span class="sxs-lookup"><span data-stu-id="76006-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="76006-113">默认情况下，不对内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="76006-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="76006-114">如果使用 Microsoft Exchange 集成，则必须启用和配置 Exchange 2013，以支持驻留在 Exchange 2013 上的所有用户的邮箱放在 In-Place 保留状态的存档。</span><span class="sxs-lookup"><span data-stu-id="76006-114">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="76006-115">如本节中所述，在启用存档之前，应该为您的部署指定相应存档配置，并且还可以选择为特定站点和池指定相应存档配置。</span><span class="sxs-lookup"><span data-stu-id="76006-115">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="76006-116">有关启用存档的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="76006-116">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="76006-117">**使用 Windows PowerShell cmdlet 查看存档配置信息**</span><span class="sxs-lookup"><span data-stu-id="76006-117">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="76006-118">您可以使用 Windows PowerShell 和 **set-csarchivingconfiguration** Cmdlet 查看存档配置信息。</span><span class="sxs-lookup"><span data-stu-id="76006-118">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="76006-119">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76006-119">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76006-120">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="76006-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="76006-121">在 Lync Server 命令行管理程序中，使用以下命令查看有关所有存档配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="76006-121">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="76006-122">本部分内容</span><span class="sxs-lookup"><span data-stu-id="76006-122">In This Section</span></span>

  - [<span data-ttu-id="76006-123">在 Lync Server 2013 中创建存档配置，以管理特定网站或池的存档</span><span class="sxs-lookup"><span data-stu-id="76006-123">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="76006-124">在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档</span><span class="sxs-lookup"><span data-stu-id="76006-124">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="76006-125">在 Lync Server 2013 中启用或禁用已存档数据的清除</span><span class="sxs-lookup"><span data-stu-id="76006-125">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="76006-126">启用或禁用 Lync Server 2013 中的关键模式以阻止或允许 IM 和 web 会议会话（如果存档失败）</span><span class="sxs-lookup"><span data-stu-id="76006-126">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="76006-127">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="76006-127">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="76006-128">启用或禁用与 Exchange 存储的 Lync Server 2013 集成</span><span class="sxs-lookup"><span data-stu-id="76006-128">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="76006-129">在 Lync Server 2013 中删除存档配置</span><span class="sxs-lookup"><span data-stu-id="76006-129">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76006-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76006-130">See Also</span></span>


[<span data-ttu-id="76006-131">管理 Lync Server 2013 存档</span><span class="sxs-lookup"><span data-stu-id="76006-131">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

