---
title: Lync Server 2013：规划会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1197dd61ea6ed871b851061d86c8653de32ddc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="b0afa-102">在 Lync Server 2013 中规划会议</span><span class="sxs-lookup"><span data-stu-id="b0afa-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0afa-103">_**上次修改的主题：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="b0afa-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="b0afa-104">Lync Server 2013 提供了一组丰富的会议功能：</span><span class="sxs-lookup"><span data-stu-id="b0afa-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="b0afa-105">Web 会议，其中包括文档协作、应用程序共享和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="b0afa-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="b0afa-106">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="b0afa-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="b0afa-107">有关安装和配置 Office Web Apps Server 的详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="b0afa-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="b0afa-108">音频/视频（A/V）会议，使用户可以在不需要外部服务（如 Microsoft Live Meeting 服务或第三方音频网桥）的情况下进行实时音频或视频会议。</span><span class="sxs-lookup"><span data-stu-id="b0afa-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="b0afa-109">电话拨入式会议，它允许用户在不需要第三方音频会议提供商的情况下使用公用电话交换网（PSTN）电话加入 Lync Server 2013 会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="b0afa-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="b0afa-110">即时消息（IM）会议，在一个 IM 会话中有两个以上的参与方进行通信。</span><span class="sxs-lookup"><span data-stu-id="b0afa-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="b0afa-111">有关 IM 会议的详细信息，请参阅[在 Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="b0afa-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="b0afa-112">Lync Server 2013 支持安排的会议和即席会议。</span><span class="sxs-lookup"><span data-stu-id="b0afa-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="b0afa-113">当您部署 Lync Server 2013 （前端服务器）时，您可以选择是否还要部署 web 会议、A/V 会议和电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="b0afa-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="b0afa-114">IM 会议功能总是随 Lync Server 2013 前端服务器上的 IM 对话功能一起自动部署。</span><span class="sxs-lookup"><span data-stu-id="b0afa-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0afa-115">如果您的部署包括使用 Office Communicator 2007 R2 客户端（包括 Live Meeting 控制台或 Microsoft Office Outlook 的会议外接程序）组织的会议，则在将会议迁移到 Lync 后，会有以下限制：服务器2013：</span><span class="sxs-lookup"><span data-stu-id="b0afa-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b0afa-116">会议中的用户将不能使用数据协作功能，包括文档协作、应用程序共享和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="b0afa-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="b0afa-117">由于 Lync Server 2013 不支持 Office Communicator 2007 R2 客户端，因此可能会出现稳定性问题。</span><span class="sxs-lookup"><span data-stu-id="b0afa-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="b0afa-118">若要避免这些问题，请使用 2013 Lync Online 的联机会议外接程序 for Lync 2010 或联机会议外接程序，重新安排使用 Office Communicator 2007 R2 客户端与 Outlook 2010 或 Outlook 2013 组织的任何会议。</span><span class="sxs-lookup"><span data-stu-id="b0afa-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="b0afa-119">以下各节介绍了部署各种类型的会议功能所需的内容，包括规划过程、组件、硬件和软件要求以及部署过程。</span><span class="sxs-lookup"><span data-stu-id="b0afa-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b0afa-120">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b0afa-120">In This Section</span></span>

  - [<span data-ttu-id="b0afa-121">Lync Server 2013 中的会议概述</span><span class="sxs-lookup"><span data-stu-id="b0afa-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="b0afa-122">在 Lync Server 2013 中定义会议要求</span><span class="sxs-lookup"><span data-stu-id="b0afa-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="b0afa-123">Lync Server 2013 中的会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="b0afa-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="b0afa-124">Lync Server 2013 中的会议的技术要求</span><span class="sxs-lookup"><span data-stu-id="b0afa-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="b0afa-125">Lync Server 2013 中的会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="b0afa-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="b0afa-126">在 Lync Server 2013 中支持大型会议</span><span class="sxs-lookup"><span data-stu-id="b0afa-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

