---
title: Lync Server 2013：租户表
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
ms.openlocfilehash: b0d2459c169fb93520125ceef7a8076bd51343db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="b99c9-102">Lync Server 2013 中的租户表</span><span class="sxs-lookup"><span data-stu-id="b99c9-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b99c9-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b99c9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b99c9-p101">Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。</span><span class="sxs-lookup"><span data-stu-id="b99c9-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b99c9-106">在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="b99c9-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="b99c9-107">列</span><span class="sxs-lookup"><span data-stu-id="b99c9-107">Column</span></span></th>
<th><span data-ttu-id="b99c9-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="b99c9-108">Data Type</span></span></th>
<th><span data-ttu-id="b99c9-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="b99c9-109">Key/Index</span></span></th>
<th><span data-ttu-id="b99c9-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="b99c9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b99c9-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="b99c9-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="b99c9-112">int</span><span class="sxs-lookup"><span data-stu-id="b99c9-112">int</span></span></p></td>
<td><p><span data-ttu-id="b99c9-113">主</span><span class="sxs-lookup"><span data-stu-id="b99c9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b99c9-114">标识此租户 ID 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b99c9-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b99c9-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="b99c9-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b99c9-116">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="b99c9-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b99c9-117">允许的值：</span><span class="sxs-lookup"><span data-stu-id="b99c9-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="b99c9-118">00000000-0000-0000-0000-000000000000 – 企业</span><span class="sxs-lookup"><span data-stu-id="b99c9-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="b99c9-119">00000000-0000-0000-0000-000000000001 – 联盟</span><span class="sxs-lookup"><span data-stu-id="b99c9-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="b99c9-120">00000000-0000-0000-0000-000000000002 – 匿名</span><span class="sxs-lookup"><span data-stu-id="b99c9-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="b99c9-121">00000000-0000-0000-0000-000000000003 – 公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="b99c9-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

