---
title: Lync Server 2013：前端服务器、即时消息和状态的特性和功能
description: Lync Server 2013：前端服务器、即时消息和状态的特性和功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543408"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="1deac-103">Lync Server 2013 中前端服务器、即时消息和状态的特性和功能</span><span class="sxs-lookup"><span data-stu-id="1deac-103">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1deac-104">_**上次修改的主题：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="1deac-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="1deac-105">前端服务器提供大多数 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="1deac-105">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="1deac-106">有两种可用的版本： Lync Server Enterprise Edition 主要用于大型组织和 Lync Server Standard Edition，后者主要针对需要较小硬件 investement 且无需高可用性的小型组织设计。</span><span class="sxs-lookup"><span data-stu-id="1deac-106">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="1deac-107">这两个版本都支持所有 Lync Server 工作负载，包括 IM、状态、会议和企业语音。</span><span class="sxs-lookup"><span data-stu-id="1deac-107">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="1deac-p102">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="1deac-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1deac-112">Lync 和 Communicator 客户端参与一次通信时，通常称为对等。</span><span class="sxs-lookup"><span data-stu-id="1deac-112">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="1deac-113">从技术上讲，两个客户端在一次对话中进行通信，即时消息 multipoint 控制单位 (IMMCU) 在中间。</span><span class="sxs-lookup"><span data-stu-id="1deac-113">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="1deac-114">IMMCU 是前端服务器的组件。</span><span class="sxs-lookup"><span data-stu-id="1deac-114">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="1deac-115">将 IMMCU 置于所需的通信工作流中可允许呼叫详细记录和前端服务器启用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="1deac-115">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="1deac-116">通信是从客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 (，假定使用的是建议的传输层安全性) 。</span><span class="sxs-lookup"><span data-stu-id="1deac-116">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="1deac-117">根据设计，只有在 Lync Server 和 IMMCU 处于活动状态且可用时，才能使用对等通信 (以及多方 IM) 。</span><span class="sxs-lookup"><span data-stu-id="1deac-117">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="1deac-118">*状态* 向用户提供网络中其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="1deac-118">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="1deac-119">用户的状态所提供的信息有助于其他人决定是否应尝试与该用户联系，以及使用即时消息、电话还是电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1deac-119">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="1deac-120">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="1deac-120">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="1deac-121">此状态显示为 Lync 中的状态图标和其他状态感知应用程序，包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术、Microsoft Word 和 Microsoft Excel 电子表格软件。</span><span class="sxs-lookup"><span data-stu-id="1deac-121">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="1deac-122">状态图标表明用户当前是否有空以及是否愿意进行交流。</span><span class="sxs-lookup"><span data-stu-id="1deac-122">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

