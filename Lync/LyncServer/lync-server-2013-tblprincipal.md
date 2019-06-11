---
title: Lync Server 2013：tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="27caa-102">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="27caa-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27caa-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="27caa-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="27caa-104">tblPrincipal 包含所有主体, 包括用户、文件夹和组。</span><span class="sxs-lookup"><span data-stu-id="27caa-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="27caa-105">多</span><span class="sxs-lookup"><span data-stu-id="27caa-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27caa-106">列</span><span class="sxs-lookup"><span data-stu-id="27caa-106">Column</span></span></th>
<th><span data-ttu-id="27caa-107">类型</span><span class="sxs-lookup"><span data-stu-id="27caa-107">Type</span></span></th>
<th><span data-ttu-id="27caa-108">说明</span><span class="sxs-lookup"><span data-stu-id="27caa-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27caa-109">prinID</span><span class="sxs-lookup"><span data-stu-id="27caa-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="27caa-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="27caa-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="27caa-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="27caa-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-114">主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="27caa-114">Principal GUID.</span></span> <span data-ttu-id="27caa-115">它被广泛用作备用主键, 因为它的含义与 Active Directory 域服务空间中的含义相同。</span><span class="sxs-lookup"><span data-stu-id="27caa-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="27caa-116">(缓存主体的 GUID 等于相应的 Active Directory 对象 GUID。)</span><span class="sxs-lookup"><span data-stu-id="27caa-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="27caa-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="27caa-118">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="27caa-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-119">主体 URI。</span><span class="sxs-lookup"><span data-stu-id="27caa-119">Principal URI.</span></span> <span data-ttu-id="27caa-120">SIP 方案用于用户, 并且 ma-grp 用于几乎所有其他内容。</span><span class="sxs-lookup"><span data-stu-id="27caa-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-121">prinName</span><span class="sxs-lookup"><span data-stu-id="27caa-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="27caa-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27caa-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="27caa-123">公用名。</span><span class="sxs-lookup"><span data-stu-id="27caa-123">Common name.</span></span> <span data-ttu-id="27caa-124">仅由用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="27caa-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="27caa-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="27caa-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27caa-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="27caa-127">显示名称。</span><span class="sxs-lookup"><span data-stu-id="27caa-127">Display name.</span></span> <span data-ttu-id="27caa-128">仅由用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="27caa-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="27caa-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="27caa-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27caa-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="27caa-131">公司名称。</span><span class="sxs-lookup"><span data-stu-id="27caa-131">Company name.</span></span> <span data-ttu-id="27caa-132">仅由用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="27caa-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="27caa-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="27caa-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27caa-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="27caa-135">电子邮件。</span><span class="sxs-lookup"><span data-stu-id="27caa-135">Email.</span></span> <span data-ttu-id="27caa-136">仅由用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="27caa-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="27caa-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="27caa-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="27caa-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="27caa-139">Active Directory 对象的域名, 主体是的缓存版本。</span><span class="sxs-lookup"><span data-stu-id="27caa-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="27caa-140">对于非 Active Directory 对象 (如系统用户) 的类型, 可以为 Null。</span><span class="sxs-lookup"><span data-stu-id="27caa-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="27caa-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="27caa-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27caa-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="27caa-143">用户的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="27caa-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="27caa-144">仅由常规用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="27caa-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="27caa-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="27caa-146">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="27caa-147">0: 主体处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27caa-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="27caa-148">1: 主体被禁用, 因为用户的 SIP 功能已被禁用。</span><span class="sxs-lookup"><span data-stu-id="27caa-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="27caa-149">2: 删除主体, 因为关联的 AD 对象已被删除。</span><span class="sxs-lookup"><span data-stu-id="27caa-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="27caa-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="27caa-151">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-152">主体类型 (来自 tblPrincipalType 表)。</span><span class="sxs-lookup"><span data-stu-id="27caa-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="27caa-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="27caa-154">整形</span><span class="sxs-lookup"><span data-stu-id="27caa-154">Int</span></span></p></td>
<td><p><span data-ttu-id="27caa-155">主体的 Lync 池分配。</span><span class="sxs-lookup"><span data-stu-id="27caa-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="27caa-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="27caa-157">整形</span><span class="sxs-lookup"><span data-stu-id="27caa-157">Int</span></span></p></td>
<td><p><span data-ttu-id="27caa-158">用户的持久聊天服务器策略值 (如果存在标记类型策略)。</span><span class="sxs-lookup"><span data-stu-id="27caa-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="27caa-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="27caa-160">int</span><span class="sxs-lookup"><span data-stu-id="27caa-160">int</span></span></p></td>
<td><p><span data-ttu-id="27caa-161">创建者的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="27caa-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="27caa-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="27caa-163">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-164">创建时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="27caa-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="27caa-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="27caa-166">int</span><span class="sxs-lookup"><span data-stu-id="27caa-166">int</span></span></p></td>
<td><p><span data-ttu-id="27caa-167">上次更新此操作的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="27caa-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27caa-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="27caa-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="27caa-169">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-170">上次更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="27caa-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="27caa-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="27caa-172">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="27caa-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="27caa-173">主体的上次 Active Directory 同步刷新的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="27caa-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="27caa-174">标示</span><span class="sxs-lookup"><span data-stu-id="27caa-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27caa-175">列</span><span class="sxs-lookup"><span data-stu-id="27caa-175">Column</span></span></th>
<th><span data-ttu-id="27caa-176">说明</span><span class="sxs-lookup"><span data-stu-id="27caa-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27caa-177">prinID</span><span class="sxs-lookup"><span data-stu-id="27caa-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="27caa-178">主键。</span><span class="sxs-lookup"><span data-stu-id="27caa-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27caa-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="27caa-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="27caa-180">TblPrincipalType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="27caa-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

