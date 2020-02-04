---
title: Lync Server 2013：存档概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f718ac939fc665c0464d4986f51279d3afdee8a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="a87ad-102">Lync Server 2013 中的存档概述</span><span class="sxs-lookup"><span data-stu-id="a87ad-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a87ad-103">_**主题上次修改时间：** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="a87ad-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="a87ad-104">Lync Server 2013 中的存档提供了一种存档通过 Lync Server 2013 发送的通信的方式。</span><span class="sxs-lookup"><span data-stu-id="a87ad-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="a87ad-105">你可以在初始 Lync Server 2013 部署中实现存档，也可以将其添加到现有部署。</span><span class="sxs-lookup"><span data-stu-id="a87ad-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="a87ad-106">若要使用 Lync Server 2013 存档数据库（SQL Server 数据库）存储存档数据，请使用拓扑生成器将数据库添加到拓扑，然后再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a87ad-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="a87ad-107">如果你的所有用户都托管在 Exchange 2013 上，并且其邮箱置于原地保留，则不必更新你的拓扑，但仅需要启用 Microsoft Exchange 集成才能将已存档的数据存储在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="a87ad-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="a87ad-108">实现存档时，将其配置为指定存档内容。</span><span class="sxs-lookup"><span data-stu-id="a87ad-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="a87ad-109">默认情况下，不会存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="a87ad-109">By default, nothing is archived.</span></span> <span data-ttu-id="a87ad-110">使用 Lync Server 2013 控制面板配置和管理存档。</span><span class="sxs-lookup"><span data-stu-id="a87ad-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="a87ad-111">你可以实现内部通信、外部通信或两者的存档。</span><span class="sxs-lookup"><span data-stu-id="a87ad-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="a87ad-112">你可以配置整个组织的存档设置，也可以配置特定网站、特定池和特定用户和用户组的存档设置。</span><span class="sxs-lookup"><span data-stu-id="a87ad-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="a87ad-113">有关确定组织的相应选项的详细信息，请参阅在规划文档中[定义 Lync Server 2013 中的存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="a87ad-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="a87ad-114">有关如何实施存档策略和配置的详细信息以及有关哪些信息可以或无法存档的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="a87ad-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

