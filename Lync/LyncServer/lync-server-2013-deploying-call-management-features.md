---
title: Lync Server 2013：部署呼叫管理功能
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
ms.openlocfilehash: 33d3c659e90f2e6603cc114f27b7d800f20a0be4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="54321-102">在 Lync Server 2013 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="54321-102">Deploying call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54321-103">_**上次修改的主题：** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="54321-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="54321-104">企业语音呼叫管理功能控制如何路由和应答传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="54321-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="54321-105">Lync Server 2013 提供以下呼叫管理功能：</span><span class="sxs-lookup"><span data-stu-id="54321-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="54321-106">**呼叫寄存：** 允许语音用户暂时寄存呼叫，然后从同一电话或其他电话中进行挑选。</span><span class="sxs-lookup"><span data-stu-id="54321-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="54321-107">**组装货：** 使用户能够通过拨打呼叫应答组号码来应答分配给分拣组的另一个用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="54321-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="54321-108">**响应组：** 通过使用智能寻线或互动语音响应（IVR）问题和答案，将传入呼叫路由到代理组。</span><span class="sxs-lookup"><span data-stu-id="54321-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="54321-109">**通知：** 为对未分配号码发出的呼叫播放消息，或将呼叫路由到其他位置，或同时进行这两种呼叫。</span><span class="sxs-lookup"><span data-stu-id="54321-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="54321-110">本节介绍如何在企业语音部署过程中配置这些呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="54321-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54321-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="54321-111">In This Section</span></span>

  - [<span data-ttu-id="54321-112">在 Lync Server 2013 中配置呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="54321-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="54321-113">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="54321-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="54321-114">在 Lync Server 2013 中配置响应组</span><span class="sxs-lookup"><span data-stu-id="54321-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="54321-115">在 Lync Server 2013 中配置未分配号码的公告</span><span class="sxs-lookup"><span data-stu-id="54321-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

