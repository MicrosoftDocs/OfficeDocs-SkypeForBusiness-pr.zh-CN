---
title: 在 Skype for Business 中规划 Exchange 统一消息集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要： 计划集成为 Exchange 2013 具有的业务服务器 2015 Skype 时仔细阅读本主题。
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="ded6a-103">在 Skype for Business 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="ded6a-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>
 
<span data-ttu-id="ded6a-104">**摘要：**计划为 Exchange 2013 具有的业务服务器 2015年集成 Skype 时仔细阅读本主题。</span><span class="sxs-lookup"><span data-stu-id="ded6a-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with Exchange 2013.</span></span>
  
<span data-ttu-id="ded6a-105">Skype 的业务服务器 2015年组合语音邮件和电子邮件消息到一个消息基础结构支持集成与 Exchange 统一消息 (UM)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-105">Skype for Business Server 2015 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="ded6a-106">在 Exchange 中，Exchange 统一消息 (UM) 是的您可以安装和配置多个 Exchange 服务器角色之一。</span><span class="sxs-lookup"><span data-stu-id="ded6a-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span> 
  
<span data-ttu-id="ded6a-107">在 Microsoft Exchange Server 2013，UM Exchange 作为服务运行的 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="ded6a-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="ded6a-108">对于业务服务器 2015年企业语音部署 Skype，语音邮件和电子邮件消息到一个用户可从电话 (Outlook Voice Access) 或计算机访问的单个存储区结合统一消息。</span><span class="sxs-lookup"><span data-stu-id="ded6a-108">For Skype for Business Server 2015 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="ded6a-109">统一消息传送、 业务服务器 2015年的 Skype 协同工作以提供企业语音的用户的呼叫应答、 Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="ded6a-109">Unified Messaging and Skype for Business Server 2015 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>
  
