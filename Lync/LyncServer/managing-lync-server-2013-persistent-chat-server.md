---
title: 管理 Lync Server 2013 持久聊天服务器
description: 管理 Lync Server 2013、持久聊天服务器。
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
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544578"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="61700-103">管理 Lync Server 2013 持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="61700-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61700-104">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="61700-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="61700-105">您可以使用 Lync Server 2013 和持久聊天服务器，使多个用户可以参与对话，在其中发布和访问有关特定主题（包括文本、链接和文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="61700-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="61700-106">尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。</span><span class="sxs-lookup"><span data-stu-id="61700-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="61700-107">持久聊天室的内容主要由简短的短信组成，尽管它可以包含更长的邮件（称为 *文章*），也可以是超链接、图释和上载的文档。</span><span class="sxs-lookup"><span data-stu-id="61700-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61700-108">Lync 2013 客户端不支持文件上载和下载;但是，它仍然受 Lync Server 2013、持久聊天服务器支持。</span><span class="sxs-lookup"><span data-stu-id="61700-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="61700-109">旧式组聊天客户端可以发布和查看文件，但是，如果通过 Lync 2013 客户端访问相同的聊天室，它将无法访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="61700-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="61700-110">聊天室的访问由成员身份列表控制。</span><span class="sxs-lookup"><span data-stu-id="61700-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="61700-111">完整聊天室历史记录可供任何成员按时间顺序查阅或进行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="61700-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="61700-112">有关使用持久聊天客户端的详细信息，请参阅部署文档中的规划文档中的 [在 Lync server 2013 中规划客户端](lync-server-2013-planning-for-clients.md) 和在 [lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md) 。</span><span class="sxs-lookup"><span data-stu-id="61700-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="61700-113">为组织设置持久聊天服务器时，请在部署过程中指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="61700-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="61700-114">但是，有时您可能需要更改实现持久聊天服务器支持的方式。</span><span class="sxs-lookup"><span data-stu-id="61700-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="61700-115">例如，您可能需要为组织内的特定团队或组设置与之不同的持久聊天服务器支持和控件。</span><span class="sxs-lookup"><span data-stu-id="61700-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="61700-116">本节提供可帮助您自定义持久聊天服务器部署的信息和过程。</span><span class="sxs-lookup"><span data-stu-id="61700-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="61700-117">有关可为持久聊天服务器配置的特性和功能的详细信息，请参阅规划文档中的在 [Lync server 2013 中定义组织的持久聊天服务器要求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) ，以及在规划文档、部署文档或操作文档中的 [持久聊天服务器在 lync server 2013 中的工作方式](lync-server-2013-how-persistent-chat-server-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="61700-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="61700-118">有关为 Lync Server 2013 部署持久聊天服务器的详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="61700-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61700-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="61700-119">In This Section</span></span>

  - [<span data-ttu-id="61700-120">Lync Server 2013 中持久聊天服务器的工作原理</span><span class="sxs-lookup"><span data-stu-id="61700-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="61700-121">使用类别管理持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="61700-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="61700-122">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="61700-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="61700-123">持久聊天服务器最佳实践</span><span class="sxs-lookup"><span data-stu-id="61700-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="61700-124">在 Lync Server 2013 中管理类别、聊天室和外接程序</span><span class="sxs-lookup"><span data-stu-id="61700-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="61700-125">在 Lync Server 2013 中管理持久聊天用户访问</span><span class="sxs-lookup"><span data-stu-id="61700-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="61700-126">在 Lync Server 2013 中运行和维护持久聊天系统</span><span class="sxs-lookup"><span data-stu-id="61700-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

