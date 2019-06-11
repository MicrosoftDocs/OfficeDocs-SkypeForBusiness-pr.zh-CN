---
title: Lync Server 2013：规划持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe82f9504aa6a6fefe85e501297edf44da4ba29c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="97496-102">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="97496-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97496-103">_**主题上次修改时间:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="97496-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="97496-104">你可以使用 Lync Server 2013 的持久聊天服务器, 使多个用户能够参与对话, 在其中发布和访问有关特定主题 (包括文本、链接和文件) 的内容。</span><span class="sxs-lookup"><span data-stu-id="97496-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="97496-105">尽管在会话过程中用户可以实时通信，但每个会话的内容都是持久存在的，这意味着在会话结束后，内容仍然可用。</span><span class="sxs-lookup"><span data-stu-id="97496-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="97496-106">本部分介绍 Lync Server 2013、持久聊天服务器部署中的规划注意事项, 包括定义要求、识别组件和受支持的拓扑以及部署建议。</span><span class="sxs-lookup"><span data-stu-id="97496-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97496-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="97496-107">In This Section</span></span>

  - [<span data-ttu-id="97496-108">Lync Server 2013 中的持久聊天服务器概述</span><span class="sxs-lookup"><span data-stu-id="97496-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="97496-109">在 Lync Server 2013 中持久聊天服务器的工作方式</span><span class="sxs-lookup"><span data-stu-id="97496-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="97496-110">在 Lync Server 2013 中定义持久聊天服务器要求</span><span class="sxs-lookup"><span data-stu-id="97496-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="97496-111">Lync Server 2013 中持久聊天服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="97496-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="97496-112">Lync Server 2013 中持久聊天服务器的技术要求</span><span class="sxs-lookup"><span data-stu-id="97496-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="97496-113">在 Lync Server 2013 中设置持久聊天服务器的系统和基础结构</span><span class="sxs-lookup"><span data-stu-id="97496-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="97496-114">Lync Server 2013 中的持久聊天服务器的部署清单</span><span class="sxs-lookup"><span data-stu-id="97496-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

