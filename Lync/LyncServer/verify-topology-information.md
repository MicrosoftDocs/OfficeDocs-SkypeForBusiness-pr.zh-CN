---
title: 验证拓扑信息
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ef4c2884d9810793b6431c9d518c92bdcd1a3a4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518039"
---
# <a name="verify-topology-information"></a><span data-ttu-id="e6662-102">验证拓扑信息</span><span class="sxs-lookup"><span data-stu-id="e6662-102">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6662-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e6662-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e6662-104">成功完成合并验证的第一步是查看与 Lync Server 2013 合并的 Office 通信服务器 2007 R2 拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="e6662-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="e6662-105">在拓扑生成器中， **BackCompatSite** 节点显示您合并的每个 Office 通信服务器 2007 R2 池和服务器的完全限定域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="e6662-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="e6662-106">在拓扑生成器中查看 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="e6662-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="e6662-107">在 Office 通信服务器 2007 R2 环境中，打开 Office 通信服务器 2007 R2 管理工具，并记下旧版池和服务器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="e6662-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="e6662-108">在 Lync Server 2013 环境中，打开拓扑生成器，然后展开 " **BackCompatSite** " 节点。</span><span class="sxs-lookup"><span data-stu-id="e6662-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="e6662-109">验证您合并的池和服务器的 FQDN 是否显示。</span><span class="sxs-lookup"><span data-stu-id="e6662-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6662-110">您不会在 <STRONG>BackCompatSite</STRONG> 中看到在前端服务器或 Standard Edition server 上并置的服务器角色的任何信息。</span><span class="sxs-lookup"><span data-stu-id="e6662-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="e6662-111">仅显示 Office 通信服务器 2007 R2 和 Lync Server 2013 之间的互操作性所需的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e6662-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="e6662-112">!["拓扑生成器 BackCompatSite" 对话框](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg ""拓扑生成器 BackCompatSite" 对话框")</span><span class="sxs-lookup"><span data-stu-id="e6662-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="e6662-113">您还可以使用 Lync Server 2013 控制面板查看合并的拓扑。</span><span class="sxs-lookup"><span data-stu-id="e6662-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="e6662-114">在 Lync Server 2013 控制面板中，可以看到合并拓扑的每个服务器 FQDN、池 FQDN 和站点名称。</span><span class="sxs-lookup"><span data-stu-id="e6662-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="e6662-115">合并的服务器的“站点”\*\*\*\* 名称为“BackCompatSite”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e6662-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="e6662-116">在 Lync Server 2013 "控制面板" 中查看合并的拓扑</span><span class="sxs-lookup"><span data-stu-id="e6662-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e6662-117">打开 "Lync Server 2013 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e6662-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="e6662-118">单击“拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e6662-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="e6662-119">在“状态”\*\*\*\* 选项卡上，通过在“站点”\*\*\*\* 列中查找 **BackCompatSite** 来验证合并的服务器和池是否显示。</span><span class="sxs-lookup"><span data-stu-id="e6662-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="e6662-120">![显示合并拓扑的 "Lync Server 控制面板"](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "显示合并拓扑的 "Lync Server 控制面板"")</span><span class="sxs-lookup"><span data-stu-id="e6662-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="e6662-121">要查看有关合并的池的更多详细信息，请使用 **Get-CsPool** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6662-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="e6662-122">除了拓扑生成器和 Lync Server 2013 控制面板中提供的信息外，此 cmdlet 还会显示在 Lync Server 2013 池中运行的服务。</span><span class="sxs-lookup"><span data-stu-id="e6662-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6662-123">在拓扑生成器中运行合并向导之后发布拓扑时，会议目录将合并到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e6662-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="e6662-124">可以通过运行 <STRONG>new-csconferencedirectory</STRONG> cmdlet 来验证会议目录。</span><span class="sxs-lookup"><span data-stu-id="e6662-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="e6662-125">查看合并的池中的服务</span><span class="sxs-lookup"><span data-stu-id="e6662-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="e6662-126">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e6662-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e6662-127">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6662-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="e6662-128">例如：</span><span class="sxs-lookup"><span data-stu-id="e6662-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="e6662-129">验证合并的会议目录</span><span class="sxs-lookup"><span data-stu-id="e6662-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="e6662-130">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e6662-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e6662-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e6662-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="e6662-132">验证正在合并的池或服务器的所有会议目录现在是否在 Lync Server 2013 中。</span><span class="sxs-lookup"><span data-stu-id="e6662-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

