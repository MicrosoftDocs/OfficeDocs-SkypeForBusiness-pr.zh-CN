---
title: Lync Server 2013： Grant-CsOUPermission 所做的更改
description: Lync Server 2013： CsOUPermission 所做的更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543608"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="daa77-103">Lync Server 2013 中 Grant-CsOUPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="daa77-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daa77-104">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="daa77-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="daa77-105">若要委派 Lync Server 2013 管理，可以将权限添加到指定的组织单位 (Ou 中) 以便由林准备创建的 RTC 通用组的成员可以访问 Ou，而无需成为 Domain Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="daa77-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="daa77-106">**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="daa77-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="daa77-107">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="daa77-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="daa77-108">在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="daa77-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="daa77-109">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="daa77-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa77-110">Group</span><span class="sxs-lookup"><span data-stu-id="daa77-110">Group</span></span></th>
<th><span data-ttu-id="daa77-111">权限</span><span class="sxs-lookup"><span data-stu-id="daa77-111">Permission</span></span></th>
<th><span data-ttu-id="daa77-112">适用于</span><span class="sxs-lookup"><span data-stu-id="daa77-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa77-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="daa77-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="daa77-114">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="daa77-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="daa77-115">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-117">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-117">List contents</span></span></p>
<p><span data-ttu-id="daa77-118">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-118">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-119">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-120">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-122">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-122">List contents</span></span></p>
<p><span data-ttu-id="daa77-123">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-123">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-124">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-125">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-127">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-128">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-129">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-130">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-131">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-131">Read General-Information</span></span></p>
<p><span data-ttu-id="daa77-132">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="daa77-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="daa77-133">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="daa77-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-135">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-136">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="daa77-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="daa77-137">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-138">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-139">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daa77-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="daa77-140">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="daa77-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="daa77-141">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="daa77-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="daa77-142">在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="daa77-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="daa77-143">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="daa77-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa77-144">Group</span><span class="sxs-lookup"><span data-stu-id="daa77-144">Group</span></span></th>
<th><span data-ttu-id="daa77-145">权限</span><span class="sxs-lookup"><span data-stu-id="daa77-145">Permission</span></span></th>
<th><span data-ttu-id="daa77-146">适用于</span><span class="sxs-lookup"><span data-stu-id="daa77-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa77-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="daa77-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="daa77-148">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="daa77-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="daa77-149">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-151">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-151">List contents</span></span></p>
<p><span data-ttu-id="daa77-152">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-152">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-153">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-154">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-156">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-156">List contents</span></span></p>
<p><span data-ttu-id="daa77-157">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-157">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-158">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-159">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-161">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-162">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="daa77-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="daa77-163">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="daa77-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-165">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-166">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="daa77-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="daa77-167">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="daa77-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="daa77-168">为联系人或 AppContact 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="daa77-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="daa77-169">在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="daa77-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="daa77-170">为联系人对象或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="daa77-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa77-171">Group</span><span class="sxs-lookup"><span data-stu-id="daa77-171">Group</span></span></th>
<th><span data-ttu-id="daa77-172">权限</span><span class="sxs-lookup"><span data-stu-id="daa77-172">Permission</span></span></th>
<th><span data-ttu-id="daa77-173">适用于</span><span class="sxs-lookup"><span data-stu-id="daa77-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa77-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="daa77-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="daa77-175">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="daa77-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="daa77-176">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-178">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-178">List contents</span></span></p>
<p><span data-ttu-id="daa77-179">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-179">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-180">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-181">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-183">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-183">List contents</span></span></p>
<p><span data-ttu-id="daa77-184">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-184">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-185">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-186">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-188">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-189">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-190">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-191">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-192">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-192">Read General-Information</span></span></p>
<p><span data-ttu-id="daa77-193">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="daa77-194">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="daa77-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="daa77-195">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="daa77-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-197">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-198">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="daa77-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="daa77-199">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="daa77-199">Write displayName</span></span></p>
<p><span data-ttu-id="daa77-200">写入 description</span><span class="sxs-lookup"><span data-stu-id="daa77-200">Write description</span></span></p>
<p><span data-ttu-id="daa77-201">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="daa77-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="daa77-202">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="daa77-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="daa77-203">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-204">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-205">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daa77-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="daa77-206">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="daa77-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="daa77-207">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="daa77-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="daa77-208">在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="daa77-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="daa77-209">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="daa77-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa77-210">Group</span><span class="sxs-lookup"><span data-stu-id="daa77-210">Group</span></span></th>
<th><span data-ttu-id="daa77-211">权限</span><span class="sxs-lookup"><span data-stu-id="daa77-211">Permission</span></span></th>
<th><span data-ttu-id="daa77-212">适用于</span><span class="sxs-lookup"><span data-stu-id="daa77-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa77-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="daa77-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="daa77-214">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="daa77-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="daa77-215">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-217">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-217">List contents</span></span></p>
<p><span data-ttu-id="daa77-218">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-218">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-219">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-220">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-222">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-222">List contents</span></span></p>
<p><span data-ttu-id="daa77-223">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-223">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-224">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-225">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-227">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-228">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-229">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-230">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-231">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="daa77-232">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-232">Read General-Information</span></span></p>
<p><span data-ttu-id="daa77-233">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="daa77-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="daa77-234">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="daa77-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-236">创建子级</span><span class="sxs-lookup"><span data-stu-id="daa77-236">Create child</span></span></p>
<p><span data-ttu-id="daa77-237">删除子级</span><span class="sxs-lookup"><span data-stu-id="daa77-237">Delete child</span></span></p>
<p><span data-ttu-id="daa77-238">删除树</span><span class="sxs-lookup"><span data-stu-id="daa77-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="daa77-239">Contact</span><span class="sxs-lookup"><span data-stu-id="daa77-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-241">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="daa77-241">Write displayName</span></span></p>
<p><span data-ttu-id="daa77-242">写入 description</span><span class="sxs-lookup"><span data-stu-id="daa77-242">Write description</span></span></p>
<p><span data-ttu-id="daa77-243">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="daa77-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="daa77-244">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="daa77-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-246">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-247">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="daa77-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="daa77-248">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="daa77-248">Write displayName</span></span></p>
<p><span data-ttu-id="daa77-249">写入 description</span><span class="sxs-lookup"><span data-stu-id="daa77-249">Write description</span></span></p>
<p><span data-ttu-id="daa77-250">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="daa77-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="daa77-251">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="daa77-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="daa77-252">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-253">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-254">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daa77-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="daa77-255">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="daa77-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="daa77-256">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="daa77-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="daa77-257">在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="daa77-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="daa77-258">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="daa77-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa77-259">Group</span><span class="sxs-lookup"><span data-stu-id="daa77-259">Group</span></span></th>
<th><span data-ttu-id="daa77-260">权限</span><span class="sxs-lookup"><span data-stu-id="daa77-260">Permission</span></span></th>
<th><span data-ttu-id="daa77-261">适用于</span><span class="sxs-lookup"><span data-stu-id="daa77-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa77-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="daa77-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="daa77-263">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="daa77-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="daa77-264">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-266">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-266">List contents</span></span></p>
<p><span data-ttu-id="daa77-267">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-267">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-268">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-269">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-271">列出内容</span><span class="sxs-lookup"><span data-stu-id="daa77-271">List contents</span></span></p>
<p><span data-ttu-id="daa77-272">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="daa77-272">Read all properties</span></span></p>
<p><span data-ttu-id="daa77-273">读取权限</span><span class="sxs-lookup"><span data-stu-id="daa77-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="daa77-274">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="daa77-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa77-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="daa77-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="daa77-276">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-277">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-278">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-279">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="daa77-280">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="daa77-281">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="daa77-281">Read General-Information</span></span></p>
<p><span data-ttu-id="daa77-282">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="daa77-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="daa77-283">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="daa77-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa77-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="daa77-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="daa77-285">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="daa77-286">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="daa77-287">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="daa77-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="daa77-288">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daa77-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="daa77-289">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="daa77-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

