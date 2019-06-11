---
title: 'Lync Server 2013: 配置组呼叫装货号码范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbcbf05fbb73e2023b48bdb1f7e74ecdee6a36bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="c4295-102">在 Lync Server 2013 中配置组呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="c4295-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4295-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c4295-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c4295-104">组呼叫分拣基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4295-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="c4295-105">当您部署组呼叫时, 可将 "呼叫公园轨道" 表配置为指定为 "呼叫装货组号码" 的电话号码范围。</span><span class="sxs-lookup"><span data-stu-id="c4295-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="c4295-106">这些组号码是用户拨打以应答为另一个用户响铃的呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="c4295-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="c4295-107">与呼叫寄存轨道号码类似，呼叫应答组号码需要是没有为其分配用户或电话的虚拟分机号。</span><span class="sxs-lookup"><span data-stu-id="c4295-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="c4295-108">你在其中部署组呼叫装货的每个前端池都可以具有一个或多个呼叫装货组编号范围。</span><span class="sxs-lookup"><span data-stu-id="c4295-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="c4295-109">组编号范围在 Lync Server 部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="c4295-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4295-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="c4295-110">In This Section</span></span>

  - [<span data-ttu-id="c4295-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4295-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="c4295-112">在 Lync Server 2013 中删除组呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="c4295-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

