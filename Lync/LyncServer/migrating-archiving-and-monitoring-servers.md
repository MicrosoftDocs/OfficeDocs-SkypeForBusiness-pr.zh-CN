---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="4f53a-102">迁移存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="4f53a-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f53a-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4f53a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4f53a-104">如果在 Lync Server 2010 环境中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。</span><span class="sxs-lookup"><span data-stu-id="4f53a-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="4f53a-105">但是，如果存档和监视功能对你的组织至关重要，则应在迁移之前将存档和监视添加到 Lync Server 2013 试验池，以便在迁移过程中使用该功能。</span><span class="sxs-lookup"><span data-stu-id="4f53a-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="4f53a-106">如果在迁移过程中需要存档和监视功能，请记住以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="4f53a-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="4f53a-107">存档数据和监视数据不会迁移到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="4f53a-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="4f53a-108">您在取消旧版环境之前备份的数据将是 Lync Server 2010 环境中的活动历史记录。</span><span class="sxs-lookup"><span data-stu-id="4f53a-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="4f53a-109">Lync Server 2010 版本的存档服务器和监视服务器只能与 Lync Server 2010 前端池关联。</span><span class="sxs-lookup"><span data-stu-id="4f53a-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="4f53a-110">在 Lync Server 2013 中，存档和监控不再是服务器角色，而是与 Lync Server 2013 前端池集成的服务。</span><span class="sxs-lookup"><span data-stu-id="4f53a-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="4f53a-111">在旧版本和 Lync Server 2013 部署共存期间，将在 Lync server 2010 版本的存档服务器和监视服务器上为驻留在 Lync Server 2010 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="4f53a-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="4f53a-112">Lync Server 2013 中的存档和监视为驻留在 Lync Server 2013 池中的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="4f53a-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f53a-113">在迁移阶段，当你仍将旧式 Edge 服务器与新的 Lync Server 2013 试验池配合使用时，存档服务器的 Lync Server 2010 版本会继续为驻留在 lync server 2010 池和存档中的用户收集数据（在 Lync Server 2013 中）为驻留在 Lync Server 2013 池的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="4f53a-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="4f53a-114">如果您将第三方存档和监视解决方案与 Lync Server 2013 中的存档和监视结合使用，请咨询您的供应商，了解何时以及如何将第三方解决方案与 Lync Server 2013 集成。</span><span class="sxs-lookup"><span data-stu-id="4f53a-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

