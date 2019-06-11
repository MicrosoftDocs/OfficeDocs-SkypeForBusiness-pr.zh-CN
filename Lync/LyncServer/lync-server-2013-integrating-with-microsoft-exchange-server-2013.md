---
title: 'Lync Server 2013: 与 Microsoft Exchange Server 2013 集成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ba140e4f7e33684a280a9d9c4b71f1d7e141a65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="bd13a-102">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd13a-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd13a-103">_**主题上次修改时间:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="bd13a-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="bd13a-104">Exchange 和 Lync 服务器的集成和兼容性历史记录很长。</span><span class="sxs-lookup"><span data-stu-id="bd13a-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="bd13a-105">此集成在其各自的客户端应用程序中最显著。</span><span class="sxs-lookup"><span data-stu-id="bd13a-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="bd13a-106">例如, 可以在 Microsoft Outlook 中报告 Lync 状态信息;同样, Lync 可以使用 Outlook 日历自动更新该状态信息。</span><span class="sxs-lookup"><span data-stu-id="bd13a-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="bd13a-107">(例如, 当你的日历显示你已安排会议时, Lync 可以随时将你的状态更改为 "忙碌"。)虽然您不必运行 Exchange 即可运行 Lync Server (反之亦然), 但很不用怀疑使用这两个产品, epitomizes "更好的"。</span><span class="sxs-lookup"><span data-stu-id="bd13a-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="bd13a-108">在发布 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 时尤其如此。</span><span class="sxs-lookup"><span data-stu-id="bd13a-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="bd13a-109">除了在 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的功能 (如统一消息和 IM 和状态) 之外, 服务器产品的2013版本包括许多新功能。</span><span class="sxs-lookup"><span data-stu-id="bd13a-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="bd13a-110">这些功能包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="bd13a-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="bd13a-111">**Lync 存档集成**。</span><span class="sxs-lookup"><span data-stu-id="bd13a-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="bd13a-112">在 Lync Server 2013 中, 管理员仍然可以选择将即时消息和 Web 会议脚本存档到 SQL Server (与在 Lync Server 2010 中存档这些脚本的方式相同)。</span><span class="sxs-lookup"><span data-stu-id="bd13a-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="bd13a-113">但是, 管理员可以选择将脚本存档到 Exchange 2013, 将这些脚本存储在单个用户邮箱中, 就像 Exchange 存档通信一样。</span><span class="sxs-lookup"><span data-stu-id="bd13a-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="bd13a-114">这意味着用于所有电子通信的单个存储库 (来自 Exchange 和 Lync 服务器), 这样就可以更轻松地搜索和检索这些存档的通信。</span><span class="sxs-lookup"><span data-stu-id="bd13a-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="bd13a-115">**统一联系人存储**。</span><span class="sxs-lookup"><span data-stu-id="bd13a-115">**Unified Contact Store**.</span></span> <span data-ttu-id="bd13a-116">在 Lync Server 2010 中, 用户必须在 Outlook 和 Lync 中维护单独的联系人列表;实际上, 为确保您在两种产品中都可以使用相同的联系人, 您必须维护重复的联系人列表, 一个用于 Outlook, 另一个用于 Lync。</span><span class="sxs-lookup"><span data-stu-id="bd13a-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="bd13a-117">但是, 使用 Lync Server 2013, 用户联系人可以存储在 Exchange 2013 和统一联系人存储中。</span><span class="sxs-lookup"><span data-stu-id="bd13a-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="bd13a-118">使用单个联系人存储可使用户只保留一组联系人, 其中一组联系人在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中可用。</span><span class="sxs-lookup"><span data-stu-id="bd13a-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="bd13a-119">**从 OWA 安排 Lync 会议**。</span><span class="sxs-lookup"><span data-stu-id="bd13a-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="bd13a-120">使用 Lync Server 2013 和 Exchange 2013 集成, 用户可以从 Outlook Web Access 2013 中安排 Lync 会议。</span><span class="sxs-lookup"><span data-stu-id="bd13a-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="bd13a-121">**高分辨率照片**。</span><span class="sxs-lookup"><span data-stu-id="bd13a-121">**High resolution photos**.</span></span> <span data-ttu-id="bd13a-122">Lync 2010 仅显示您的联系人的少量照片;这是因为这些照片存储在 Active Directory 中, 并且 Active Directory 在存储的照片上施加48像素大小限制的48像素。</span><span class="sxs-lookup"><span data-stu-id="bd13a-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="bd13a-123">但是, 对于 Lync Server 2013, 照片可以存储在 Microsoft Exchange 中;这允许高分辨率的照片, 最大为648像素乘以648像素。</span><span class="sxs-lookup"><span data-stu-id="bd13a-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="bd13a-124">正如你所料, Lync 2013 已升级为允许显示这些高分辨率的照片。</span><span class="sxs-lookup"><span data-stu-id="bd13a-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="bd13a-125">请记住, 这些新功能需要同时使用 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="bd13a-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="bd13a-126">此外, 希望充分利用这些新功能的用户必须在 Lync Server 2013 和 Exchange 2013 上拥有帐户, 并且必须使用最新版本的客户端软件 (如 Lync 2013)。</span><span class="sxs-lookup"><span data-stu-id="bd13a-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="bd13a-127">例如, 在 Lync Server 2010 上托管的用户不能使用 "统一联系人存储";同样, 无法在 Lync 2010 中显示高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="bd13a-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="bd13a-128">本文档提供有关如何集成 Lync Server 2013 和 Exchange 2013 的信息。</span><span class="sxs-lookup"><span data-stu-id="bd13a-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="bd13a-129">包括有关启用新功能 (如存档集成和统一联系人存储) 的分步信息。</span><span class="sxs-lookup"><span data-stu-id="bd13a-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="bd13a-130">本文档不执行的操作是讨论这两种产品的初始设置和配置。</span><span class="sxs-lookup"><span data-stu-id="bd13a-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="bd13a-131">有关部署 Lync Server 2013 的详细信息, 请参阅 Lync Server 2013 技术[http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)中心。</span><span class="sxs-lookup"><span data-stu-id="bd13a-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="bd13a-132">有关部署 Exchange 2013 的详细信息, 请参阅 Exchange 2013 技术[http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)中心。</span><span class="sxs-lookup"><span data-stu-id="bd13a-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd13a-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd13a-133">In This Section</span></span>

[<span data-ttu-id="bd13a-134">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件</span><span class="sxs-lookup"><span data-stu-id="bd13a-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="bd13a-135">在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="bd13a-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="bd13a-136">将 Microsoft Lync Server 2013 配置为使用 Microsoft Exchange Server 2013 存档</span><span class="sxs-lookup"><span data-stu-id="bd13a-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="bd13a-137">配置 Microsoft SharePoint Server 2013 以搜索已存档的 Microsoft Lync Server 2013 数据</span><span class="sxs-lookup"><span data-stu-id="bd13a-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="bd13a-138">将 Microsoft Lync Server 2013 配置为使用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="bd13a-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="bd13a-139">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</span><span class="sxs-lookup"><span data-stu-id="bd13a-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="bd13a-140">为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息</span><span class="sxs-lookup"><span data-stu-id="bd13a-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="bd13a-141">集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="bd13a-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

