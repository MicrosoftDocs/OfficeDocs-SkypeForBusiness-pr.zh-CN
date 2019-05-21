---
title: 在 Skype for Business 中规划 Exchange 统一消息集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '摘要: 在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时, 请查看本主题。'
ms.openlocfilehash: 3b71dd740440aeab37919bb94ef98eaeb83d4d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297342"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="4b5ef-103">在 Skype for Business 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="4b5ef-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>

<span data-ttu-id="4b5ef-104">**摘要:** 在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时, 请查看此主题。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>

<span data-ttu-id="4b5ef-105">Skype for Business 服务器支持与 Exchange 统一消息 (UM) 集成, 以将语音消息和电子邮件合并到单个消息传递基础结构中。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-105">Skype for Business Server supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="4b5ef-106">在 Exchange 中, Exchange 统一消息 (UM) 是你可以安装和配置的若干 Exchange 服务器角色之一。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="4b5ef-107">在 Microsoft Exchange Server 2013 和2016中, Exchange UM 在 Exchange 邮箱服务器上作为服务运行。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-107">In Microsoft Exchange Server 2013 and 2016, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="4b5ef-108">对于 Skype for business 服务器企业语音部署, 统一消息将语音消息和电子邮件合并到单个应用商店, 用户可以从电话 (Outlook Voice Access) 或计算机访问该应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-108">For Skype for Business Server Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="4b5ef-109">统一消息和 Skype for business 服务器协同工作, 为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-109">Unified Messaging and Skype for Business Server work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

