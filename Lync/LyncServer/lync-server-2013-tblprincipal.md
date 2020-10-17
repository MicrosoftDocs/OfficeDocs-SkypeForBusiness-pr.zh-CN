---
title: Lync Server 2013： tblPrincipal
description: Lync Server 2013： tblPrincipal。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547488"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="c8a83-103">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="c8a83-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8a83-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c8a83-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c8a83-105">tblPrincipal 包含所有主体，其中包括用户、文件夹和组。</span><span class="sxs-lookup"><span data-stu-id="c8a83-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="c8a83-106">列数</span><span class="sxs-lookup"><span data-stu-id="c8a83-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8a83-107">列</span><span class="sxs-lookup"><span data-stu-id="c8a83-107">Column</span></span></th>
<th><span data-ttu-id="c8a83-108">类型</span><span class="sxs-lookup"><span data-stu-id="c8a83-108">Type</span></span></th>
<th><span data-ttu-id="c8a83-109">说明</span><span class="sxs-lookup"><span data-stu-id="c8a83-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-110">prinID</span><span class="sxs-lookup"><span data-stu-id="c8a83-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-112">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="c8a83-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c8a83-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c8a83-114">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-115">主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="c8a83-115">Principal GUID.</span></span> <span data-ttu-id="c8a83-116">它被广泛用作备用主键，因为它的含义与 Active Directory 域服务空间中的含义相同。</span><span class="sxs-lookup"><span data-stu-id="c8a83-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="c8a83-117"> (缓存的主体的 GUID 等于相应的 Active Directory 对象 GUID。 ) </span><span class="sxs-lookup"><span data-stu-id="c8a83-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="c8a83-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="c8a83-119">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p102">主体 URI。SIP 方案用于用户，ma-grp 用于几乎其他的一切对象。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-122">prinName</span><span class="sxs-lookup"><span data-stu-id="c8a83-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="c8a83-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c8a83-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p103">公用名。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="c8a83-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="c8a83-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c8a83-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p104">显示名称。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="c8a83-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="c8a83-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c8a83-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p105">公司名称。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="c8a83-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="c8a83-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c8a83-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p106">电子邮件。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c8a83-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="c8a83-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="c8a83-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p107">主体是其缓存版本的 Active Directory 对象的域名。对于非 Active Directory 对象的类型（例如系统用户），可以为 Null。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c8a83-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="c8a83-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c8a83-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c8a83-p108">用户的用户主体名称 (UPN)。仅供常规用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="c8a83-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="c8a83-147">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8a83-148">0：主体处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c8a83-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="c8a83-149">1：禁用主体，因为用户的 SIP 功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="c8a83-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="c8a83-150">2：删除主体，因为关联的 AD 对象已被删除。</span><span class="sxs-lookup"><span data-stu-id="c8a83-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="c8a83-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-152">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-153">主体类型（来自 tblPrincipalType 表）。</span><span class="sxs-lookup"><span data-stu-id="c8a83-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="c8a83-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-155">Int</span><span class="sxs-lookup"><span data-stu-id="c8a83-155">Int</span></span></p></td>
<td><p><span data-ttu-id="c8a83-156">主体的 Lync 池分配。</span><span class="sxs-lookup"><span data-stu-id="c8a83-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="c8a83-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-158">Int</span><span class="sxs-lookup"><span data-stu-id="c8a83-158">Int</span></span></p></td>
<td><p><span data-ttu-id="c8a83-159">如果存在标记类型策略，则为用户的持久聊天服务器策略值。</span><span class="sxs-lookup"><span data-stu-id="c8a83-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="c8a83-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="c8a83-161">int</span><span class="sxs-lookup"><span data-stu-id="c8a83-161">int</span></span></p></td>
<td><p><span data-ttu-id="c8a83-162">创建者的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="c8a83-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="c8a83-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="c8a83-164">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-165">创建时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="c8a83-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="c8a83-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="c8a83-167">int</span><span class="sxs-lookup"><span data-stu-id="c8a83-167">int</span></span></p></td>
<td><p><span data-ttu-id="c8a83-168">上次更新它的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8a83-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="c8a83-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="c8a83-170">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-171">上次更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="c8a83-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="c8a83-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="c8a83-173">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="c8a83-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c8a83-174">主体上次进行 Active Directory 同步刷新的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="c8a83-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c8a83-175">Keys</span><span class="sxs-lookup"><span data-stu-id="c8a83-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8a83-176">列</span><span class="sxs-lookup"><span data-stu-id="c8a83-176">Column</span></span></th>
<th><span data-ttu-id="c8a83-177">说明</span><span class="sxs-lookup"><span data-stu-id="c8a83-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8a83-178">prinID</span><span class="sxs-lookup"><span data-stu-id="c8a83-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-179">主键。</span><span class="sxs-lookup"><span data-stu-id="c8a83-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8a83-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="c8a83-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="c8a83-181">其查找包含在 tblPrincipalType.ptypeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="c8a83-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

