---
title: 'Lync Server 2013: 部署通话管理功能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc8e13127242cb81a1e51af72230c67a6a774111
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="af06a-102">在 Lync Server 2013 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="af06a-102">Deploying call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af06a-103">_**主题上次修改时间:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="af06a-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="af06a-104">企业语音呼叫管理功能控制如何传送和应答传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="af06a-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="af06a-105">Lync Server 2013 提供下列呼叫管理功能:</span><span class="sxs-lookup"><span data-stu-id="af06a-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="af06a-106">**电话寄存:** 允许语音用户暂时寄存呼叫, 然后从同一电话或另一电话中进行选择。</span><span class="sxs-lookup"><span data-stu-id="af06a-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="af06a-107">**组装货:** 通过拨打 "呼叫装货" 组编号, 让用户可以向分配给装货组的另一用户接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="af06a-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="af06a-108">**响应组:** 通过使用查寻组或交互式语音响应 (IVR) 问题和解答将传入呼叫路由到代理组。</span><span class="sxs-lookup"><span data-stu-id="af06a-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="af06a-109">**公告:** 对未分配号码的通话播放消息, 或在别处路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="af06a-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="af06a-110">本部分介绍了如何在企业语音部署期间配置这些呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="af06a-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af06a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="af06a-111">In This Section</span></span>

  - [<span data-ttu-id="af06a-112">在 Lync Server 2013 中配置呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="af06a-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="af06a-113">在 Lync Server 2013 中配置组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="af06a-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="af06a-114">在 Lync Server 2013 中配置响应组</span><span class="sxs-lookup"><span data-stu-id="af06a-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="af06a-115">在 Lync Server 2013 中配置未分配号码的通知</span><span class="sxs-lookup"><span data-stu-id="af06a-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

