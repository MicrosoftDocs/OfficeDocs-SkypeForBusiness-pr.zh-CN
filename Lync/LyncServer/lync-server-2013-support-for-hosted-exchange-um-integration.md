---
title: 托管 Exchange UM 集成的 Lync Server 2013 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="72950-102">Lync Server 2013 中的托管 Exchange UM 集成支持</span><span class="sxs-lookup"><span data-stu-id="72950-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72950-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="72950-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="72950-104">Lync Server 2013 ExUM 路由应用程序支持与 Exchange 统一消息 (UM) 在本地环境中进行集成, 其中 Lync Server 2013 和 Exchange UM 都安装在您的企业内部, 或者在托管的 Exchange UM 中由服务提供商, 如下图所示。</span><span class="sxs-lookup"><span data-stu-id="72950-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="72950-105">![本地 Lync Server EXCHANGE UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server EXCHANGE UM 部署")</span><span class="sxs-lookup"><span data-stu-id="72950-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="72950-106">支持下列模式:</span><span class="sxs-lookup"><span data-stu-id="72950-106">The following modes are supported:</span></span>

  - <span data-ttu-id="72950-107">**本地模式**   Lync Server 2013 和 Exchange UM 均部署在企业内的本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="72950-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="72950-108">**跨平台模式**   Lync Server 2013 部署在你的企业内的本地服务器上, Exchange UM 托管在一个联机服务提供商的设备 (如 Microsoft Exchange online 数据中心) 中。</span><span class="sxs-lookup"><span data-stu-id="72950-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="72950-109">**混合模式**   您的 Lync Server 2013 部署在您的企业中的本地服务器上有一些用户邮箱, 并且某些邮箱驻留在托管 Exchange 服务数据中心中。</span><span class="sxs-lookup"><span data-stu-id="72950-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72950-110">在评估和 stepwise 用户迁移到托管 Exchange UM 的过程中, 混合模式可用作过渡式解决方案, 如果你选择在迁移其他用户之后将某些用户的 Exchange UM 服务保留在本地, 则为永久解决方案。</span><span class="sxs-lookup"><span data-stu-id="72950-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="72950-111">若要将 Lync Server 2013 与托管 Exchange UM 集成, 必须配置*共享 SIP 地址空间*(也称为*拆分域*)。</span><span class="sxs-lookup"><span data-stu-id="72950-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="72950-112">在此配置中, Lync Server 2013 和第三方托管 Exchange UM 服务提供商可以访问相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="72950-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="72950-113">有关详细信息, 请参阅规划文档中的[Lync Server 2013 中的托管 EXCHANGE UM 集成体系结构](lync-server-2013-hosted-exchange-um-integration-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="72950-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

