---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53021b37baca7a859c79a6c47bfbf3d587a3466d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="a633a-102">迁移过程</span><span class="sxs-lookup"><span data-stu-id="a633a-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a633a-103">_**主题上次修改时间：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a633a-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a633a-104">Lync Server 2013 的推荐和支持的迁移过程是并行迁移。</span><span class="sxs-lookup"><span data-stu-id="a633a-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="a633a-105">本主题介绍了应使用并行迁移的原因，还包括有关共存测试的信息。</span><span class="sxs-lookup"><span data-stu-id="a633a-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="a633a-106">并行迁移</span><span class="sxs-lookup"><span data-stu-id="a633a-106">Side-By-Side Migration</span></span>

<span data-ttu-id="a633a-107">在几乎所有迁移中，都应使用并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="a633a-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="a633a-108">在并行迁移中，你将新服务器与运行 Lync server 2010 的相应服务器一起部署在 Lync Server 2013 旁边，然后将操作转移到新服务器。</span><span class="sxs-lookup"><span data-stu-id="a633a-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="a633a-109">如果需要回退到 Lync Server 2010，您只需将操作转移回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="a633a-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="a633a-110">请注意，在这种情况下，使用升级的客户安排的新会议将不起作用，并且客户端也需要降级。</span><span class="sxs-lookup"><span data-stu-id="a633a-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="a633a-111">共存测试</span><span class="sxs-lookup"><span data-stu-id="a633a-111">Coexistence Testing</span></span>

<span data-ttu-id="a633a-112">在与 Lync Server 2010 并行部署 Lync Server 2013 之后，该部署表示 Lync Server 2013 和 Lync Server 2010 的共存测试状态。</span><span class="sxs-lookup"><span data-stu-id="a633a-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="a633a-113">在此状态下，测试和确保服务已启动、可管理每个网站，并且客户端可以与当前用户和旧版用户进行通信非常重要。</span><span class="sxs-lookup"><span data-stu-id="a633a-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="a633a-114">在迁移所有用户之前，了解每个部署的状态非常重要，并确保每个部署都能正常运行。</span><span class="sxs-lookup"><span data-stu-id="a633a-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="a633a-115">通常，共存测试阶段存在于 Lync Server 2013 的试点测试中。</span><span class="sxs-lookup"><span data-stu-id="a633a-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="a633a-116">旧版用户在一段时间内被移动到 Lync Server 2013，以确保应用程序兼容性和功能和功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="a633a-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="a633a-117">试点测试后，用户和应用程序将移至 Lync Server 2013 的产品版本，并且 Lync Server 2010 的旧池和应用程序将被停用。</span><span class="sxs-lookup"><span data-stu-id="a633a-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