<span data-ttu-id="ded6a-110">有关 Microsoft Exchange Server 2013年的体系结构更改的详细信息，请参阅 Microsoft Exchange Server 2013年文档中的[语音体系结构更改](https://go.microsoft.com/fwlink/p/?LinkId=266730)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see [Voice Architecture Changes](https://go.microsoft.com/fwlink/p/?LinkId=266730) in the Microsoft Exchange Server 2013 documentation.</span></span>
  
<span data-ttu-id="ded6a-111">对于内部部署 UM Exchange 部署中必须支持这些功能，您必须运行以下任一项：</span><span class="sxs-lookup"><span data-stu-id="ded6a-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>
  
- <span data-ttu-id="ded6a-112">Microsoft Exchange Server 2010年上，或者新的服务包</span><span class="sxs-lookup"><span data-stu-id="ded6a-112">Microsoft Exchange Server 2010 or latest service pack</span></span>
    
- <span data-ttu-id="ded6a-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="ded6a-113">Microsoft Exchange Server 2013</span></span>
    
-  <span data-ttu-id="ded6a-114">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="ded6a-114">Microsoft Exchange Server 2016</span></span>
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="ded6a-115">集成统一消息和 Skype for Business Server 2015 的功能</span><span class="sxs-lookup"><span data-stu-id="ded6a-115">Features of integrated Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="ded6a-116">Skype 的业务服务器 2015，企业语音使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、 电话通知、 语音访问 （包括语音邮件），并自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="ded6a-116">Skype for Business Server 2015, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>
  
- <span data-ttu-id="ded6a-p103">**呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="ded6a-p103">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>
    
    <span data-ttu-id="ded6a-p104">如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。</span><span class="sxs-lookup"><span data-stu-id="ded6a-p104">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>
    
- <span data-ttu-id="ded6a-123">**Outlook Voice Access**Outlook Voice Access 使企业语音用户访问而不仅仅是语音邮件，但也的 Exchange 收件箱，包括电子邮件、 日历和联系人电话接口。</span><span class="sxs-lookup"><span data-stu-id="ded6a-123">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="ded6a-124">由 UM Exchange 管理员分配订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="ded6a-124">The subscriber access number is assigned by an Exchange UM administrator.</span></span>
    
- <span data-ttu-id="ded6a-125">**自动助理**自动助理是 UM 交换功能，可用于配置了电话号码，外部用户可以拨通公司代表。</span><span class="sxs-lookup"><span data-stu-id="ded6a-125">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="ded6a-126">特别是，它提供了一系列帮助外部呼叫者导航菜单系统的语音提示。</span><span class="sxs-lookup"><span data-stu-id="ded6a-126">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="ded6a-127">可用选项的列表由 UM Exchange 管理员配置 Exchange UM 服务器上。</span><span class="sxs-lookup"><span data-stu-id="ded6a-127">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>
    
- <span data-ttu-id="ded6a-128">**传真服务**嗯交换包括使用户能够在其 Exchange 邮箱中接收传入传真的传真功能。</span><span class="sxs-lookup"><span data-stu-id="ded6a-128">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="ded6a-129">有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-129">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ded6a-130">由 Exchange UM 服务器提供传真服务在中不可用 Skype 与 Microsoft Exchange Server 2010年、 Exchange 2010 与最新的 service pack 或 Exchange 2013 集成的业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="ded6a-130">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span> 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a><span data-ttu-id="ded6a-131">Skype for Business Server 2015 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="ded6a-131">Components and topologies for on-premises Unified Messaging in Skype for Business Server 2015</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="ded6a-132">Exchange Server 组件</span><span class="sxs-lookup"><span data-stu-id="ded6a-132">Exchange Server Components</span></span>

<span data-ttu-id="ded6a-133">若要提供的 UM Exchange 功能和服务[功能的集成统一消息和 Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx)中所述到您组织中的企业语音用户，您必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器其中驻留用户邮箱，并提供电子邮件和语音邮件的单个存储位置。</span><span class="sxs-lookup"><span data-stu-id="ded6a-133">To provide the Exchange UM features and services described in [Features of Integrated Unified Messaging and Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="ded6a-134">嗯交换作为一种服务将运行 Exchange 邮箱服务器和客户端访问服务器。</span><span class="sxs-lookup"><span data-stu-id="ded6a-134">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>
  
<span data-ttu-id="ded6a-135">有关 Exchange UM 在 Microsoft Exchange Server 2010年中的组件的详细信息，请参阅[部署内部 Exchange UM 提供 Lync 服务器 2013年预览语音邮件到](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="ded6a-135">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) in the Deployment documentation.</span></span>
  
### <a name="supported-topologies"></a><span data-ttu-id="ded6a-136">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="ded6a-136">Supported Topologies</span></span>

<span data-ttu-id="ded6a-137">您可以为业务服务器 2015年和 Exchange 统一消息 (UM) 在同一个林中或多个目录林部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="ded6a-137">You can deploy Skype for Business Server 2015 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="ded6a-138">如果部署跨多个目录林，则必须为每个 UM Exchange 林执行交换集成步骤。</span><span class="sxs-lookup"><span data-stu-id="ded6a-138">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="ded6a-139">此外，您还必须配置每个 Microsoft Exchange 目录林信任业务服务器 2015年林 Skype 和 Skype 业务服务器 2015年林信任每个 UM Exchange 目录林。</span><span class="sxs-lookup"><span data-stu-id="ded6a-139">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="ded6a-140">除了此目录林信任，必须在中为业务服务器 2015年林 Skype 用户对象设置所有用户的 Exchange UM 设置。</span><span class="sxs-lookup"><span data-stu-id="ded6a-140">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server 2015 forest.</span></span> 
  
<span data-ttu-id="ded6a-141">Skype 的业务服务器 2015 UM 交换集成支持下列拓扑：</span><span class="sxs-lookup"><span data-stu-id="ded6a-141">Skype for Business Server 2015 supports the following topologies for Exchange UM integration:</span></span>
  
- <span data-ttu-id="ded6a-142">单林</span><span class="sxs-lookup"><span data-stu-id="ded6a-142">Single forest</span></span>
    
- <span data-ttu-id="ded6a-143">单域（即具有单个域的单林）。</span><span class="sxs-lookup"><span data-stu-id="ded6a-143">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="ded6a-144">Skype 业务服务器 2015年、 Microsoft Exchange 和全部位于同一个域中的用户。</span><span class="sxs-lookup"><span data-stu-id="ded6a-144">Skype for Business Server 2015, Microsoft Exchange, and users all reside in the same domain.</span></span>
    
- <span data-ttu-id="ded6a-145">多域（即具有一个或多个子域的根域）。</span><span class="sxs-lookup"><span data-stu-id="ded6a-145">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="ded6a-146">Skype 业务服务器 2015，和 Microsoft Exchange 服务器部署在不同的域，您可在其中创建用户的域中。</span><span class="sxs-lookup"><span data-stu-id="ded6a-146">Skype for Business Server 2015, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="ded6a-147">可以在不同的域，从它们所支持的业务服务器 2015年池 Skype 部署 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="ded6a-147">Exchange UM servers can be deployed in different domains from the Skype for Business Server 2015 pool they support.</span></span>
    
- <span data-ttu-id="ded6a-148">多林（即资源林）。</span><span class="sxs-lookup"><span data-stu-id="ded6a-148">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="ded6a-149">Skype 的业务服务器 2015年部署单个目录林，然后用户分布在多个目录林。</span><span class="sxs-lookup"><span data-stu-id="ded6a-149">Skype for Business Server 2015 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="ded6a-150">交换 UM 的用户的属性必须通过复制到企业服务器 2015年林 Skype。</span><span class="sxs-lookup"><span data-stu-id="ded6a-150">The users' Exchange UM attributes must be replicated over to the Skype for Business Server 2015 forest.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ded6a-151">可在多个林中部署 Exchange。</span><span class="sxs-lookup"><span data-stu-id="ded6a-151">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="ded6a-152">每个 Exchange 组织可以交换 UM 提供给它的用户，或 UM Exchange 可以部署在同一个林中 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="ded6a-152">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server 2015.</span></span> 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="ded6a-153">集成本地统一消息与 Skype for Business Server 2015 的指南</span><span class="sxs-lookup"><span data-stu-id="ded6a-153">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="ded6a-154">以下是部署企业语音时要考虑的准则和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="ded6a-154">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ded6a-155">Exchange 统一消息 (UM) 支持 IPv6，仅当您同时还使用 UCMA 4。</span><span class="sxs-lookup"><span data-stu-id="ded6a-155">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span> 
  
- <span data-ttu-id="ded6a-156">部署业务服务器 2015年标准版服务器或前端池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="ded6a-156">Deploy a Skype for Business Server 2015 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="ded6a-157">有关安装的详细信息，请参阅部署文档中的[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md) 。</span><span class="sxs-lookup"><span data-stu-id="ded6a-157">For details about installation, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="ded6a-158">与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。</span><span class="sxs-lookup"><span data-stu-id="ded6a-158">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>
    
- <span data-ttu-id="ded6a-159">将每个想要启用用户的 Exchange UM 的 Exchange 统一消息 (UM) 目录林中的 Exchange 邮箱服务器角色的部署。</span><span class="sxs-lookup"><span data-stu-id="ded6a-159">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="ded6a-160">有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013年文档。</span><span class="sxs-lookup"><span data-stu-id="ded6a-160">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ded6a-161">安装 Exchange 统一消息 (UM) 后，它被配置为使用自签名的证书。</span><span class="sxs-lookup"><span data-stu-id="ded6a-161">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="ded6a-162">自签名的证书不支持 Skype 业务服务器 2015年和 UM 交换要相互信任，因此，有必要从两个服务器信任的证书颁发机构请求一个单独的证书。</span><span class="sxs-lookup"><span data-stu-id="ded6a-162">The self-signed certificate does not enable Skype for Business Server 2015 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span> 
  
- <span data-ttu-id="ded6a-163">如果 Skype 业务服务器 2015年和 UM Exchange 安装在不同的目录林中，配置每个 Exchange 目录林信任业务服务器 2015年林 Skype 和 Skype 业务服务器 2015年林信任每个 Exchange 目录林。</span><span class="sxs-lookup"><span data-stu-id="ded6a-163">If Skype for Business Server 2015 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange forest.</span></span> <span data-ttu-id="ded6a-164">此外，Exchange UM 的用户的设置中业务服务器 2015年林，Skype 的用户对象通常使用设置脚本或跨目录林的工具，如身份生命周期管理器 (ILM)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-164">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server 2015 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>
    
- <span data-ttu-id="ded6a-165">必要时，安装 Exchange 管理控制台以管理统一消息服务器。</span><span class="sxs-lookup"><span data-stu-id="ded6a-165">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>
    
- <span data-ttu-id="ded6a-166">获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。</span><span class="sxs-lookup"><span data-stu-id="ded6a-166">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>
    
- <span data-ttu-id="ded6a-167">如果您使用的 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 比早期版本的 Exchange UM，坐标交换 UM SIP 的 URI 名称拨号计划和企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ded6a-167">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span> 
    
### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="ded6a-168">部署冗余 Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="ded6a-168">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ded6a-169">我们建议您部署最少的两个服务器的 Exchange UM 服务运行您为您的组织配置每个 Exchange UM SIP 的 URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ded6a-169">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="ded6a-170">除了提供扩展容量之外，部署冗余服务还可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ded6a-170">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="ded6a-171">发生服务器故障时，可以配置业务服务器 2015年的 Skype 为故障转移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="ded6a-171">In the event of an server failure, Skype for Business Server 2015 can be configured to fail over to another server.</span></span> 
  
<span data-ttu-id="ded6a-172">以下示例配置提供 Exchange UM 恢复能力。</span><span class="sxs-lookup"><span data-stu-id="ded6a-172">The following example configurations provide Exchange UM resiliency.</span></span>
  
<span data-ttu-id="ded6a-173">**示例 1: Exchange UM 复原**</span><span class="sxs-lookup"><span data-stu-id="ded6a-173">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
<span data-ttu-id="ded6a-p119">在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="ded6a-p119">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ded6a-178">对于示例 1 中，您还应分配下列每个 UM Exchange 服务器上的证书之一： 使用者备用名称 (SAN) 中的通配符证书或四个 Exchange UM 服务器 SAN 中的每个放置的完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-178">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span> 
  
<span data-ttu-id="ded6a-179">**示例 2: Exchange UM 复原**</span><span class="sxs-lookup"><span data-stu-id="ded6a-179">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
<span data-ttu-id="ded6a-p120">在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。</span><span class="sxs-lookup"><span data-stu-id="ded6a-p120">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>
  
<span data-ttu-id="ded6a-184">有关如何启用或禁用统一邮件在 Exchange 2013 的详细信息，请参阅[集成交换 2013 UM 使用 Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)。</span><span class="sxs-lookup"><span data-stu-id="ded6a-184">For details about how to enable or disable Unified Messaging on Exchange 2013, see [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="ded6a-185">提供的信息同样适用于 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="ded6a-185">The information provided applies equally to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ded6a-186">有关如何启用或禁用 Microsoft Exchange Server 2010年上的统一消息的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ded6a-186">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>
  
- [<span data-ttu-id="ded6a-187">启用统一邮件在 Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="ded6a-187">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [<span data-ttu-id="ded6a-188">禁用统一邮件在 Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="ded6a-188">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a><span data-ttu-id="ded6a-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ded6a-189">See also</span></span>

#### 

[<span data-ttu-id="ded6a-190">部署过程概述用于集成内部统一消息和 Skype 业务</span><span class="sxs-lookup"><span data-stu-id="ded6a-190">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)

