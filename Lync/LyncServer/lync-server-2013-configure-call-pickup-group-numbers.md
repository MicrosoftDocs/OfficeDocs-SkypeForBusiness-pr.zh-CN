---
title: Lync Server 2013：配置呼叫应答组号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e380e5b857a59405d42e382d18d7470395a5f580
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="754db-102">在 Lync Server 2013 中配置呼叫应答组号码</span><span class="sxs-lookup"><span data-stu-id="754db-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754db-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="754db-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="754db-104">组呼叫应答基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="754db-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="754db-105">当您部署组呼叫应答时，可以使用指定为呼叫应答组号码的电话号码范围配置呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="754db-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="754db-106">这些组号码是用户拨打以接听其他用户拨打的呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="754db-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="754db-107">与呼叫寄存通道号一样，呼叫应答组号码必须是没有向其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="754db-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="754db-108">您在其中部署组内呼叫应答的每个前端池都可以有一个或多个呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="754db-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="754db-109">在 Lync Server 部署中，组号范围必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="754db-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="754db-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="754db-110">In This Section</span></span>

[<span data-ttu-id="754db-111">在 Lync Server 2013 中创建或修改组内呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="754db-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

