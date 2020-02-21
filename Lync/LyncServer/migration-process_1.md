---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ea0dd9dee35693fadedd13f6026ebb0d9f211d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="678d1-102">迁移过程</span><span class="sxs-lookup"><span data-stu-id="678d1-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="678d1-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="678d1-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="678d1-104">Lync Server 2013 的推荐和受支持的迁移过程是并行迁移过程。</span><span class="sxs-lookup"><span data-stu-id="678d1-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="678d1-105">本主题介绍为什么应使用并行迁移，还包括有关共存的信息。</span><span class="sxs-lookup"><span data-stu-id="678d1-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="678d1-106">并行迁移</span><span class="sxs-lookup"><span data-stu-id="678d1-106">Side-by-Side Migration</span></span>

<span data-ttu-id="678d1-107">在几乎每个迁移中，都应该使用并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="678d1-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="678d1-108">在并行迁移中，可以使用 Lync Server 2013 和运行 Office 通信 Server 2007 R2 的相应服务器一起部署新的服务器，然后将操作转移到新服务器。</span><span class="sxs-lookup"><span data-stu-id="678d1-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="678d1-109">如果有必要回滚到 Office 通信服务器 2007 R2，您只需将操作转移回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="678d1-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="678d1-110">请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。</span><span class="sxs-lookup"><span data-stu-id="678d1-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="678d1-111">共存测试</span><span class="sxs-lookup"><span data-stu-id="678d1-111">Coexistence Testing</span></span>

<span data-ttu-id="678d1-112">在与 Office 通信服务器 2007 R2 并行部署 Lync Server 2013 之后，该拓扑表示 Lync Server 2013 和 Office 通信服务器 2007 R2 的共存测试状态。</span><span class="sxs-lookup"><span data-stu-id="678d1-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="678d1-113">在这种状态下，必须测试并确保服务已启动，这一点很重要；可以管理每个站点，并且客户端可以与当前用户和旧用户通信。</span><span class="sxs-lookup"><span data-stu-id="678d1-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="678d1-114">在迁移所有用户之前，必须了解每个部署的状态和确保每个部署正常运行，这点非常重要。</span><span class="sxs-lookup"><span data-stu-id="678d1-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="678d1-115">通常情况下，共存测试阶段在 Lync Server 2013 的试点测试中存在。</span><span class="sxs-lookup"><span data-stu-id="678d1-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="678d1-116">旧版用户在一段时间内被移动到 Lync Server 2013，以确保应用程序兼容性和功能和功能正常运行。</span><span class="sxs-lookup"><span data-stu-id="678d1-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="678d1-117">完成试点测试后，用户和应用程序将移至 Lync Server 2013 的生产版本，并且旧池和 Office 通信服务器 2007 R2 的应用程序将停用。</span><span class="sxs-lookup"><span data-stu-id="678d1-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

