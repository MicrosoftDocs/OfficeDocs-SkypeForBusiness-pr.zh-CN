---
title: Lync Server 2013：前端服务器、即时消息和状态的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="1177f-102">Lync Server 2013 中前端服务器、即时消息和状态的功能</span><span class="sxs-lookup"><span data-stu-id="1177f-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1177f-103">_**主题上次修改时间:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="1177f-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="1177f-104">前端服务器提供大多数 Lync 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="1177f-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="1177f-105">有两个可用版本: Lync Server 企业版 (主要针对较大组织和 Lync Server 标准版设计), 它主要用于需要较小硬件 investement 的小型组织需要高可用性。</span><span class="sxs-lookup"><span data-stu-id="1177f-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="1177f-106">这两个版本都支持所有 Lync Server 工作负荷, 包括即时消息、状态、会议和企业语音。</span><span class="sxs-lookup"><span data-stu-id="1177f-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="1177f-107">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。</span><span class="sxs-lookup"><span data-stu-id="1177f-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="1177f-108">支持双方和多方之间的 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="1177f-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="1177f-109">双方 IM 对话中的一方可以随时将第三方参与者加入对话中。</span><span class="sxs-lookup"><span data-stu-id="1177f-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="1177f-110">发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="1177f-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1177f-111">Lync 和 Communicator 客户参与一次通信时, 通常称为对等。</span><span class="sxs-lookup"><span data-stu-id="1177f-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="1177f-112">从技术上讲, 两个客户在一次对话中进行通信, 中间有即时消息 multipoint control 单元 (IMMCU)。</span><span class="sxs-lookup"><span data-stu-id="1177f-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="1177f-113">IMMCU 是前端服务器的组件。</span><span class="sxs-lookup"><span data-stu-id="1177f-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="1177f-114">将 IMMCU 放入所需的通信工作流中, 可使呼叫详细记录和前端服务器启用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="1177f-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="1177f-115">通信来自客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 (假设使用了推荐的传输层安全性)。</span><span class="sxs-lookup"><span data-stu-id="1177f-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="1177f-116">根据设计, 仅当 Lync Server 和 IMMCU 处于活动状态且可用时, 才能使用对等通信 (以及多方 IM)。</span><span class="sxs-lookup"><span data-stu-id="1177f-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="1177f-117">"*状态*" 向用户提供有关网络上其他人的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="1177f-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="1177f-118">用户的状态所提供的信息有助于其他人决定是否应尝试与该用户联系，以及使用即时消息、电话还是电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1177f-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="1177f-119">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="1177f-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="1177f-120">此状态显示为 Lync 和其他状态感知应用程序中的 "状态" 图标, 包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术、Microsoft Word 和 Microsoft Excel 电子表格软件业.</span><span class="sxs-lookup"><span data-stu-id="1177f-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="1177f-121">状态图标表明用户当前是否有空以及是否愿意进行交流。</span><span class="sxs-lookup"><span data-stu-id="1177f-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

