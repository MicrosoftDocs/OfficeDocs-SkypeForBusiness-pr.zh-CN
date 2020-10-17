---
title: Lync Server 2013：租户表
description: Lync Server 2013：租户表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96025dfd9fb42a6083f7f3daca98e243f01a8516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568528"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="c84fc-103">Lync Server 2013 中的租户表</span><span class="sxs-lookup"><span data-stu-id="c84fc-103">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c84fc-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c84fc-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c84fc-p101">Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。</span><span class="sxs-lookup"><span data-stu-id="c84fc-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c84fc-107">在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="c84fc-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c84fc-108">列</span><span class="sxs-lookup"><span data-stu-id="c84fc-108">Column</span></span></th>
<th><span data-ttu-id="c84fc-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="c84fc-109">Data Type</span></span></th>
<th><span data-ttu-id="c84fc-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="c84fc-110">Key/Index</span></span></th>
<th><span data-ttu-id="c84fc-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="c84fc-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c84fc-112"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="c84fc-112"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="c84fc-113">int</span><span class="sxs-lookup"><span data-stu-id="c84fc-113">int</span></span></p></td>
<td><p><span data-ttu-id="c84fc-114">主</span><span class="sxs-lookup"><span data-stu-id="c84fc-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="c84fc-115">标识此租户 ID 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="c84fc-115">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c84fc-116"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="c84fc-116"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c84fc-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c84fc-117">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c84fc-118">允许的值：</span><span class="sxs-lookup"><span data-stu-id="c84fc-118">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="c84fc-119">00000000-0000-0000-0000-000000000000 – 企业</span><span class="sxs-lookup"><span data-stu-id="c84fc-119">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="c84fc-120">00000000-0000-0000-0000-000000000001 – 联盟</span><span class="sxs-lookup"><span data-stu-id="c84fc-120">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="c84fc-121">00000000-0000-0000-0000-000000000002 – 匿名</span><span class="sxs-lookup"><span data-stu-id="c84fc-121">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="c84fc-122">00000000-0000-0000-0000-000000000003 – 公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="c84fc-122">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

