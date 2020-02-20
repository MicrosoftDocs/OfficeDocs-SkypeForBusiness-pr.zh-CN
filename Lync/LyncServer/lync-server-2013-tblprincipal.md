---
title: Lync Server 2013： tblPrincipal
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
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="bae86-102">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="bae86-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bae86-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bae86-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bae86-104">tblPrincipal 包含所有主体，其中包括用户、文件夹和组。</span><span class="sxs-lookup"><span data-stu-id="bae86-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="bae86-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bae86-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bae86-106">列</span><span class="sxs-lookup"><span data-stu-id="bae86-106">Column</span></span></th>
<th><span data-ttu-id="bae86-107">类型</span><span class="sxs-lookup"><span data-stu-id="bae86-107">Type</span></span></th>
<th><span data-ttu-id="bae86-108">说明</span><span class="sxs-lookup"><span data-stu-id="bae86-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bae86-109">prinID</span><span class="sxs-lookup"><span data-stu-id="bae86-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="bae86-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="bae86-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bae86-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bae86-113">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-114">主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="bae86-114">Principal GUID.</span></span> <span data-ttu-id="bae86-115">它被广泛用作备用主键，因为它的含义与 Active Directory 域服务空间中的含义相同。</span><span class="sxs-lookup"><span data-stu-id="bae86-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="bae86-116">（缓存主体的 GUID 等于相应的 Active Directory 对象 GUID。）</span><span class="sxs-lookup"><span data-stu-id="bae86-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="bae86-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="bae86-118">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-p102">主体 URI。SIP 方案用于用户，ma-grp 用于几乎其他的一切对象。</span><span class="sxs-lookup"><span data-stu-id="bae86-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-121">prinName</span><span class="sxs-lookup"><span data-stu-id="bae86-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="bae86-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bae86-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p103">公用名。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="bae86-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="bae86-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="bae86-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bae86-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p104">显示名称。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="bae86-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="bae86-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="bae86-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bae86-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p105">公司名称。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="bae86-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="bae86-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="bae86-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bae86-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p106">电子邮件。仅供用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="bae86-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="bae86-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="bae86-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="bae86-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p107">主体是其缓存版本的 Active Directory 对象的域名。对于非 Active Directory 对象的类型（例如系统用户），可以为 Null。</span><span class="sxs-lookup"><span data-stu-id="bae86-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bae86-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="bae86-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bae86-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bae86-p108">用户的用户主体名称 (UPN)。仅供常规用户类型使用。</span><span class="sxs-lookup"><span data-stu-id="bae86-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="bae86-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="bae86-146">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bae86-147">0：主体处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bae86-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="bae86-148">1：禁用主体，因为用户的 SIP 功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="bae86-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="bae86-149">2：删除主体，因为关联的 AD 对象已被删除。</span><span class="sxs-lookup"><span data-stu-id="bae86-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="bae86-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="bae86-151">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-152">主体类型（来自 tblPrincipalType 表）。</span><span class="sxs-lookup"><span data-stu-id="bae86-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="bae86-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="bae86-154">Int</span><span class="sxs-lookup"><span data-stu-id="bae86-154">Int</span></span></p></td>
<td><p><span data-ttu-id="bae86-155">主体的 Lync 池分配。</span><span class="sxs-lookup"><span data-stu-id="bae86-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="bae86-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="bae86-157">Int</span><span class="sxs-lookup"><span data-stu-id="bae86-157">Int</span></span></p></td>
<td><p><span data-ttu-id="bae86-158">如果存在标记类型策略，则为用户的持久聊天服务器策略值。</span><span class="sxs-lookup"><span data-stu-id="bae86-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="bae86-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="bae86-160">int</span><span class="sxs-lookup"><span data-stu-id="bae86-160">int</span></span></p></td>
<td><p><span data-ttu-id="bae86-161">创建者的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="bae86-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="bae86-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="bae86-163">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-164">创建时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bae86-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bae86-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="bae86-166">int</span><span class="sxs-lookup"><span data-stu-id="bae86-166">int</span></span></p></td>
<td><p><span data-ttu-id="bae86-167">上次更新它的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="bae86-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae86-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="bae86-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="bae86-169">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-170">上次更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bae86-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="bae86-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="bae86-172">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="bae86-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bae86-173">主体上次进行 Active Directory 同步刷新的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bae86-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bae86-174">Keys</span><span class="sxs-lookup"><span data-stu-id="bae86-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bae86-175">列</span><span class="sxs-lookup"><span data-stu-id="bae86-175">Column</span></span></th>
<th><span data-ttu-id="bae86-176">说明</span><span class="sxs-lookup"><span data-stu-id="bae86-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bae86-177">prinID</span><span class="sxs-lookup"><span data-stu-id="bae86-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="bae86-178">主键。</span><span class="sxs-lookup"><span data-stu-id="bae86-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae86-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="bae86-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="bae86-180">其查找包含在 tblPrincipalType.ptypeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="bae86-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

