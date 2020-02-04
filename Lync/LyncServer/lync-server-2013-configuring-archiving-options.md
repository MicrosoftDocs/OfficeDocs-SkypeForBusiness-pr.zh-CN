---
title: Lync Server 2013：配置存档选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa49aceacbd5053ead1af6b881be87c74b2ea30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="0c0b4-102">在 Lync Server 2013 中配置存档选项</span><span class="sxs-lookup"><span data-stu-id="0c0b4-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c0b4-103">_**主题上次修改时间：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0c0b4-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0c0b4-104">在 Lync Server 2013 "控制面板" 中，使用存档配置来指定如何实施存档。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="0c0b4-105">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="0c0b4-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="0c0b4-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0c0b4-107">可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="0c0b4-108">你在部署存档时开始设置存档配置，但你可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="0c0b4-109">在 Lync Server 2013 "控制面板" 中，可以使用 "**存档和监视**" 组的 "**存档配置**" 页来管理全局级别、网站级别和池级别的配置。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="0c0b4-110">有关如何实现存档配置的详细信息，包括你可以指定哪些选项和存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="0c0b4-111">有关如何在部署后管理配置的详细信息，请参阅操作文档中的[组织、网站和池的 Lync Server 2013 中的 "管理存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)"。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c0b4-112">若要使用存档，必须配置存档策略以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="0c0b4-113">默认情况下，不会为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="0c0b4-114">在任何策略中启用存档之前，应为你的部署指定相应的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0c0b4-115">有关启用存档的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0c0b4-116">如果你不为部署中的所有用户使用 Microsoft Exchange 集成，则必须配置存档策略，以指定是为内部通信还是在外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="0c0b4-117">默认情况下，在使用 Lync Server 2013 存档数据库时，不会为内部或外部通信启用存档，以便存档数据。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="0c0b4-118">在任何策略中启用存档之前，应为你的部署指定相应的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0c0b4-119">有关启用用于 Lync Server 2013 存档数据库的存档的详细信息，请参阅在部署文档中<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配 Lync server 2013 中的存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="0c0b4-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c0b4-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c0b4-120">In This Section</span></span>

  - [<span data-ttu-id="0c0b4-121">在 Lync Server 2013 的全局级别配置存档选项</span><span class="sxs-lookup"><span data-stu-id="0c0b4-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="0c0b4-122">在 Lync Server 2013 中配置网站的存档选项</span><span class="sxs-lookup"><span data-stu-id="0c0b4-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="0c0b4-123">在 Lync Server 2013 中配置池的存档选项</span><span class="sxs-lookup"><span data-stu-id="0c0b4-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

