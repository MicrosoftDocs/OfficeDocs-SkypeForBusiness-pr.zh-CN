---
title: Lync Server 2013：规划会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="bcd72-102">在 Lync Server 2013 中规划会议</span><span class="sxs-lookup"><span data-stu-id="bcd72-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcd72-103">_**主题上次修改时间:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="bcd72-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="bcd72-104">Lync Server 2013 提供了一组丰富的会议功能:</span><span class="sxs-lookup"><span data-stu-id="bcd72-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="bcd72-105">Web 会议, 包括文档协作、应用程序共享和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="bcd72-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="bcd72-106">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="bcd72-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="bcd72-107">有关安装和配置 Office Web Apps 服务器的详细信息, 请参阅[配置与 Office web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd72-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="bcd72-108">音频/视频 (A/V) 会议, 使用户可以在不需要外部服务 (如 Microsoft Live Meeting 服务或第三方音频桥) 的情况下进行实时音频或视频会议。</span><span class="sxs-lookup"><span data-stu-id="bcd72-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="bcd72-109">电话拨入式会议允许用户通过使用公共交换电话网络 (PSTN) 电话加入 Lync Server 2013 会议的音频部分, 而无需第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="bcd72-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="bcd72-110">即时消息 (IM) 会议, 其中多个参与方在一个即时消息会话中进行通信。</span><span class="sxs-lookup"><span data-stu-id="bcd72-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="bcd72-111">有关 IM 会议的详细信息, 请参阅[Lync Server 2013 中的 "规划前端服务器"、"即时消息" 和 "状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)"。</span><span class="sxs-lookup"><span data-stu-id="bcd72-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="bcd72-112">Lync Server 2013 支持计划的会议和即席会议。</span><span class="sxs-lookup"><span data-stu-id="bcd72-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="bcd72-113">当你部署 Lync Server 2013 (前端服务器) 时, 你可以选择是否同时部署 web 会议、A/V 会议和电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="bcd72-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="bcd72-114">IM 会议功能始终随 Lync Server 2013 前端服务器上的 IM 对话功能一起自动部署。</span><span class="sxs-lookup"><span data-stu-id="bcd72-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bcd72-115">如果你的部署包含使用 Office Communicator 2007 R2 客户 (包括 Live Meeting 控制台或 Microsoft Office Outlook 的会议加载项) 组织的会议, 则会议在迁移到 Lync 后将具有以下限制服务器 2013:</span><span class="sxs-lookup"><span data-stu-id="bcd72-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bcd72-116">会议中的用户将无法使用数据协作功能, 包括文档协作、应用程序共享和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="bcd72-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="bcd72-117">由于 Lync Server 2013 不支持 Office Communicator 2007 R2 客户端, 因此可能会出现稳定性问题。</span><span class="sxs-lookup"><span data-stu-id="bcd72-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="bcd72-118">若要避免这些问题, 请使用适用于 2013 Lync 2010 的 Office Communicator 2007 R2 客户端或适用于 Lync 的联机会议加载项, 重新安排任何使用 Office 2010 或 Outlook 2013 组织的会议 R2 客户端。</span><span class="sxs-lookup"><span data-stu-id="bcd72-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="bcd72-119">以下部分介绍了部署各种类型的会议功能所需的内容, 包括规划过程、组件、硬件和软件要求以及部署过程。</span><span class="sxs-lookup"><span data-stu-id="bcd72-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bcd72-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="bcd72-120">In This Section</span></span>

  - [<span data-ttu-id="bcd72-121">Lync Server 2013 中的会议概述</span><span class="sxs-lookup"><span data-stu-id="bcd72-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="bcd72-122">在 Lync Server 2013 中定义会议要求</span><span class="sxs-lookup"><span data-stu-id="bcd72-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="bcd72-123">Lync Server 2013 中用于会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="bcd72-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="bcd72-124">Lync Server 2013 中的会议技术要求</span><span class="sxs-lookup"><span data-stu-id="bcd72-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="bcd72-125">Lync Server 2013 中会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="bcd72-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="bcd72-126">Lync Server 2013 中的大型会议支持</span><span class="sxs-lookup"><span data-stu-id="bcd72-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

