---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8958fbf22e096a1d9fef03afd3aac3b4656ed0e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515929"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="cbb97-102">验证试点池与旧池的共存情况</span><span class="sxs-lookup"><span data-stu-id="cbb97-102">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbb97-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="cbb97-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="cbb97-104">部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。</span><span class="sxs-lookup"><span data-stu-id="cbb97-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="cbb97-105">对于 Lync Server 2013 池和旧版池，必须使用 Lync Server 2013 控制面板和拓扑生成器工具。</span><span class="sxs-lookup"><span data-stu-id="cbb97-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="cbb97-106">验证 Lync Server 2013 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="cbb97-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="cbb97-107">在 Lync Server 2013 前端服务器中，导航到 "管理工具 \\ 服务" 小程序。</span><span class="sxs-lookup"><span data-stu-id="cbb97-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="cbb97-108">确认以下服务正在前端服务器上运行：</span><span class="sxs-lookup"><span data-stu-id="cbb97-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="cbb97-109">**Lync Server 2013 服务**</span><span class="sxs-lookup"><span data-stu-id="cbb97-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="cbb97-110">![已启动 Lync Server 服务的列表](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "已启动 Lync Server 服务的列表")</span><span class="sxs-lookup"><span data-stu-id="cbb97-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="cbb97-111">打开 "Lync Server 2013 控制面板"</span><span class="sxs-lookup"><span data-stu-id="cbb97-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="cbb97-112">在 Lync Server 2013 部署的前端服务器中，打开 Lync Server 2013 控制面板并选择 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="cbb97-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="cbb97-113">重复此过程以打开 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cbb97-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="cbb97-114">**打开 Lync Server 2013 控制面板**</span><span class="sxs-lookup"><span data-stu-id="cbb97-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="cbb97-115">!["选择 URL" 对话框](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png ""选择 URL" 对话框")</span><span class="sxs-lookup"><span data-stu-id="cbb97-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cbb97-116">在 Lync Server 2013 上，您必须先将 Silverlight 升级到 Silverlight 版本5，然后再使用 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="cbb97-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="cbb97-117">此拓扑现在包括 Lync Server 2010 和 Lync Server 2013 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="cbb97-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="cbb97-118">**“Lync Server 2013 控制面板拓扑”页**</span><span class="sxs-lookup"><span data-stu-id="cbb97-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="cbb97-119">![Lync Server 控制面板-拓扑页面](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制面板-拓扑页面")</span><span class="sxs-lookup"><span data-stu-id="cbb97-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="cbb97-120">请勿尝试在 Lync Server 2010 拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="cbb97-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="cbb97-121">如果尝试使用 Lync Server 2010 拓扑生成器打开拓扑，将会遇到以下错误。</span><span class="sxs-lookup"><span data-stu-id="cbb97-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="cbb97-122">仅可使用 Lync Server 2013 拓扑生成器查看拓扑。</span><span class="sxs-lookup"><span data-stu-id="cbb97-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="cbb97-123">Lync Server 2013 拓扑生成器必须用于为 Lync Server 2013 和 Lync Server 2010 创建池。</span><span class="sxs-lookup"><span data-stu-id="cbb97-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="cbb97-124">**Lync Server 2010 拓扑生成器错误消息**</span><span class="sxs-lookup"><span data-stu-id="cbb97-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="cbb97-125">![Lync Server 拓扑生成器 MMC Snap 错误](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓扑生成器 MMC Snap 错误")</span><span class="sxs-lookup"><span data-stu-id="cbb97-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

