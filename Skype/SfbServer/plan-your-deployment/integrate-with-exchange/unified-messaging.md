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
description: 摘要： 查看 while planning to 集成的 Exchange 2013 的业务服务器 2015 Skype 本主题。
ms.openlocfilehash: 6ab3ab1e7cad9f09c6713ea0fbfbc7b7e1a9cc2e
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505109"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="6f6ad-103">在 Skype for Business 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="6f6ad-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>
 
<span data-ttu-id="6f6ad-104">**摘要：** While planning to 集成的 Exchange 2013 的业务服务器 2015 Skype 查看以下主题。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with Exchange 2013.</span></span>
  
<span data-ttu-id="6f6ad-105">Skype 的业务服务器 2015年支持的组合语音消息传递和电子邮件到单个消息传递基础结构与 Exchange 统一消息 (UM) 集成。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-105">Skype for Business Server 2015 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="6f6ad-106">在 Exchange 中，Exchange 统一消息 (UM) 是可安装和配置多个 Exchange 服务器角色之一。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span> 
  
<span data-ttu-id="6f6ad-107">在 Microsoft Exchange Server 2013，Exchange UM 作为服务运行在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="6f6ad-108">Skype 的业务服务器 2015年企业语音部署，为语音消息传递和电子邮件消息到一个存储的用户可以从 (Outlook Voice Access) 的电话或计算机访问结合统一消息。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-108">For Skype for Business Server 2015 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="6f6ad-109">统一消息和 Skype 的业务服务器 2015年协同工作来向企业语音用户提供呼叫应答、 Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-109">Unified Messaging and Skype for Business Server 2015 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>
  
