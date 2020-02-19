---
title: Lync Server 2013： DeRegisterType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f1bee5dfa5a0f24b46ba51abafee8d0a89b0a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="5257b-102">Lync Server 2013 中的 DeRegisterType 表</span><span class="sxs-lookup"><span data-stu-id="5257b-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5257b-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5257b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5257b-104">DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（例如“客户端已启动”、“注册过期”或“客户端停止响应”）的列表。</span><span class="sxs-lookup"><span data-stu-id="5257b-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5257b-105">列</span><span class="sxs-lookup"><span data-stu-id="5257b-105">Column</span></span></th>
<th><span data-ttu-id="5257b-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="5257b-106">Data Type</span></span></th>
<th><span data-ttu-id="5257b-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="5257b-107">Key/Index</span></span></th>
<th><span data-ttu-id="5257b-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="5257b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5257b-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5257b-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5257b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="5257b-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5257b-111">主</span><span class="sxs-lookup"><span data-stu-id="5257b-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5257b-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="5257b-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="5257b-113">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="5257b-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5257b-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="5257b-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="5257b-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="5257b-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="5257b-116">1 -- 客户端启动的取消注册</span><span class="sxs-lookup"><span data-stu-id="5257b-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="5257b-117">2 -- 注册过期</span><span class="sxs-lookup"><span data-stu-id="5257b-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="5257b-118">3 – 客户端崩溃</span><span class="sxs-lookup"><span data-stu-id="5257b-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="5257b-119">4 -- 用户属性已更改</span><span class="sxs-lookup"><span data-stu-id="5257b-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="5257b-120">5 – 首选注册器已更改</span><span class="sxs-lookup"><span data-stu-id="5257b-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="5257b-121">6 -- 旧客户端处于生存模式</span><span class="sxs-lookup"><span data-stu-id="5257b-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

