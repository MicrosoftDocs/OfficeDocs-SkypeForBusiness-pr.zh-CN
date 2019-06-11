---
title: 'Lync Server 2013: 通过授予 CsOUPermission 进行的更改'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="ffe3d-102">Lync Server 2013 中的 "授权-CsOUPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe3d-103">_**主题上次修改时间:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ffe3d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ffe3d-104">若要委派 Lync Server 2013 管理, 可以向指定的组织单位 (Ou) 添加权限, 以便林准备创建的 RTC 通用组的成员无需成为域管理员组的成员即可访问 Ou。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ffe3d-105">**CsOuPermission** cmdlet 按下表中指定的方式向指定 OU 中的对象授予权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="ffe3d-106">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="ffe3d-107">在 OU 上运行用户对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="ffe3d-108">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe3d-109">团队</span><span class="sxs-lookup"><span data-stu-id="ffe3d-109">Group</span></span></th>
<th><span data-ttu-id="ffe3d-110">权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-110">Permission</span></span></th>
<th><span data-ttu-id="ffe3d-111">适用于</span><span class="sxs-lookup"><span data-stu-id="ffe3d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffe3d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-113">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-114">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-116">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-116">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-117">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-117">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-119">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-121">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-121">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-122">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-122">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-123">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-124">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-126">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-127">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-128">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-129">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-130">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="ffe3d-131">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="ffe3d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-132">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-134">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-135">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ffe3d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffe3d-136">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-137">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-138">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ffe3d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-139">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="ffe3d-140">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="ffe3d-141">在 OU 上运行计算机对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="ffe3d-142">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe3d-143">团队</span><span class="sxs-lookup"><span data-stu-id="ffe3d-143">Group</span></span></th>
<th><span data-ttu-id="ffe3d-144">权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-144">Permission</span></span></th>
<th><span data-ttu-id="ffe3d-145">适用于</span><span class="sxs-lookup"><span data-stu-id="ffe3d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffe3d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-147">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-148">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-150">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-150">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-151">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-151">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-152">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-153">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-155">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-155">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-156">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-156">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-157">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-158">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-160">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-161">读取已验证的 DNS 主机名</span><span class="sxs-lookup"><span data-stu-id="ffe3d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-162">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-164">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-165">读取已验证的 DNS 主机名</span><span class="sxs-lookup"><span data-stu-id="ffe3d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-166">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffe3d-167">授予联系人或 AppContact 对象的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="ffe3d-168">当你为某个 OU 上的 Contact 对象或 AppContact 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="ffe3d-169">为联系人或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe3d-170">团队</span><span class="sxs-lookup"><span data-stu-id="ffe3d-170">Group</span></span></th>
<th><span data-ttu-id="ffe3d-171">权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-171">Permission</span></span></th>
<th><span data-ttu-id="ffe3d-172">适用于</span><span class="sxs-lookup"><span data-stu-id="ffe3d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffe3d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-174">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-175">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-177">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-177">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-178">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-178">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-179">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-180">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-182">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-182">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-183">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-183">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-184">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-185">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-187">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-188">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-189">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-190">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-191">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="ffe3d-192">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffe3d-193">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="ffe3d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-194">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-196">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-197">写 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="ffe3d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffe3d-198">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="ffe3d-198">Write displayName</span></span></p>
<p><span data-ttu-id="ffe3d-199">写入说明</span><span class="sxs-lookup"><span data-stu-id="ffe3d-199">Write description</span></span></p>
<p><span data-ttu-id="ffe3d-200">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ffe3d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffe3d-201">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ffe3d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffe3d-202">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-203">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-204">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ffe3d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-205">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="ffe3d-206">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="ffe3d-207">在 OU 上运行设备对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="ffe3d-208">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe3d-209">团队</span><span class="sxs-lookup"><span data-stu-id="ffe3d-209">Group</span></span></th>
<th><span data-ttu-id="ffe3d-210">权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-210">Permission</span></span></th>
<th><span data-ttu-id="ffe3d-211">适用于</span><span class="sxs-lookup"><span data-stu-id="ffe3d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffe3d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-213">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-214">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-216">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-216">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-217">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-217">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-218">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-219">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-221">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-221">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-222">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-222">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-223">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-224">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-226">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-227">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-228">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-229">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-230">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffe3d-231">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="ffe3d-232">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="ffe3d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-233">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-235">创建子元素</span><span class="sxs-lookup"><span data-stu-id="ffe3d-235">Create child</span></span></p>
<p><span data-ttu-id="ffe3d-236">删除子元素</span><span class="sxs-lookup"><span data-stu-id="ffe3d-236">Delete child</span></span></p>
<p><span data-ttu-id="ffe3d-237">删除树</span><span class="sxs-lookup"><span data-stu-id="ffe3d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-238">联系人</span><span class="sxs-lookup"><span data-stu-id="ffe3d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-240">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="ffe3d-240">Write displayName</span></span></p>
<p><span data-ttu-id="ffe3d-241">写入说明</span><span class="sxs-lookup"><span data-stu-id="ffe3d-241">Write description</span></span></p>
<p><span data-ttu-id="ffe3d-242">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ffe3d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-243">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-245">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-246">写 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="ffe3d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ffe3d-247">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="ffe3d-247">Write displayName</span></span></p>
<p><span data-ttu-id="ffe3d-248">写入说明</span><span class="sxs-lookup"><span data-stu-id="ffe3d-248">Write description</span></span></p>
<p><span data-ttu-id="ffe3d-249">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ffe3d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ffe3d-250">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ffe3d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ffe3d-251">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-252">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-253">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ffe3d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-254">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="ffe3d-255">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="ffe3d-256">当你针对 OU 上的 InetOrgPerson 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="ffe3d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="ffe3d-257">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffe3d-258">团队</span><span class="sxs-lookup"><span data-stu-id="ffe3d-258">Group</span></span></th>
<th><span data-ttu-id="ffe3d-259">权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-259">Permission</span></span></th>
<th><span data-ttu-id="ffe3d-260">适用于</span><span class="sxs-lookup"><span data-stu-id="ffe3d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ffe3d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-262">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="ffe3d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-263">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-265">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-265">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-266">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-266">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-267">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-268">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-270">列表内容</span><span class="sxs-lookup"><span data-stu-id="ffe3d-270">List contents</span></span></p>
<p><span data-ttu-id="ffe3d-271">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="ffe3d-271">Read all properties</span></span></p>
<p><span data-ttu-id="ffe3d-272">读取权限</span><span class="sxs-lookup"><span data-stu-id="ffe3d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-273">仅此对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffe3d-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ffe3d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-275">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-276">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-277">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-278">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ffe3d-279">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="ffe3d-280">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="ffe3d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="ffe3d-281">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="ffe3d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-282">子代 inetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffe3d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ffe3d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-284">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-285">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-286">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ffe3d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ffe3d-287">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ffe3d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ffe3d-288">子代 inetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="ffe3d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

