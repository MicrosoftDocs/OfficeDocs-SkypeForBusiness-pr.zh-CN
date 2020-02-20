---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799f2258344d94f4dcfc0e477bd3e77316c3a060
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="74cfd-102">迁移存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="74cfd-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cfd-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="74cfd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="74cfd-104">如果在 Office 通信服务器 2007 R2 中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。</span><span class="sxs-lookup"><span data-stu-id="74cfd-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="74cfd-105">不过，如果存档和监控功能对您的组织至关重要，则应在迁移之前在试点池中添加存档和监控，以便迁移过程中可使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="74cfd-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="74cfd-106">如果在迁移和共存阶段需要存档和监控功能，应注意以下问题：</span><span class="sxs-lookup"><span data-stu-id="74cfd-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="74cfd-107">存档数据和监控数据不会移动到 Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="74cfd-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="74cfd-108">在您解除旧环境之前备份的数据将是 Office 通信服务器 2007 R2 中的活动历史记录。</span><span class="sxs-lookup"><span data-stu-id="74cfd-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="74cfd-109">Office 通信服务器 2007 R2 版本的存档服务器和监视服务器只能与 Office 通信服务器 2007 R2 前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="74cfd-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="74cfd-110">在 Lync Server 2013 中，存档和监控不再是服务器角色，而是集成到 Lync Server 2013 前端池的服务。</span><span class="sxs-lookup"><span data-stu-id="74cfd-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="74cfd-111">在旧版和 Lync Server 2013 部署共存期间，存档服务器和监视服务器的 Office 通信服务器 2007 R2 版本将为驻留在 Office 通信服务器上的用户收集数据，以 2007 R2 池。</span><span class="sxs-lookup"><span data-stu-id="74cfd-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="74cfd-112">Lync Server 2013 版本的存档服务器和监视服务器为驻留在 Lync Server 2013 池上的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="74cfd-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74cfd-113">在迁移阶段，如果你仍在使用新的 Lync Server 2013 试点池时使用旧版边缘服务器，则存档服务器的 Office 通信服务器 2007 R2 版本将继续为驻留在 Office 通信服务器上的用户收集数据。2007R2 池和 Lync Server 2013 版本的存档服务器为驻留在 Lync Server 2013 池上的用户收集数据。</span><span class="sxs-lookup"><span data-stu-id="74cfd-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="74cfd-114">如果将第三方存档和监控解决方案与存档服务器和监视服务器结合使用，请与供应商联系，了解何时以及如何使用 Lync Server 2013 集成第三方解决方案。</span><span class="sxs-lookup"><span data-stu-id="74cfd-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

