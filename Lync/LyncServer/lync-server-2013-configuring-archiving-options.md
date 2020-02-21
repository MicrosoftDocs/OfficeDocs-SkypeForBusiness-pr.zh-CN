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
ms.openlocfilehash: dd70d2742e54da801f80b07f1a00b97e0d91a990
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="f1bbc-102">在 Lync Server 2013 中配置存档选项</span><span class="sxs-lookup"><span data-stu-id="f1bbc-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1bbc-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f1bbc-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f1bbc-104">在 Lync Server 2013 控制面板中，可以使用存档配置来指定如何实施存档。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="f1bbc-105">这包括以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="f1bbc-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f1bbc-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f1bbc-107">您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f1bbc-108">存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f1bbc-109">在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档配置**" 页来管理全局级别、站点级别和池级别的配置。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="f1bbc-110">有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="f1bbc-111">有关如何在部署后管理配置的详细信息，请参阅 Operations 文档中的在[Lync Server 2013 中管理存档配置选项（针对组织、网站和池](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)）。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1bbc-112">若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="f1bbc-113">默认情况下，不会为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f1bbc-114">在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f1bbc-115">有关启用存档的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f1bbc-116">如果您的部署中的所有用户不使用 Microsoft Exchange 集成，则必须配置存档策略，以指定是为内部通信启用存档，还是对二者启用存档。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="f1bbc-117">默认情况下，在使用 Lync Server 2013 存档数据库时，不会为内部或外部通信启用存档来存档数据。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="f1bbc-118">在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f1bbc-119">有关启用存档以用于 Lync Server 2013 存档数据库的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync server 2013 中配置和分配存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="f1bbc-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1bbc-120">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f1bbc-120">In This Section</span></span>

  - [<span data-ttu-id="f1bbc-121">在 Lync Server 2013 中配置全局级别的存档选项</span><span class="sxs-lookup"><span data-stu-id="f1bbc-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="f1bbc-122">在 Lync Server 2013 中配置网站的存档选项</span><span class="sxs-lookup"><span data-stu-id="f1bbc-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="f1bbc-123">在 Lync Server 2013 中配置池的存档选项</span><span class="sxs-lookup"><span data-stu-id="f1bbc-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

