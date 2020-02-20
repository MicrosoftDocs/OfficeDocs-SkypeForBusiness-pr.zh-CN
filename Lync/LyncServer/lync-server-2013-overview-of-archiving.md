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
ms.openlocfilehash: a31ef3492ff4c6d0ced3dcf08dd385b7a6801ef6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="666f0-102">Lync Server 2013 中的存档概述</span><span class="sxs-lookup"><span data-stu-id="666f0-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="666f0-103">_**上次修改的主题：** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="666f0-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="666f0-104">Lync Server 2013 中的存档为您提供了一种存档通过 Lync Server 2013 发送的通信的方法。</span><span class="sxs-lookup"><span data-stu-id="666f0-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="666f0-105">您可以在最初的 Lync Server 2013 部署中实施存档，也可以将其添加到现有部署中。</span><span class="sxs-lookup"><span data-stu-id="666f0-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="666f0-106">若要使用 Lync Server 2013 存档数据库（SQL Server 数据库）来存储存档数据，请使用拓扑生成器将数据库添加到拓扑，然后重新发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="666f0-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="666f0-107">如果你的所有用户都托管在 Exchange 2013 上，并将其邮箱置于就地保留状态，则无需更新你的拓扑，但只需启用 Microsoft Exchange 集成即可在 Exchange 2013 中存储存档的数据。</span><span class="sxs-lookup"><span data-stu-id="666f0-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="666f0-108">部署存档时，需要配置存档以指定要存档的内容。</span><span class="sxs-lookup"><span data-stu-id="666f0-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="666f0-109">默认情况下，不对任何内容存档。</span><span class="sxs-lookup"><span data-stu-id="666f0-109">By default, nothing is archived.</span></span> <span data-ttu-id="666f0-110">您可以使用 Lync Server 2013 控制面板配置和管理存档。</span><span class="sxs-lookup"><span data-stu-id="666f0-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="666f0-111">可以针对内部通信和/或外部通信实施存档。</span><span class="sxs-lookup"><span data-stu-id="666f0-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="666f0-112">可以为您的整个组织和（可选）特定站点、特定池以及特定用户和用户组配置存档设置。</span><span class="sxs-lookup"><span data-stu-id="666f0-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="666f0-113">有关确定组织的相应选项的详细信息，请参阅规划文档中的在[Lync Server 2013 中定义存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="666f0-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="666f0-114">有关如何实施存档策略和配置的详细信息，以及有关哪些信息可以存档或无法存档的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="666f0-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

