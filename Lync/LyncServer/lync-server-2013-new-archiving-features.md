---
title: Lync Server 2013：新的存档功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="4dc47-102">Lync Server 2013 中新的存档功能</span><span class="sxs-lookup"><span data-stu-id="4dc47-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc47-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="4dc47-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="4dc47-104">Lync Server 2013 中的存档可存档以下类型的内容:</span><span class="sxs-lookup"><span data-stu-id="4dc47-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="4dc47-105">对等即时消息</span><span class="sxs-lookup"><span data-stu-id="4dc47-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="4dc47-106">多方即时消息的会议 (会议)</span><span class="sxs-lookup"><span data-stu-id="4dc47-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="4dc47-107">会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）</span><span class="sxs-lookup"><span data-stu-id="4dc47-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="4dc47-108">此外, Lync Server 2013 中的存档提供了可提高部署和操作效率的新功能。</span><span class="sxs-lookup"><span data-stu-id="4dc47-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="4dc47-109">这些新功能包括:</span><span class="sxs-lookup"><span data-stu-id="4dc47-109">These new features consist of:</span></span>

  - <span data-ttu-id="4dc47-110">**Collocation 前端服务器上的存档。**   Lync Server 2013 没有单独的存档服务器角色。</span><span class="sxs-lookup"><span data-stu-id="4dc47-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="4dc47-111">存档是在企业版部署中的所有前端服务器上提供的可选功能, 也可以在标准版服务器上实现, 可以为池或网站进行配置。</span><span class="sxs-lookup"><span data-stu-id="4dc47-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="4dc47-112">**Microsoft Exchange 集成。**   部署存档时, 可以为托管在 Exchange 2013 上的所有用户将数据存储与现有 exchange 2013 存储进行集成, 并将其邮箱置于原地保留, 因此无需部署单独的 SQL Server用于存档 Lync 数据的数据库。</span><span class="sxs-lookup"><span data-stu-id="4dc47-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="4dc47-113">如果你没有 Exchange 2013 部署, 或者你不希望与它集成, 或者如果你拥有的任何 Lync 2013 用户未托管在 Exchange 2013 上, 并且其邮箱放置在原地保留中, 你可以通过使用 SQL Server 使用 SQL Server 来部署单独的存档数据库 store 已存档 Lync 通信中的数据。</span><span class="sxs-lookup"><span data-stu-id="4dc47-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="4dc47-114">如果你想要对部署中的部分而非所有用户使用 Microsoft Exchange 集成, 则可以使用 Microsoft Exchange 集成和 Lync Server 2013 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="4dc47-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="4dc47-115">有关就地保留的详细信息, 请参阅的 "就地保留" [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)。</span><span class="sxs-lookup"><span data-stu-id="4dc47-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="4dc47-116">**SQL 应用商店镜像。**   部署存档时, 可以为存档数据库启用 SQL Server 数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="4dc47-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="4dc47-117">**白板和投票的存档。**   已存档的会议内容现在包括在会议期间共享的白板和投票。</span><span class="sxs-lookup"><span data-stu-id="4dc47-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="4dc47-118">以下类型的内容未存档:</span><span class="sxs-lookup"><span data-stu-id="4dc47-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="4dc47-119">对等文件传输</span><span class="sxs-lookup"><span data-stu-id="4dc47-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="4dc47-120">对等即时消息和会议的音频/视频</span><span class="sxs-lookup"><span data-stu-id="4dc47-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="4dc47-121">对等即时消息和会议的应用程序共享</span><span class="sxs-lookup"><span data-stu-id="4dc47-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4dc47-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc47-122">See Also</span></span>


[<span data-ttu-id="4dc47-123">在 Lync Server 2013 中规划存档</span><span class="sxs-lookup"><span data-stu-id="4dc47-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

