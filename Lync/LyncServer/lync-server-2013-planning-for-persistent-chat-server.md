---
title: Lync Server 2013：规划持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37208a366ae1cac70733113d6b15605886f34e97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521959"
---
# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3d1cc-102">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="3d1cc-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d1cc-103">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="3d1cc-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="3d1cc-104">您可以使用 Lync Server 2013 和持久聊天服务器，使多个用户可以参与对话，在其中发布和访问有关特定主题（包括文本、链接和文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="3d1cc-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="3d1cc-105">尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。</span><span class="sxs-lookup"><span data-stu-id="3d1cc-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="3d1cc-106">本节介绍 Lync Server 2013、持久聊天服务器部署中的规划注意事项，包括定义要求、识别组件和受支持的拓扑以及部署建议。</span><span class="sxs-lookup"><span data-stu-id="3d1cc-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d1cc-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3d1cc-107">In This Section</span></span>

  - [<span data-ttu-id="3d1cc-108">Lync Server 2013 中的持久聊天服务器概述</span><span class="sxs-lookup"><span data-stu-id="3d1cc-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="3d1cc-109">Lync Server 2013 中持久聊天服务器的工作原理</span><span class="sxs-lookup"><span data-stu-id="3d1cc-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="3d1cc-110">定义您的组织在 Lync Server 2013 中的持久聊天服务器的要求</span><span class="sxs-lookup"><span data-stu-id="3d1cc-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="3d1cc-111">Lync Server 2013 中持久聊天服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="3d1cc-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="3d1cc-112">Lync Server 2013 中持久聊天服务器的技术要求</span><span class="sxs-lookup"><span data-stu-id="3d1cc-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="3d1cc-113">在 Lync Server 2013 中为持久聊天服务器设置系统和基础结构</span><span class="sxs-lookup"><span data-stu-id="3d1cc-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="3d1cc-114">Lync Server 2013 中持久聊天服务器的部署清单</span><span class="sxs-lookup"><span data-stu-id="3d1cc-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

