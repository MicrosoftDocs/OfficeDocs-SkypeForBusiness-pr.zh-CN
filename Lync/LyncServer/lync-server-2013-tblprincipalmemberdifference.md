---
title: Lync Server 2013： tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 681b6699e2542a066b9e5b0709fa64f52991b2fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523659"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="d1fda-102">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="d1fda-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1fda-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d1fda-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d1fda-104">tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除的成员) 后续的 Active Directory 域服务同步步骤尚未处理。</span><span class="sxs-lookup"><span data-stu-id="d1fda-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="d1fda-105">列数</span><span class="sxs-lookup"><span data-stu-id="d1fda-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1fda-106">列</span><span class="sxs-lookup"><span data-stu-id="d1fda-106">Column</span></span></th>
<th><span data-ttu-id="d1fda-107">类型</span><span class="sxs-lookup"><span data-stu-id="d1fda-107">Type</span></span></th>
<th><span data-ttu-id="d1fda-108">说明</span><span class="sxs-lookup"><span data-stu-id="d1fda-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1fda-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d1fda-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d1fda-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="d1fda-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d1fda-111">更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="d1fda-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1fda-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d1fda-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="d1fda-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d1fda-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="d1fda-114">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="d1fda-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1fda-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="d1fda-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="d1fda-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="d1fda-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1fda-p101">在添加成员时，设置为 False。在删除成员时，设置为 True。</span><span class="sxs-lookup"><span data-stu-id="d1fda-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d1fda-119">键</span><span class="sxs-lookup"><span data-stu-id="d1fda-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1fda-120">列</span><span class="sxs-lookup"><span data-stu-id="d1fda-120">Column</span></span></th>
<th><span data-ttu-id="d1fda-121">说明</span><span class="sxs-lookup"><span data-stu-id="d1fda-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1fda-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="d1fda-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="d1fda-123">主键。</span><span class="sxs-lookup"><span data-stu-id="d1fda-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

