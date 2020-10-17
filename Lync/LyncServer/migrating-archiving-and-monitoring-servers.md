---
title: 迁移存档和监控服务器
description: 迁移存档和监控服务器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabd16fd38dbf463a4bc608fe77368e781571fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565378"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="e253b-103">迁移存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="e253b-103">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e253b-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e253b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e253b-105">如果您在 Lync Server 2010 环境中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。</span><span class="sxs-lookup"><span data-stu-id="e253b-105">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="e253b-106">但是，如果存档和监视功能对您的组织至关重要，那么在迁移之前，应在您的 Lync Server 2013 试点池中添加存档和监控功能，以便在迁移过程中使用该功能。</span><span class="sxs-lookup"><span data-stu-id="e253b-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="e253b-107">如果迁移过程中需要存档和监控功能，应注意以下问题：</span><span class="sxs-lookup"><span data-stu-id="e253b-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="e253b-108">存档数据和监控数据不会移动到 Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="e253b-108">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="e253b-109">在停用旧环境之前备份的数据将成为 Lync Server 2010 环境中的活动历史记录。</span><span class="sxs-lookup"><span data-stu-id="e253b-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="e253b-110">Lync Server 2010 版本的存档服务器和监视服务器只能与 Lync Server 2010 前端池关联。</span><span class="sxs-lookup"><span data-stu-id="e253b-110">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="e253b-111">在 Lync Server 2013 中，存档和监控不再是服务器角色，而是集成到 Lync Server 2013 前端池的服务。</span><span class="sxs-lookup"><span data-stu-id="e253b-111">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="e253b-112">在旧版和 Lync Server 2013 部署共存期间，存档服务器和监视服务器的 Lync Server 2010 版本将为驻留在 Lync Server 2010 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="e253b-112">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="e253b-113">Lync Server 2013 中的存档和监控为驻留在 Lync Server 2013 池上的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="e253b-113">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e253b-114">在迁移阶段，如果你仍在使用新的 Lync Server 2013 试点池时使用旧版边缘服务器，则存档服务器的 Lync Server 2010 版本将继续为驻留2010在 lync server 中的用户收集数据。2013在 lync server 中的池和存档中，为驻留在 Lync Server 2013 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="e253b-114">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="e253b-115">如果将第三方存档和监控解决方案与 Lync Server 2013 中的存档和监控结合使用，请咨询您的供应商，了解何时以及如何将第三方解决方案与 Lync Server 2013 集成。</span><span class="sxs-lookup"><span data-stu-id="e253b-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

