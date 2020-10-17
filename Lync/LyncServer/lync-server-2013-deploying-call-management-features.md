---
title: Lync Server 2013：部署呼叫管理功能
description: Lync Server 2013：部署呼叫管理功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa89b75dbcae9de1069daf99986076b66e0411cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570678"
---
# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="6e041-103">在 Lync Server 2013 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="6e041-103">Deploying call management features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e041-104">_**上次修改的主题：** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="6e041-104">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="6e041-105">企业语音呼叫管理功能控制如何路由和应答传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="6e041-105">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="6e041-106">Lync Server 2013 提供以下呼叫管理功能：</span><span class="sxs-lookup"><span data-stu-id="6e041-106">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="6e041-107">**呼叫寄存：** 允许语音用户暂时寄存呼叫，然后从同一电话或其他电话中进行挑选。</span><span class="sxs-lookup"><span data-stu-id="6e041-107">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="6e041-108">**组装货：** 使用户能够通过拨打呼叫应答组号码来应答分配给分拣组的另一个用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6e041-108">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="6e041-109">**响应组：** 使用智能寻线或互动语音响应将传入呼叫路由到代理组 (IVR) 问题和解答。</span><span class="sxs-lookup"><span data-stu-id="6e041-109">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="6e041-110">**通知：** 为对未分配号码发出的呼叫播放消息，或将呼叫路由到其他位置，或同时进行这两种呼叫。</span><span class="sxs-lookup"><span data-stu-id="6e041-110">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="6e041-111">本节介绍如何在企业语音部署过程中配置这些呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="6e041-111">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e041-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="6e041-112">In This Section</span></span>

  - [<span data-ttu-id="6e041-113">在 Lync Server 2013 中配置呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="6e041-113">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="6e041-114">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="6e041-114">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="6e041-115">在 Lync Server 2013 中配置响应组</span><span class="sxs-lookup"><span data-stu-id="6e041-115">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="6e041-116">在 Lync Server 2013 中配置未分配号码的公告</span><span class="sxs-lookup"><span data-stu-id="6e041-116">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

