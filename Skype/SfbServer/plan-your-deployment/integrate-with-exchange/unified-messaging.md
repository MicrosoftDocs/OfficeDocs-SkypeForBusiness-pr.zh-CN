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
description: 摘要： 查看 while planning to Exchange 2013 或 2016年业务服务器集成 Skype 本主题。
ms.openlocfilehash: f560df43ab6347890cc5a3b956d43ed37a55bdf3
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263898"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="e506e-103">在 Skype for Business 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="e506e-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>

<span data-ttu-id="e506e-104">**摘要：** While planning to Exchange 2013 或 2016年业务服务器集成 Skype 查看以下主题。</span><span class="sxs-lookup"><span data-stu-id="e506e-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>

<span data-ttu-id="e506e-105">Skype 业务服务器支持的组合语音消息传递和电子邮件到单个消息传递基础结构与 Exchange 统一消息 (UM) 集成。</span><span class="sxs-lookup"><span data-stu-id="e506e-105">Skype for Business Server supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="e506e-106">在 Exchange 中，Exchange 统一消息 (UM) 是可安装和配置多个 Exchange 服务器角色之一。</span><span class="sxs-lookup"><span data-stu-id="e506e-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="e506e-107">在 Microsoft Exchange Server 2013 和 2016年，Exchange UM 作为服务运行在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="e506e-107">In Microsoft Exchange Server 2013 and 2016, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="e506e-108">Skype 的业务 Server 企业语音部署，为语音消息传递和电子邮件消息到一个存储的用户可以从 (Outlook Voice Access) 的电话或计算机访问结合统一消息。</span><span class="sxs-lookup"><span data-stu-id="e506e-108">For Skype for Business Server Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="e506e-109">统一消息和企业服务器的 Skype 协同工作来向企业语音用户提供呼叫应答、 Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="e506e-109">Unified Messaging and Skype for Business Server work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

> [!NOTE]
> <span data-ttu-id="e506e-110">Exchange UM 仍可在 Skype 的业务服务器 2019年与 Exchange 2013 或 Exchange 2016 集成 for Business 2019 Skype 时。</span><span class="sxs-lookup"><span data-stu-id="e506e-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="e506e-111">由于 Exchange 2019 中支持的变化，Exchange UM 集成正在注销 emphasised 支持云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="e506e-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  <span data-ttu-id="e506e-112">有关详细信息，请参阅[规划云语音邮件服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)和[Plan for Business Server 和 Exchange Server 迁移的 Skype](../../../SfBServer2019/hybrid/plan-um-migration.md) 。</span><span class="sxs-lookup"><span data-stu-id="e506e-112">See [Plan Cloud Voicemail service](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../../../SfBServer2019/hybrid/plan-um-migration.md) for more information.</span></span>


<span data-ttu-id="e506e-113">内部部署 Exchange UM 部署中支持这些功能，您必须运行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e506e-113">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

- <span data-ttu-id="e506e-114">Microsoft Exchange Server 2010 或最新 service pack (Skype 的业务服务器 2015 仅)</span><span class="sxs-lookup"><span data-stu-id="e506e-114">Microsoft Exchange Server 2010 or latest service pack (Skype for Business Server 2015 only)</span></span>
- <span data-ttu-id="e506e-115">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e506e-115">Microsoft Exchange Server 2013</span></span>
- <span data-ttu-id="e506e-116">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="e506e-116">Microsoft Exchange Server 2016</span></span>
- <span data-ttu-id="e506e-117">Microsoft Exchange Server 2019 (仅业务服务器 2019 Skype)</span><span class="sxs-lookup"><span data-stu-id="e506e-117">Microsoft Exchange Server 2019  (Skype for Business Server 2019 only)</span></span>