<span data-ttu-id="6f6ad-110">有关 Microsoft Exchange Server 2013 中的体系结构更改的详细信息，请参阅 Microsoft Exchange Server 2013 文档中的[语音体系结构更改](https://go.microsoft.com/fwlink/p/?LinkId=266730)。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see [Voice Architecture Changes](https://go.microsoft.com/fwlink/p/?LinkId=266730) in the Microsoft Exchange Server 2013 documentation.</span></span>
  
<span data-ttu-id="6f6ad-111">内部部署 Exchange UM 部署中支持这些功能，您必须运行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6f6ad-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>
  
- <span data-ttu-id="6f6ad-112">Microsoft Exchange Server 2010 或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="6f6ad-112">Microsoft Exchange Server 2010 or latest service pack</span></span>
    
- <span data-ttu-id="6f6ad-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f6ad-113">Microsoft Exchange Server 2013</span></span>
    
-  <span data-ttu-id="6f6ad-114">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="6f6ad-114">Microsoft Exchange Server 2016</span></span>
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="6f6ad-115">集成统一消息和 Skype for Business Server 2015 的功能</span><span class="sxs-lookup"><span data-stu-id="6f6ad-115">Features of integrated Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="6f6ad-116">业务服务器 2015，企业语音的 Skype 使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、 呼叫通知、 语音访问 （包括语音邮件） 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-116">Skype for Business Server 2015, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>
  
- <span data-ttu-id="6f6ad-p103">**呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p103">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>
    
    <span data-ttu-id="6f6ad-p104">如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p104">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>
    
- <span data-ttu-id="6f6ad-123">**Outlook Voice Access**Outlook Voice Access 使企业语音用户访问而不仅仅是语音邮件，但还 Exchange 收件箱，其中包括电子邮件、 日历和联系人通过电话界面。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-123">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="6f6ad-124">由 Exchange UM 管理员分配订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-124">The subscriber access number is assigned by an Exchange UM administrator.</span></span>
    
- <span data-ttu-id="6f6ad-125">**自动助理**自动助理是 Exchange UM 功能，可以用来配置的外部用户访问公司代表可拨打的电话号码。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-125">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="6f6ad-126">具体而言，它提供了一系列语音提示来帮助外部呼叫者导航菜单系统。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-126">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="6f6ad-127">可用选项的列表由 Exchange UM 管理员配置 Exchange UM 服务器上。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-127">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>
    
- <span data-ttu-id="6f6ad-128">**传真服务**Exchange UM 包括传真功能，它使用户能够在其 Exchange 邮箱中接收传入的传真。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-128">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="6f6ad-129">有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-129">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f6ad-130">由 Exchange UM 服务器提供的传真服务不与 Microsoft Exchange Server 2010、 具有最新的 service pack 的 Exchange 2010 或 Exchange 2013 集成的业务服务器部署 Skype 适用。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-130">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span> 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a><span data-ttu-id="6f6ad-131">Skype for Business Server 2015 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="6f6ad-131">Components and topologies for on-premises Unified Messaging in Skype for Business Server 2015</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="6f6ad-132">Exchange Server 组件</span><span class="sxs-lookup"><span data-stu-id="6f6ad-132">Exchange Server Components</span></span>

<span data-ttu-id="6f6ad-133">若要提供的 Exchange UM 功能和服务于您的组织中的企业语音用户[功能的集成的统一消息和 Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx)中所述，必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器其中承载用户邮箱，并提供单一的存储位置的电子邮件和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-133">To provide the Exchange UM features and services described in [Features of Integrated Unified Messaging and Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="6f6ad-134">Exchange UM 作为服务运行在 Exchange 邮箱和客户端访问服务器上。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-134">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>
  
<span data-ttu-id="6f6ad-135">有关 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅[部署内部部署 Exchange UM 提供 Lync Server 2013 Preview Voice Mail](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-135">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) in the Deployment documentation.</span></span>
  
### <a name="supported-topologies"></a><span data-ttu-id="6f6ad-136">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="6f6ad-136">Supported Topologies</span></span>

<span data-ttu-id="6f6ad-137">您可以部署 Skype 业务服务器 2015年和 Exchange 统一消息 (UM) 中同一个林或多个林。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-137">You can deploy Skype for Business Server 2015 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="6f6ad-138">如果部署跨越多个林，您必须为每个 Exchange UM 林执行 Exchange 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-138">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="6f6ad-139">此外，您必须配置每个 Microsoft Exchange 林信任业务服务器 2015年林 Skype 和业务服务器 2015年林 Skype 信任 Exchange UM 的每个林。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-139">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="6f6ad-140">除了该林信任，所有用户的 Exchange UM 设置必须设置中的业务服务器 2015年林 Skype 的用户对象。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-140">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server 2015 forest.</span></span> 
  
<span data-ttu-id="6f6ad-141">Skype 的业务服务器 2015年支持 Exchange UM 集成的以下拓扑：</span><span class="sxs-lookup"><span data-stu-id="6f6ad-141">Skype for Business Server 2015 supports the following topologies for Exchange UM integration:</span></span>
  
- <span data-ttu-id="6f6ad-142">单林</span><span class="sxs-lookup"><span data-stu-id="6f6ad-142">Single forest</span></span>
    
- <span data-ttu-id="6f6ad-143">单域（即具有单个域的单林）。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-143">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="6f6ad-144">Skype 业务服务器 2015年、 Microsoft Exchange、 和都位于同一域的用户。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-144">Skype for Business Server 2015, Microsoft Exchange, and users all reside in the same domain.</span></span>
    
- <span data-ttu-id="6f6ad-145">多域（即具有一个或多个子域的根域）。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-145">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="6f6ad-146">Skype 业务服务器 2015年和 Microsoft Exchange 服务器部署在不同域中您在其中创建用户的域中。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-146">Skype for Business Server 2015, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="6f6ad-147">可以从它们支持的业务服务器 2015年池 Skype 的不同域中部署 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-147">Exchange UM servers can be deployed in different domains from the Skype for Business Server 2015 pool they support.</span></span>
    
- <span data-ttu-id="6f6ad-148">多林（即资源林）。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-148">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="6f6ad-149">Skype 的业务服务器 2015年部署在单个林中，且用户然后分配跨多级林。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-149">Skype for Business Server 2015 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="6f6ad-150">必须将用户的 Exchange UM 属性通过复制到业务服务器 2015年林 Skype。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-150">The users' Exchange UM attributes must be replicated over to the Skype for Business Server 2015 forest.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f6ad-151">可在多个林中部署 Exchange。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-151">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="6f6ad-152">每个 Exchange 组织可以为其用户，Exchange UM 提供或 Exchange UM 可以部署在同一个林中 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-152">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server 2015.</span></span> 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="6f6ad-153">集成本地统一消息与 Skype for Business Server 2015 的指南</span><span class="sxs-lookup"><span data-stu-id="6f6ad-153">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="6f6ad-154">以下是部署企业语音时要考虑的准则和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="6f6ad-154">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6f6ad-155">Exchange 统一消息 (UM) 支持 IPv6，仅当您也使用 UCMA 4。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-155">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span> 
  
- <span data-ttu-id="6f6ad-156">部署 Skype 业务 Server 2015 Standard Edition server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-156">Deploy a Skype for Business Server 2015 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="6f6ad-157">有关安装的详细信息，请参阅部署文档中[的业务服务器 2015年部署 Skype](../../deploy/deploy.md) 。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-157">For details about installation, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="6f6ad-158">与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-158">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>
    
- <span data-ttu-id="6f6ad-159">部署中每个要为用户启用 Exchange UM 的 Exchange 统一消息 (UM) 林的 Exchange 邮箱服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-159">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="6f6ad-160">有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-160">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6f6ad-161">安装 Exchange 统一消息 (UM) 时，它被配置为使用自签名的证书。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-161">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="6f6ad-162">自签名的证书不启用了业务服务器 2015年和 Exchange UM 以相互信任，这是原因需要单独的证书请求从两台服务器信任的证书颁发机构的 Skype。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-162">The self-signed certificate does not enable Skype for Business Server 2015 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span> 
  
- <span data-ttu-id="6f6ad-163">如果在不同的林中安装了业务服务器 2015年和 Exchange UM 的 Skype，配置每个 Exchange 林信任业务服务器 2015年林 Skype 和 Skype 业务服务器 2015年林信任每个 Exchange 林。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-163">If Skype for Business Server 2015 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange forest.</span></span> <span data-ttu-id="6f6ad-164">此外，用户的 Exchange UM 上设置设置为业务服务器 2015年林 Skype 中的用户对象通常使用脚本或跨林工具，例如 Identity Lifecycle Manager (ILM)。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-164">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server 2015 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>
    
- <span data-ttu-id="6f6ad-165">必要时，安装 Exchange 管理控制台以管理统一消息服务器。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-165">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>
    
- <span data-ttu-id="6f6ad-166">获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-166">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>
    
- <span data-ttu-id="6f6ad-167">如果您使用 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 以前版本的 Exchange UM，坐标名称 Exchange UM SIP 的 URI 拨号计划和企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-167">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span> 
    
### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="6f6ad-168">部署冗余 Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="6f6ad-168">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f6ad-169">我们建议您部署至少两台服务器的 Exchange UM 服务正在运行的每个为组织配置的 Exchange UM SIP 的 URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-169">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="6f6ad-170">除了提供扩展容量之外，部署冗余服务还可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-170">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="6f6ad-171">发生服务器故障，可配置的业务服务器 2015 Skype 为故障转移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-171">In the event of an server failure, Skype for Business Server 2015 can be configured to fail over to another server.</span></span> 
  
<span data-ttu-id="6f6ad-172">以下示例配置提供 Exchange UM 恢复能力。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-172">The following example configurations provide Exchange UM resiliency.</span></span>
  
<span data-ttu-id="6f6ad-173">**示例 1: Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="6f6ad-173">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
<span data-ttu-id="6f6ad-p119">在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p119">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f6ad-178">示例 1 中，您还应分配下列每台 Exchange UM 服务器上的证书之一： 用于在使用者替代名称 (SAN) 的通配符证书或每个四台 Exchange UM 服务器 SAN 中放置的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-178">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span> 
  
<span data-ttu-id="6f6ad-179">**示例 2: Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="6f6ad-179">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
<span data-ttu-id="6f6ad-p120">在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p120">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>
  
<span data-ttu-id="6f6ad-184">有关如何启用或禁用 Exchange 2013 上的统一消息的详细信息，请参阅[Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-184">For details about how to enable or disable Unified Messaging on Exchange 2013, see [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="6f6ad-185">提供的信息同样适用于 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="6f6ad-185">The information provided applies equally to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6f6ad-186">有关如何启用或禁用 Microsoft Exchange Server 2010 统一消息的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6f6ad-186">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>
  
- [<span data-ttu-id="6f6ad-187">启用 Exchange 2010 统一消息</span><span class="sxs-lookup"><span data-stu-id="6f6ad-187">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [<span data-ttu-id="6f6ad-188">禁用 Exchange 2010 统一消息</span><span class="sxs-lookup"><span data-stu-id="6f6ad-188">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a><span data-ttu-id="6f6ad-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f6ad-189">See also</span></span>

[<span data-ttu-id="6f6ad-190">集成的部署过程概述在本地统一消息和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6f6ad-190">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)