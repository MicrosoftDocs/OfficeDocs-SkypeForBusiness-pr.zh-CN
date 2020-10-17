---
title: Lync Server 2013：配置组呼叫装货号码范围
description: Lync Server 2013：配置组呼叫装货号码范围。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f0594bd681a157b8ff479846b2f6f1964a09cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553278"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="37c3b-103">在 Lync Server 2013 中配置组呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="37c3b-103">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c3b-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="37c3b-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="37c3b-105">组呼叫应答基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="37c3b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="37c3b-106">当您部署组呼叫应答时，可以使用指定为呼叫应答组号码的电话号码范围配置呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="37c3b-106">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="37c3b-107">这些组号码是用户拨打以接听其他用户拨打的呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="37c3b-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="37c3b-108">与呼叫寄存通道号一样，呼叫应答组号码必须是没有向其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="37c3b-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="37c3b-109">您在其中部署组内呼叫应答的每个前端池都可以有一个或多个呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="37c3b-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="37c3b-110">在 Lync Server 部署中，组号范围必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="37c3b-110">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37c3b-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="37c3b-111">In This Section</span></span>

  - [<span data-ttu-id="37c3b-112">在 Lync Server 2013 中创建或修改组内呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="37c3b-112">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="37c3b-113">在 Lync Server 2013 中删除组呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="37c3b-113">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

