---
title: Lync Server 2013：规划共享线路外观
description: Lync Server 2013：规划共享线路外观。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c34a4792d6df9b37b138c08881699dfcdf684d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554378"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="3ba8c-103">在 Lync Server 2013 中规划共享线路外观</span><span class="sxs-lookup"><span data-stu-id="3ba8c-103">Plan for Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ba8c-104">_**上次修改的主题：** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="3ba8c-104">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="3ba8c-105">阅读本主题，了解如何在 Lync Server 2013 中规划共享线路外观 (SLA) ，累积更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-105">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="3ba8c-106">共享线路外观是 Lync Server 2013 中的一项功能，累积更新4月2016，用于处理对特定号码（称为共享号码）的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-106">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="3ba8c-107">SLA 可以将任何已启用企业语音的 Lync 用户配置为具有多个线路的共享号码，以响应多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-107">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="3ba8c-108">实际上不会在共享号码上接收呼叫，而是将其转发给充当共享号码的代理人的用户。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-108">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="3ba8c-109">任何一个代理都可以接听呼叫，而代理的其余部分会在他们的电话上收到通知，告知他们接听呼叫的人以及哪些线路因结果而变得占线。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-109">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="3ba8c-110">可以为 SLA 中的共享号码配置行数和代理人。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-110">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="3ba8c-111">此外，高级选项（例如 BusyOption (在所有线路忙) 和 (MissedCallOption 中时，如果没有任何代理挑选呼叫) 的情况下，也可以为共享号码进行配置。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-111">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="3ba8c-112">仅在以下电话设备上支持 SLA (计算机、移动电话或其他设备上的 Lync 客户端不支持) ：</span><span class="sxs-lookup"><span data-stu-id="3ba8c-112">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="3ba8c-113">带有固件更新5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="3ba8c-113">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3ba8c-114">带有固件更新5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="3ba8c-114">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3ba8c-115">带有固件更新5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="3ba8c-115">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3ba8c-116">带有固件更新5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="3ba8c-116">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="3ba8c-117">SLA 是 Lync Server 2013 中的一项新功能，累积更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-117">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="3ba8c-118">有关部署 SLA 的信息，请参阅 [在 Lync Server 2013 中部署共享线路外观](lync-server-2013-deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-118">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="3ba8c-119">功能列表</span><span class="sxs-lookup"><span data-stu-id="3ba8c-119">Feature List</span></span>

<span data-ttu-id="3ba8c-120">设置 SLA 组可实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="3ba8c-120">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="3ba8c-121">组中的所有代理都可以将入站呼叫应答为相同的共享号码。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-121">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="3ba8c-122">呼叫可以是基于 PSTN 的，也可以是基于 SIP 的。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-122">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="3ba8c-123">代理人可以保留和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-123">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="3ba8c-124">代理可以将呼叫转移到 SLA 组之外的号码。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-124">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="3ba8c-125">代理可以查看共享号码上当前有多少呼叫，并查看每个呼叫的状态。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-125">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="3ba8c-126">您可以为共享号码配置最大并发呼叫数。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-126">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="3ba8c-127">您还可以设置在达到此最大值后您希望如何处理其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-127">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="3ba8c-128">多余的呼叫可以通过占线信号被拒绝，将其转发到备用号码，或转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-128">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="3ba8c-129">您可以配置在特定时间) 处理时，您希望未选取的未接来电 (呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-129">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="3ba8c-130">如果为组标识启用语音邮件，则未接来电将自动转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-130">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="3ba8c-131">如果您没有为组标识启用 (共享号码) 的语音邮件，则可以选择使用占线信号拒绝的未接来电，并将其转接至备用号码或断开连接。</span><span class="sxs-lookup"><span data-stu-id="3ba8c-131">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

