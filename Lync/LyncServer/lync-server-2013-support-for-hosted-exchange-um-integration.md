---
title: Lync Server 2013 支持托管 Exchange UM 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 714b10cfc10e101439670eda6ff3810be06b8599
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="aa84e-102">在 Lync Server 2013 中支持托管 Exchange UM 集成</span><span class="sxs-lookup"><span data-stu-id="aa84e-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa84e-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="aa84e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="aa84e-104">Lync Server 2013 ExUM 路由应用程序支持与 Exchange 统一消息（UM）集成在本地环境中，其中 Lync Server 2013 和 Exchange UM 都在本地安装在企业内部，或在 Exchange UM 中托管。服务提供程序，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="aa84e-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="aa84e-105">![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="aa84e-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="aa84e-106">支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="aa84e-106">The following modes are supported:</span></span>

  - <span data-ttu-id="aa84e-107">**本地模式**   Lync Server 2013 和 Exchange UM 都部署在企业中的本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="aa84e-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="aa84e-108">**跨界模式**   Lync Server 2013 部署在企业内的本地服务器上，Exchange UM 托管在联机服务提供商的设施中，如 Microsoft Exchange online 数据中心。</span><span class="sxs-lookup"><span data-stu-id="aa84e-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="aa84e-109">**混合模式**   ： Lync Server 2013 部署在企业中的本地服务器上托管一些用户邮箱，并且某些邮箱驻留在托管 Exchange service 数据中心中。</span><span class="sxs-lookup"><span data-stu-id="aa84e-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa84e-110">在评估和 stepwise 用户迁移到托管 Exchange UM 的过程中，混合模式可用作过渡解决方案，如果您选择在迁移其他用户之前将某些用户的 Exchange UM 服务保留在本地，则为永久解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa84e-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="aa84e-111">若要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置*共享 SIP 地址空间*（也称为*拆分域*）。</span><span class="sxs-lookup"><span data-stu-id="aa84e-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="aa84e-112">在此配置中，Lync Server 2013 和第三方托管 Exchange UM 服务提供商都可以访问相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="aa84e-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="aa84e-113">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中托管 EXCHANGE UM 集成体系结构](lync-server-2013-hosted-exchange-um-integration-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="aa84e-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

