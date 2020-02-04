---
title: 管理 Lync Server 2013 持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 067e24a7e1534e355e39f80b6a3fda90e059be14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="25896-102">管理 Lync Server 2013 持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="25896-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25896-103">_**主题上次修改时间：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="25896-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="25896-104">你可以使用 Lync Server 2013 的持久聊天服务器，使多个用户能够参与对话，在其中发布和访问有关特定主题（包括文本、链接和文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="25896-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="25896-105">虽然用户可以在会话期间实时进行通信，但每个会话的内容都是持久的，这意味着它在会话结束后仍然可用。</span><span class="sxs-lookup"><span data-stu-id="25896-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="25896-106">持久聊天室的内容主要包含短文本消息，尽管它可以包含较长的消息（称为*情景*），还包括超链接、表情符和上载的文档。</span><span class="sxs-lookup"><span data-stu-id="25896-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25896-107">Lync 2013 客户端不支持文件上载和下载;但是，它仍然受 Lync Server 2013、持久聊天服务器的支持。</span><span class="sxs-lookup"><span data-stu-id="25896-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="25896-108">旧式群组聊天客户端可以发布和查看文件，但如果同一聊天室是通过 Lync 2013 客户端访问的，它将无法访问文件。</span><span class="sxs-lookup"><span data-stu-id="25896-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="25896-109">对聊天室的访问权限由成员身份列表控制。</span><span class="sxs-lookup"><span data-stu-id="25896-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="25896-110">整个聊天室历史记录可供任何成员进行按时间查看或全文搜索。</span><span class="sxs-lookup"><span data-stu-id="25896-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="25896-111">有关使用持久聊天客户端的详细信息，请参阅规划文档中的 "[规划 Lync server 2013 中的客户端](lync-server-2013-planning-for-clients.md)" 和 "部署文档" 中[lync server 2013 中的客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="25896-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="25896-112">为您的组织设置持久聊天服务器时，请在部署期间指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="25896-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="25896-113">但是，有时你可能需要更改实现持久聊天服务器支持的方式。</span><span class="sxs-lookup"><span data-stu-id="25896-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="25896-114">例如，你可能需要为组织内的特定团队或组设置持续聊天服务器支持和控件的方式不同。</span><span class="sxs-lookup"><span data-stu-id="25896-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="25896-115">本部分提供了可帮助您自定义持久聊天服务器部署的信息和过程。</span><span class="sxs-lookup"><span data-stu-id="25896-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="25896-116">有关可针对持久聊天服务器配置的功能和功能的详细信息，请参阅在计划文档中[定义组织的持久聊天2013服务器的要求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)，以及在规划文档、部署文档或操作文档中的[lync server 2013 中的持久聊天服务器的工作方式](lync-server-2013-how-persistent-chat-server-works.md)。</span><span class="sxs-lookup"><span data-stu-id="25896-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="25896-117">有关为 Lync Server 2013 部署持久聊天服务器的详细信息，请参阅部署文档中[Lync server 2013 中的 "部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)"。</span><span class="sxs-lookup"><span data-stu-id="25896-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25896-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="25896-118">In This Section</span></span>

  - [<span data-ttu-id="25896-119">在 Lync Server 2013 中持久聊天服务器的工作方式</span><span class="sxs-lookup"><span data-stu-id="25896-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="25896-120">使用类别管理持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="25896-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="25896-121">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="25896-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="25896-122">持久聊天服务器最佳做法</span><span class="sxs-lookup"><span data-stu-id="25896-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="25896-123">在 Lync Server 2013 中管理类别、聊天室和加载项</span><span class="sxs-lookup"><span data-stu-id="25896-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="25896-124">在 Lync Server 2013 中管理持久聊天用户访问</span><span class="sxs-lookup"><span data-stu-id="25896-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="25896-125">在 Lync Server 2013 中运行和维护持久聊天系统</span><span class="sxs-lookup"><span data-stu-id="25896-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

