---
title: Lync Server 2013：持久聊天服务器概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5fcc87635f302f58606703b57631c71bc907efe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520859"
---
# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f92cf-102">Lync Server 2013 中的持久聊天服务器概述</span><span class="sxs-lookup"><span data-stu-id="f92cf-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f92cf-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f92cf-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f92cf-104">Lync Server 2013、持久聊天服务器使用户能够参与在一段时间内保持的基于主题的多个会话。</span><span class="sxs-lookup"><span data-stu-id="f92cf-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="f92cf-105">持久聊天服务器可帮助您的组织执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f92cf-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="f92cf-106">改善分散在不同地理位置的跨部门团队间的通信。</span><span class="sxs-lookup"><span data-stu-id="f92cf-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="f92cf-107">通过使用持久聊天，团队可以高效地与其他人共享信息、想法和决策。</span><span class="sxs-lookup"><span data-stu-id="f92cf-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="f92cf-108">发布到聊天室的邮件 (的讨论论坛) 可以持续 (即可以在) 的时间内可用，以便来自不同位置和部门的人员可以参与，即使他们不同时联机也是如此。</span><span class="sxs-lookup"><span data-stu-id="f92cf-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="f92cf-109">当用户连接到聊天室时， (backchat 会自动在聊天室中加载) 的可配置的聊天历史记录消息，以便为用户提供对话的上下文。</span><span class="sxs-lookup"><span data-stu-id="f92cf-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="f92cf-110">提高信息感知能力。</span><span class="sxs-lookup"><span data-stu-id="f92cf-110">Improve information awareness.</span></span> <span data-ttu-id="f92cf-111">通过使用客户端筛选器，用户可以在邮件内容中定义关键字（如邮件内容中的关键字或邮件中的 "发件人" 字段的值），以便在持久聊天即时消息或聊天室邮件中满足这些条件时收到通知。</span><span class="sxs-lookup"><span data-stu-id="f92cf-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="f92cf-112">这样一来，用户可以随时了解最感兴趣的内容。</span><span class="sxs-lookup"><span data-stu-id="f92cf-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="f92cf-113">改善组织扩大后的通信。</span><span class="sxs-lookup"><span data-stu-id="f92cf-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="f92cf-114">通过让组织中的其他人轻松地与长时间运行的主题进行协作，并通过提供一个持久位置来共享信息，持久聊天可帮助改进通信。</span><span class="sxs-lookup"><span data-stu-id="f92cf-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="f92cf-115">减少信息过载。</span><span class="sxs-lookup"><span data-stu-id="f92cf-115">Reduce information overload.</span></span> <span data-ttu-id="f92cf-116">用户可以通过使用客户端筛选器关注聊天室和最感兴趣的消息，也可以向其联系人列表添加要关注的聊天室。</span><span class="sxs-lookup"><span data-stu-id="f92cf-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="f92cf-117">扩大重要知识和信息的传播范围。</span><span class="sxs-lookup"><span data-stu-id="f92cf-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="f92cf-118">可以在对话中包含文档和链接，以供所有团队访问。</span><span class="sxs-lookup"><span data-stu-id="f92cf-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="f92cf-119">通过向更广泛的团队提问，用户可以从主题专家的答复中受益。</span><span class="sxs-lookup"><span data-stu-id="f92cf-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="f92cf-120">与其他信息系统的集成使重要的组织数据能够轻松地传递给大型组。</span><span class="sxs-lookup"><span data-stu-id="f92cf-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="f92cf-121">若要在 Lync Server 2013 中启用聊天室，请部署 Lync Server 2013 持久聊天。</span><span class="sxs-lookup"><span data-stu-id="f92cf-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="f92cf-122">有关启用聊天室的信息，请参阅中的持久聊天帮助 <https://go.microsoft.com/fwlink/p/?linkid=270945> 。</span><span class="sxs-lookup"><span data-stu-id="f92cf-122">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="f92cf-123">如果为用户启用 Lync Server，并且已部署 Lync Server 支持，则用户可以安装和使用 Lync 2013 持久聊天以提供聊天室支持。</span><span class="sxs-lookup"><span data-stu-id="f92cf-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="f92cf-124">如果你的组织需要遵守合规性管理法规，可以选择部署持久聊天合规性服务。</span><span class="sxs-lookup"><span data-stu-id="f92cf-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

