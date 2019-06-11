---
title: Lync Server 2013 规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning
ms:assetid: 6398cd91-8773-41bc-9b66-725d65ba9d66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398447(v=OCS.15)
ms:contentKeyID: 48184302
ms.date: 12/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fc737ff9b3a457d8227892b6e74575e332d20ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013"></a><span data-ttu-id="bb2e9-102">规划 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb2e9-102">Planning for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb2e9-103">_**主题上次修改时间:** 2014-12-09_</span><span class="sxs-lookup"><span data-stu-id="bb2e9-103">_**Topic Last Modified:** 2014-12-09_</span></span>

<span data-ttu-id="bb2e9-104">本部分中的主题介绍了如何为成功的 Lync 服务器部署进行规划。</span><span class="sxs-lookup"><span data-stu-id="bb2e9-104">The topics in this section describe how to plan for a successful Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb2e9-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="bb2e9-105">In This Section</span></span>

  - [<span data-ttu-id="bb2e9-106">Lync Server 2013 的组织规划</span><span class="sxs-lookup"><span data-stu-id="bb2e9-106">Organization planning for Lync Server 2013</span></span>](lync-server-2013-planning-for-your-organization.md)

  - [<span data-ttu-id="bb2e9-107">确定 Lync Server 2013 的基础结构要求</span><span class="sxs-lookup"><span data-stu-id="bb2e9-107">Determining your infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-determining-your-infrastructure-requirements.md)

  - [<span data-ttu-id="bb2e9-108">Lync Server 2013 的网络规划</span><span class="sxs-lookup"><span data-stu-id="bb2e9-108">Network planning for Lync Server 2013</span></span>](lync-server-2013-network-planning.md)

  - [<span data-ttu-id="bb2e9-109">Lync Server 2013 的容量规划</span><span class="sxs-lookup"><span data-stu-id="bb2e9-109">Capacity planning for Lync Server 2013</span></span>](lync-server-2013-capacity-planning.md)

  - [<span data-ttu-id="bb2e9-110">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="bb2e9-110">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="bb2e9-111">在 Lync Server 2013 中规划可管理性和虚拟化</span><span class="sxs-lookup"><span data-stu-id="bb2e9-111">Planning for manageability and virtualization in Lync Server 2013</span></span>](lync-server-2013-planning-for-manageability-and-virtualization.md)

  - [<span data-ttu-id="bb2e9-112">在 Lync Server 2013 中规划前端服务器、即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="bb2e9-112">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

  - [<span data-ttu-id="bb2e9-113">在 Lync Server 2013 中规划会议</span><span class="sxs-lookup"><span data-stu-id="bb2e9-113">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)

  - [<span data-ttu-id="bb2e9-114">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="bb2e9-114">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)

  - [<span data-ttu-id="bb2e9-115">在 Lync Server 2013 中规划企业语音</span><span class="sxs-lookup"><span data-stu-id="bb2e9-115">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)

  - [<span data-ttu-id="bb2e9-116">在 Lync Server 2013 中规划监控</span><span class="sxs-lookup"><span data-stu-id="bb2e9-116">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)

  - [<span data-ttu-id="bb2e9-117">在 Lync Server 2013 中规划存档</span><span class="sxs-lookup"><span data-stu-id="bb2e9-117">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)

  - [<span data-ttu-id="bb2e9-118">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="bb2e9-118">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)

  - [<span data-ttu-id="bb2e9-119">规划 Exchange Server 与 Lync Server 2013 的集成</span><span class="sxs-lookup"><span data-stu-id="bb2e9-119">Planning for Exchange Server integration with Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-server-integration.md)

  - [<span data-ttu-id="bb2e9-120">在 Lync Server 2013 中规划客户端和设备</span><span class="sxs-lookup"><span data-stu-id="bb2e9-120">Planning for clients and devices in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients-and-devices.md)

  - [<span data-ttu-id="bb2e9-121">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="bb2e9-121">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

  - [<span data-ttu-id="bb2e9-122">在 Lync Server 2013 中规划移动功能</span><span class="sxs-lookup"><span data-stu-id="bb2e9-122">Planning for mobility in Lync Server 2013</span></span>](lync-server-2013-planning-for-mobility.md)

  - [<span data-ttu-id="bb2e9-123">规划 Lync Server 2013 的安全性</span><span class="sxs-lookup"><span data-stu-id="bb2e9-123">Planning for security in Lync Server 2013</span></span>](lync-server-2013-planning-for-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

