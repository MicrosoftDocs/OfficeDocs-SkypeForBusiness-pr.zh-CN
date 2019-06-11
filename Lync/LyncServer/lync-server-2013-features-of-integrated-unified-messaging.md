---
title: Lync Server 2013：集成统一消息的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="a8172-102">集成统一消息和 Lync Server 2013 的功能</span><span class="sxs-lookup"><span data-stu-id="a8172-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8172-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a8172-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a8172-104">Lync Server 2013, 企业语音使用 Exchange 统一消息 (UM) 基础结构提供呼叫应答、呼叫通知、语音访问 (包括语音邮件) 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="a8172-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="a8172-105">呼叫应答</span><span class="sxs-lookup"><span data-stu-id="a8172-105">Call Answering</span></span>

<span data-ttu-id="a8172-106">呼叫应答是代表用户接收语音消息, 其呼叫没有接听或占线。</span><span class="sxs-lookup"><span data-stu-id="a8172-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="a8172-107">它包括播放个人问候语、录制邮件以及将邮件提交到将排队等待传递到用户邮箱 (存储在 Exchange 邮箱服务器上)。</span><span class="sxs-lookup"><span data-stu-id="a8172-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="a8172-p102">如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。</span><span class="sxs-lookup"><span data-stu-id="a8172-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="a8172-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="a8172-112">Outlook Voice Access</span></span>

<span data-ttu-id="a8172-113">Outlook Voice Access 使企业语音用户不仅可以访问语音邮件, 还可以访问 Exchange 收件箱, 包括来自电话界面的电子邮件、日历和联系人。</span><span class="sxs-lookup"><span data-stu-id="a8172-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="a8172-114">订阅者访问号码由 Exchange UM 管理员分配。</span><span class="sxs-lookup"><span data-stu-id="a8172-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="a8172-115">自动助理</span><span class="sxs-lookup"><span data-stu-id="a8172-115">Auto Attendant</span></span>

<span data-ttu-id="a8172-116">自动助理是一种 Exchange UM 功能, 可用于配置外部用户可以拨打联系公司代表的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8172-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="a8172-117">尤其是, 它提供一系列语音提示, 帮助外部呼叫者导航菜单系统。</span><span class="sxs-lookup"><span data-stu-id="a8172-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="a8172-118">可用选项列表由 Exchange UM 管理员在 Exchange UM 服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="a8172-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="a8172-119">传真服务</span><span class="sxs-lookup"><span data-stu-id="a8172-119">Fax Services</span></span>

<span data-ttu-id="a8172-120">Exchange UM 包括传真功能, 使用户能够接收其 Exchange 邮箱中的传入传真。</span><span class="sxs-lookup"><span data-stu-id="a8172-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="a8172-121">有关详细信息, 请参阅 Microsoft Exchange Server 文档中的 "统一消息[http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)"。</span><span class="sxs-lookup"><span data-stu-id="a8172-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8172-122">Exchange UM 服务器提供的传真服务在与 Microsoft Exchange Server 2010、Exchange 2010 和最新服务包或 Exchange 2013 集成的 Lync 服务器部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="a8172-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