> [!NOTE]
> <span data-ttu-id="e506e-118">Exchange 统一消息为以前已知不再可用的业务服务器 2019，使用电话系统来记录中的语音邮件，然后用户的 Exchange 邮箱中保留录制的 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="e506e-118">Exchange Unified Messaging as previously known is no longer available in Skype for Business Server 2019, which uses Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="e506e-119">有关详细信息，请参阅[规划语音邮件云服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="e506e-119">See [Plan Cloud Voicemail service](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) for more information.</span></span>

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="e506e-120">集成的统一消息和 Skype 业务服务器的功能</span><span class="sxs-lookup"><span data-stu-id="e506e-120">Features of integrated Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="e506e-121">对于业务 Server，企业语音的 Skype 使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、 呼叫通知、 语音访问 （包括语音邮件） 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="e506e-121">Skype for Business Server, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

- <span data-ttu-id="e506e-p105">**呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="e506e-p105">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

    <span data-ttu-id="e506e-p106">如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。</span><span class="sxs-lookup"><span data-stu-id="e506e-p106">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

- <span data-ttu-id="e506e-128">**Outlook Voice Access**Outlook Voice Access 使企业语音用户访问而不仅仅是语音邮件，但还 Exchange 收件箱，其中包括电子邮件、 日历和联系人通过电话界面。</span><span class="sxs-lookup"><span data-stu-id="e506e-128">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="e506e-129">由 Exchange UM 管理员分配订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="e506e-129">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

- <span data-ttu-id="e506e-130">**自动助理**自动助理是 Exchange UM 功能，可以用来配置的外部用户访问公司代表可拨打的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e506e-130">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="e506e-131">具体而言，它提供了一系列语音提示来帮助外部呼叫者导航菜单系统。</span><span class="sxs-lookup"><span data-stu-id="e506e-131">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="e506e-132">可用选项的列表由 Exchange UM 管理员配置 Exchange UM 服务器上。</span><span class="sxs-lookup"><span data-stu-id="e506e-132">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

- <span data-ttu-id="e506e-133">**传真服务**Exchange UM 包括传真功能，它使用户能够在其 Exchange 邮箱中接收传入的传真。</span><span class="sxs-lookup"><span data-stu-id="e506e-133">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="e506e-134">有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。</span><span class="sxs-lookup"><span data-stu-id="e506e-134">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e506e-135">由 Exchange UM 服务器提供的传真服务不与 Microsoft Exchange Server 2010、 最新的 service pack 的 Exchange 2010、 Exchange 2013 或 Exchange 2016 集成的业务服务器部署 Skype 适用。</span><span class="sxs-lookup"><span data-stu-id="e506e-135">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, Exchange 2013, or Exchange 2016.</span></span>

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a><span data-ttu-id="e506e-136">在本地统一消息中的业务服务器 Skype 的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="e506e-136">Components and topologies for on-premises Unified Messaging in Skype for Business Server</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="e506e-137">Exchange Server 组件</span><span class="sxs-lookup"><span data-stu-id="e506e-137">Exchange Server Components</span></span>

<span data-ttu-id="e506e-138">若要提供的 Exchange UM 功能和服务[集成的统一消息和 Skype 业务服务器的功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所述向您的组织中的企业语音用户，必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，用于托管用户邮箱，并提供单一的存储位置的电子邮件和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e506e-138">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="e506e-139">Exchange UM 作为服务运行在 Exchange 邮箱和客户端访问服务器上。</span><span class="sxs-lookup"><span data-stu-id="e506e-139">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="e506e-140">有关 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅[部署内部部署 Exchange UM 提供 Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="e506e-140">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .</span></span>

### <a name="supported-topologies"></a><span data-ttu-id="e506e-141">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="e506e-141">Supported Topologies</span></span>

<span data-ttu-id="e506e-142">您可以部署 Skype Business Server 和 Exchange 统一消息 (UM) 中同一个林或多个林。</span><span class="sxs-lookup"><span data-stu-id="e506e-142">You can deploy Skype for Business Server and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="e506e-143">如果部署跨越多个林，您必须为每个 Exchange UM 林执行 Exchange 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="e506e-143">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="e506e-144">此外，您必须配置每个 Microsoft Exchange 林信任 Business Server 林 Skype 和 Skype Business Server 林信任 Exchange UM 的每个林。</span><span class="sxs-lookup"><span data-stu-id="e506e-144">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="e506e-145">除了该林信任，所有用户的 Exchange UM 设置必须设置中为 Business Server 林 Skype 的用户对象。</span><span class="sxs-lookup"><span data-stu-id="e506e-145">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server forest.</span></span>

<span data-ttu-id="e506e-146">Skype 业务服务器支持 Exchange UM 集成的以下拓扑：</span><span class="sxs-lookup"><span data-stu-id="e506e-146">Skype for Business Server supports the following topologies for Exchange UM integration:</span></span>

- <span data-ttu-id="e506e-147">单林</span><span class="sxs-lookup"><span data-stu-id="e506e-147">Single forest</span></span>

- <span data-ttu-id="e506e-148">单域（即具有单个域的单林）。</span><span class="sxs-lookup"><span data-stu-id="e506e-148">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="e506e-149">Skype 业务服务器、 Microsoft Exchange、 和都位于同一域的用户。</span><span class="sxs-lookup"><span data-stu-id="e506e-149">Skype for Business Server, Microsoft Exchange, and users all reside in the same domain.</span></span>

- <span data-ttu-id="e506e-150">多域（即具有一个或多个子域的根域）。</span><span class="sxs-lookup"><span data-stu-id="e506e-150">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="e506e-151">从您在其中创建用户的域的不同域中部署 Business Server 和 Microsoft Exchange 服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="e506e-151">Skype for Business Server, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="e506e-152">可以从它们支持的业务服务器池的 Skype 的不同域中部署 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-152">Exchange UM servers can be deployed in different domains from the Skype for Business Server pool they support.</span></span>

- <span data-ttu-id="e506e-153">多林（即资源林）。</span><span class="sxs-lookup"><span data-stu-id="e506e-153">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="e506e-154">Skype 业务服务器部署在单个林中，且用户然后分配跨多级林。</span><span class="sxs-lookup"><span data-stu-id="e506e-154">Skype for Business Server is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="e506e-155">必须将用户的 Exchange UM 属性通过复制到 Business Server 林 Skype。</span><span class="sxs-lookup"><span data-stu-id="e506e-155">The users' Exchange UM attributes must be replicated over to the Skype for Business Server forest.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e506e-156">可在多个林中部署 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e506e-156">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="e506e-157">每个 Exchange 组织可以为其用户，Exchange UM 提供或 Exchange UM 可以部署在同一个林中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-157">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server.</span></span>

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="e506e-158">集成的指南在本地统一消息和 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="e506e-158">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="e506e-159">以下是部署企业语音时要考虑的准则和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="e506e-159">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e506e-160">Exchange 统一消息 (UM) 支持 IPv6，仅当您也使用 UCMA 4。</span><span class="sxs-lookup"><span data-stu-id="e506e-160">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>

- <span data-ttu-id="e506e-161">部署 Skype 业务 Server Standard Edition server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="e506e-161">Deploy a Skype for Business Server Standard Edition server or a Front End pool.</span></span>

- <span data-ttu-id="e506e-162">与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。</span><span class="sxs-lookup"><span data-stu-id="e506e-162">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

- <span data-ttu-id="e506e-163">部署中每个要为用户启用 Exchange UM 的 Exchange 统一消息 (UM) 林的 Exchange 邮箱服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e506e-163">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="e506e-164">有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="e506e-164">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e506e-165">安装 Exchange 统一消息 (UM) 时，它被配置为使用自签名的证书。</span><span class="sxs-lookup"><span data-stu-id="e506e-165">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="e506e-166">自签名的证书不启用 Skype 的业务 Server 和 Exchange UM 以相互信任，这是需要单独的证书请求从两台服务器信任的证书颁发机构的原因。</span><span class="sxs-lookup"><span data-stu-id="e506e-166">The self-signed certificate does not enable Skype for Business Server and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

- <span data-ttu-id="e506e-167">如果在不同的林中安装了 Business Server 和 Exchange UM 的 Skype，配置每个 Exchange 林信任 Business Server 林 Skype 和 Skype Business Server 林信任每个 Exchange 林。</span><span class="sxs-lookup"><span data-stu-id="e506e-167">If Skype for Business Server and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange forest.</span></span> <span data-ttu-id="e506e-168">此外，用户的 Exchange UM 上设置设置中为 Business Server 林 Skype 用户对象通常使用脚本或跨林工具，例如 Identity Lifecycle Manager (ILM)。</span><span class="sxs-lookup"><span data-stu-id="e506e-168">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

- <span data-ttu-id="e506e-169">必要时，安装 Exchange 管理控制台以管理统一消息服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-169">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

- <span data-ttu-id="e506e-170">获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。</span><span class="sxs-lookup"><span data-stu-id="e506e-170">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

- <span data-ttu-id="e506e-171">如果您使用 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 以前版本的 Exchange UM，坐标名称 Exchange UM SIP 的 URI 拨号计划和企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e506e-171">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="e506e-172">部署冗余 Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="e506e-172">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e506e-173">我们建议您部署至少两台服务器的 Exchange UM 服务正在运行的每个为组织配置的 Exchange UM SIP 的 URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e506e-173">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="e506e-174">除了提供扩展容量之外，部署冗余服务还可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="e506e-174">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="e506e-175">发生服务器故障时，可以配置 Skype 业务服务器故障转移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-175">In the event of an server failure, Skype for Business Server can be configured to fail over to another server.</span></span>

<span data-ttu-id="e506e-176">以下示例配置提供 Exchange UM 恢复能力。</span><span class="sxs-lookup"><span data-stu-id="e506e-176">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="e506e-177">**示例 1：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="e506e-177">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

<span data-ttu-id="e506e-p120">在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="e506e-p120">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="e506e-182">示例 1 中，您还应分配下列每台 Exchange UM 服务器上的证书之一： 用于在使用者替代名称 (SAN) 的通配符证书或每个四台 Exchange UM 服务器 SAN 中放置的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e506e-182">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span>

<span data-ttu-id="e506e-183">**示例 2：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="e506e-183">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

<span data-ttu-id="e506e-p121">在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-p121">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="e506e-188">有关如何启用或禁用 Exchange 2013 上的统一消息的详细信息，请参阅[Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)。</span><span class="sxs-lookup"><span data-stu-id="e506e-188">For details about how to enable or disable Unified Messaging on Exchange 2013, see  [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="e506e-189">提供的信息同样适用于 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="e506e-189">The information provided applies equally to Skype for Business Server.</span></span>

<span data-ttu-id="e506e-190">有关如何启用或禁用 Microsoft Exchange Server 2010 统一消息的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e506e-190">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

- [<span data-ttu-id="e506e-191">启用 Exchange 2010 统一消息</span><span class="sxs-lookup"><span data-stu-id="e506e-191">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [<span data-ttu-id="e506e-192">禁用 Exchange 2010 统一消息</span><span class="sxs-lookup"><span data-stu-id="e506e-192">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a><span data-ttu-id="e506e-193">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="e506e-193">Exchange Server 2019</span></span>

<span data-ttu-id="e506e-194">Exchange 统一消息不再存在于在 Exchange 2019，如果您具有 Exchange 2019 并希望将需要使用云语音邮件服务[规划云语音邮件服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)中所述的等效功能。</span><span class="sxs-lookup"><span data-stu-id="e506e-194">Exchange Unified Messaging is no longer present in Exchange 2019, if you have Exchange 2019 and you want equivalent functionality you will need to use the Cloud Voicemail service described in [Plan Cloud Voicemail service](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="e506e-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e506e-195">See also</span></span>

[<span data-ttu-id="e506e-196">集成本地统一消息与 Skype for Business 的部署过程概述</span><span class="sxs-lookup"><span data-stu-id="e506e-196">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)