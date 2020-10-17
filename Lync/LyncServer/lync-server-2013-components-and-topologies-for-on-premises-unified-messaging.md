---
title: Lync Server 2013：本地统一消息的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7b4c62daf2ed5bdc7416a704e2c70f18802419
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502509"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="da69b-102">Lync Server 2013 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="da69b-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da69b-103">_**上次修改的主题：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="da69b-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="da69b-104">本主题介绍了向 Lync Server 2013 部署提供 Exchange 统一消息 (UM) 功能所需的 Microsoft Exchange Server 2013 组件。</span><span class="sxs-lookup"><span data-stu-id="da69b-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="da69b-105">此外，它还介绍了本地 Exchange UM 集成支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="da69b-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="da69b-106">Exchange Server 组件</span><span class="sxs-lookup"><span data-stu-id="da69b-106">Exchange Server Components</span></span>

<span data-ttu-id="da69b-107">若要将 [集成统一消息和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md) 中所述的 Exchange UM 功能和服务提供给组织中的企业语音用户，您必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，以承载用户邮箱并为电子邮件和语音邮件提供一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="da69b-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="da69b-108">Exchange UM 在 Exchange 邮箱和客户端访问服务器上作为一项服务运行。</span><span class="sxs-lookup"><span data-stu-id="da69b-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="da69b-109">有关 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅部署文档中的 [部署本地 EXCHANGE um 以提供 Lync Server 2013 语音邮件](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 。</span><span class="sxs-lookup"><span data-stu-id="da69b-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="da69b-110">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="da69b-110">Supported Topologies</span></span>

<span data-ttu-id="da69b-111">您可以在同一林中或多个林中部署 Lync Server 2013 和 Exchange 统一消息 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="da69b-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="da69b-112">如果部署跨越多个林，则必须为每个 Exchange UM 林执行 Exchange 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="da69b-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="da69b-113">此外，还必须将每个 Microsoft Exchange 林配置为信任 Lync Server 2013 林，并将 Lync Server 2013 林配置为信任每个 Exchange UM 林。</span><span class="sxs-lookup"><span data-stu-id="da69b-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="da69b-114">除了此林信任之外，还必须对 Lync Server 2013 林中的用户对象设置所有用户的 Exchange UM 设置。</span><span class="sxs-lookup"><span data-stu-id="da69b-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="da69b-115">Lync Server 2013 支持 Exchange UM 集成的以下拓扑：</span><span class="sxs-lookup"><span data-stu-id="da69b-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="da69b-116">单林</span><span class="sxs-lookup"><span data-stu-id="da69b-116">Single forest</span></span>

  - <span data-ttu-id="da69b-117">单域（即具有单个域的单林）。</span><span class="sxs-lookup"><span data-stu-id="da69b-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="da69b-118">Lync Server 2013、Microsoft Exchange 和用户都驻留在同一域中。</span><span class="sxs-lookup"><span data-stu-id="da69b-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="da69b-119">多域（即具有一个或多个子域的根域）。</span><span class="sxs-lookup"><span data-stu-id="da69b-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="da69b-120">Lync Server 2013 和 Microsoft Exchange 服务器部署在您创建用户的域的不同域中。</span><span class="sxs-lookup"><span data-stu-id="da69b-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="da69b-121">Exchange UM 服务器可以部署在其支持的 Lync Server 2013 池的不同域中。</span><span class="sxs-lookup"><span data-stu-id="da69b-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="da69b-122">多林（即资源林）。</span><span class="sxs-lookup"><span data-stu-id="da69b-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="da69b-123">在单个林中部署 Lync Server 2013，然后在多个林分布用户。</span><span class="sxs-lookup"><span data-stu-id="da69b-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="da69b-124">用户的 Exchange UM 属性必须复制到 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="da69b-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da69b-125">可在多个林中部署 Exchange。</span><span class="sxs-lookup"><span data-stu-id="da69b-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="da69b-126">每个 Exchange 组织可以向其用户提供 Exchange UM，也可以将 Exchange UM 部署在与 Lync Server 2013 相同的林中。</span><span class="sxs-lookup"><span data-stu-id="da69b-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