> [!NOTE]
> <span data-ttu-id="4b5ef-110">将 Skype for business 2019 与 Exchange 2013 或 Exchange 2016 集成时, exchange UM 将在 Skype for business Server 2019 中保持可用。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="4b5ef-111">由于 Exchange 2019 中的支持的更改, Exchange UM 集成已被取消重点, 取而代之的是云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  <span data-ttu-id="4b5ef-112">有关详细信息, 请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)和[规划 Skype for Business 服务器和 Exchange Server 迁移](../../../sfbhybrid/hybrid/plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-112">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../../../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>


<span data-ttu-id="4b5ef-113">为了使这些功能在本地 Exchange UM 部署中受支持, 必须运行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="4b5ef-113">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

- <span data-ttu-id="4b5ef-114">Microsoft Exchange Server 2010 或最新服务包 (仅限 Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="4b5ef-114">Microsoft Exchange Server 2010 or latest service pack (Skype for Business Server 2015 only)</span></span>
- <span data-ttu-id="4b5ef-115">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b5ef-115">Microsoft Exchange Server 2013</span></span>
- <span data-ttu-id="4b5ef-116">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="4b5ef-116">Microsoft Exchange Server 2016</span></span>
- <span data-ttu-id="4b5ef-117">Microsoft Exchange Server 2019 (仅适用于 Skype for Business Server 2019)</span><span class="sxs-lookup"><span data-stu-id="4b5ef-117">Microsoft Exchange Server 2019  (Skype for Business Server 2019 only)</span></span>

> [!NOTE]
> <span data-ttu-id="4b5ef-118">Skype for Business Server 2019 中不再提供 Exchange 统一消息, 它使用电话系统录制语音邮件, 然后将录制内容保留在用户的 Exchange 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-118">Exchange Unified Messaging as previously known is no longer available in Skype for Business Server 2019, which uses Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="4b5ef-119">有关详细信息, 请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-119">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="4b5ef-120">集成统一消息和 Skype for business 服务器的功能</span><span class="sxs-lookup"><span data-stu-id="4b5ef-120">Features of integrated Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="4b5ef-121">Skype for Business 服务器, 企业语音使用 Exchange 统一消息 (UM) 基础结构提供呼叫应答、呼叫通知、语音访问 (包括语音邮件) 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-121">Skype for Business Server, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

- <span data-ttu-id="4b5ef-p105">**呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-p105">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

    <span data-ttu-id="4b5ef-p106">如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-p106">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

- <span data-ttu-id="4b5ef-128">**Outlook Voice Access**Outlook Voice Access 使企业语音用户不仅可以访问语音邮件, 还可以访问 Exchange 收件箱, 包括来自电话界面的电子邮件、日历和联系人。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-128">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="4b5ef-129">订阅者访问号码由 Exchange UM 管理员分配。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-129">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

- <span data-ttu-id="4b5ef-130">**自动助理**自动助理是一种 Exchange UM 功能, 可用于配置外部用户可以拨打联系公司代表的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-130">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="4b5ef-131">尤其是, 它提供一系列语音提示, 帮助外部呼叫者导航菜单系统。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-131">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="4b5ef-132">可用选项列表由 Exchange UM 管理员在 Exchange UM 服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-132">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

- <span data-ttu-id="4b5ef-133">**传真服务**Exchange UM 包括传真功能, 使用户能够接收其 Exchange 邮箱中的传入传真。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-133">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="4b5ef-134">有关详细信息, 请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-134">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b5ef-135">Exchange UM 服务器提供的传真服务在与 Microsoft Exchange Server 2010、exchange 2010 以及最新服务包、Exchange 2013 或 Exchange 2016 集成的 Skype for business 服务器部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-135">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, Exchange 2013, or Exchange 2016.</span></span>

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a><span data-ttu-id="4b5ef-136">Skype for Business Server 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="4b5ef-136">Components and topologies for on-premises Unified Messaging in Skype for Business Server</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="4b5ef-137">Exchange Server 组件</span><span class="sxs-lookup"><span data-stu-id="4b5ef-137">Exchange Server Components</span></span>

<span data-ttu-id="4b5ef-138">若要向组织中的企业语音用户提供[集成统一消息和 Skype for Business 服务器功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中介绍的 Exchange UM 功能和服务, 必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器, 它托管用户邮箱并为电子邮件和语音邮件提供单个存储位置。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-138">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="4b5ef-139">Exchange UM 在 Exchange 邮箱和客户端访问服务器上作为服务运行。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-139">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="4b5ef-140">有关 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息, 请参阅[部署本地 EXCHANGE um 以提供 Lync Server 2013 预览版语音邮件](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-140">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .</span></span>

### <a name="supported-topologies"></a><span data-ttu-id="4b5ef-141">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="4b5ef-141">Supported Topologies</span></span>

<span data-ttu-id="4b5ef-142">你可以在同一林中或多个林中部署 Skype for Business Server 和 Exchange 统一消息 (UM)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-142">You can deploy Skype for Business Server and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="4b5ef-143">如果部署跨越多个林, 则必须针对每个 Exchange UM 林执行 Exchange 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-143">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="4b5ef-144">此外, 你必须将每个 Microsoft Exchange 林配置为信任 Skype for business Server 林和 Skype for business 服务器林以信任每个 Exchange UM 林。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-144">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="4b5ef-145">除了此林信任之外, 所有用户的 Exchange UM 设置必须在 Skype for Business Server 林中的用户对象上设置。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-145">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server forest.</span></span>

<span data-ttu-id="4b5ef-146">Skype for Business 服务器支持 Exchange UM 集成的以下拓扑:</span><span class="sxs-lookup"><span data-stu-id="4b5ef-146">Skype for Business Server supports the following topologies for Exchange UM integration:</span></span>

- <span data-ttu-id="4b5ef-147">单林</span><span class="sxs-lookup"><span data-stu-id="4b5ef-147">Single forest</span></span>

- <span data-ttu-id="4b5ef-148">单域（即具有单个域的单林）。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-148">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="4b5ef-149">Skype for business 服务器、Microsoft Exchange 和用户都位于同一个域中。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-149">Skype for Business Server, Microsoft Exchange, and users all reside in the same domain.</span></span>

- <span data-ttu-id="4b5ef-150">多域（即具有一个或多个子域的根域）。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-150">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="4b5ef-151">Skype for business 服务器和 Microsoft Exchange 服务器从你创建用户的域中的不同域进行部署。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-151">Skype for Business Server, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="4b5ef-152">Exchange UM 服务器可以从其支持的 Skype for business 服务器池所在的不同域进行部署。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-152">Exchange UM servers can be deployed in different domains from the Skype for Business Server pool they support.</span></span>

- <span data-ttu-id="4b5ef-153">多林（即资源林）。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-153">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="4b5ef-154">Skype for business 服务器部署在单个林中, 然后用户跨多个目录林分布。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-154">Skype for Business Server is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="4b5ef-155">用户的 Exchange UM 属性必须复制到 Skype for business 服务器林。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-155">The users' Exchange UM attributes must be replicated over to the Skype for Business Server forest.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b5ef-156">可在多个林中部署 Exchange。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-156">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="4b5ef-157">每个 Exchange 组织可以向其用户提供 Exchange UM, 或者 Exchange UM 可以部署在 Skype for business 服务器所在的同一林中。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-157">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server.</span></span>

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="4b5ef-158">集成本地统一消息和 Skype for Business 服务器指南</span><span class="sxs-lookup"><span data-stu-id="4b5ef-158">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="4b5ef-159">以下是部署企业语音时要考虑的准则和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="4b5ef-159">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b5ef-160">Exchange 统一消息 (UM) 仅在你也使用 UCMA 4 时才支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-160">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>

- <span data-ttu-id="4b5ef-161">部署 Skype for business Server Standard Edition server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-161">Deploy a Skype for Business Server Standard Edition server or a Front End pool.</span></span>

- <span data-ttu-id="4b5ef-162">与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-162">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

- <span data-ttu-id="4b5ef-163">在要为 Exchange UM 启用用户的每个 Exchange 统一消息 (UM) 林中部署 Exchange 邮箱服务器角色。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-163">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="4b5ef-164">有关安装 Exchange server 角色的详细信息, 请参阅 Microsoft Exchange Server 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-164">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4b5ef-165">当安装 Exchange 统一消息 (UM) 时, 它将配置为使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-165">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="4b5ef-166">自签名证书不支持 Skype for business 服务器和 Exchange UM 相互信任, 这就是为什么需要从两个服务器信任的证书颁发机构请求单独的证书的原因。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-166">The self-signed certificate does not enable Skype for Business Server and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

- <span data-ttu-id="4b5ef-167">如果 Skype for business 服务器和 Exchange UM 安装在不同的林中, 请将每个 Exchange 林配置为信任 Skype for business 服务器林和 Skype for business Server 林以信任每个 Exchange 林。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-167">If Skype for Business Server and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange forest.</span></span> <span data-ttu-id="4b5ef-168">此外, 在 Skype for Business Server 林中的用户对象上设置用户的 Exchange UM 设置, 通常通过使用脚本或跨林工具 (如 "身份生命周期管理器 (ILM)")。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-168">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

- <span data-ttu-id="4b5ef-169">必要时，安装 Exchange 管理控制台以管理统一消息服务器。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-169">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

- <span data-ttu-id="4b5ef-170">获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-170">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

- <span data-ttu-id="4b5ef-171">如果你使用早于 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 的 Exchange UM 的版本, 请调整 Exchange UM SIP URI 拨号计划和企业语音拨号计划的名称。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-171">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="4b5ef-172">部署冗余 Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="4b5ef-172">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b5ef-173">我们建议你为你的组织配置的每个 Exchange UM SIP URI 拨号计划至少部署两台 Exchange UM 服务运行的服务器。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-173">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="4b5ef-174">除了提供扩展容量之外，部署冗余服务还可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-174">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="4b5ef-175">在服务器出现故障时, 可以将 Skype for Business 服务器配置为故障转移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-175">In the event of an server failure, Skype for Business Server can be configured to fail over to another server.</span></span>

<span data-ttu-id="4b5ef-176">以下示例配置提供 Exchange UM 恢复能力。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-176">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="4b5ef-177">**示例 1：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="4b5ef-177">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

<span data-ttu-id="4b5ef-p120">在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-p120">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="4b5ef-182">例如, 你还应在每个 Exchange UM 服务器上分配以下证书之一: 在 "主题备用名称" (SAN) 中使用带有通配符的证书, 或将 SAN 中四个 Exchange UM 服务器中每个服务器的完全限定的域名 (FQDN) 放入其中。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-182">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span>

<span data-ttu-id="4b5ef-183">**示例 2：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="4b5ef-183">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

<span data-ttu-id="4b5ef-p121">在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-p121">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="4b5ef-188">有关如何在 Exchange 2013 上启用或禁用统一消息的详细信息, 请参阅将[Exchange 2013 UM 与 Lync Server 集成](https://go.microsoft.com/fwlink/p/?LinkId=265372)。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-188">For details about how to enable or disable Unified Messaging on Exchange 2013, see  [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="4b5ef-189">所提供的信息同样适用于 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-189">The information provided applies equally to Skype for Business Server.</span></span>

<span data-ttu-id="4b5ef-190">有关如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="4b5ef-190">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

- [<span data-ttu-id="4b5ef-191">在 Exchange 2010 上启用统一消息</span><span class="sxs-lookup"><span data-stu-id="4b5ef-191">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [<span data-ttu-id="4b5ef-192">禁用 Exchange 2010 上的统一消息</span><span class="sxs-lookup"><span data-stu-id="4b5ef-192">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a><span data-ttu-id="4b5ef-193">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="4b5ef-193">Exchange Server 2019</span></span>

<span data-ttu-id="4b5ef-194">Exchange 2019 中不再显示 exchange 统一消息, 如果您有 Exchange 2019, 并且您需要同等的功能, 则需要使用[计划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述的云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="4b5ef-194">Exchange Unified Messaging is no longer present in Exchange 2019, if you have Exchange 2019 and you want equivalent functionality you will need to use the Cloud Voicemail service described in [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4b5ef-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b5ef-195">See also</span></span>

[<span data-ttu-id="4b5ef-196">集成本地统一消息与 Skype for Business 的部署过程概述</span><span class="sxs-lookup"><span data-stu-id="4b5ef-196">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)
