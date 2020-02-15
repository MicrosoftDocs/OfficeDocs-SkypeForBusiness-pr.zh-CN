---
title: Lync Server 2013：由 Grant-CsOUPermission 所做的更改
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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="23413-102">Lync Server 2013 中的 CsOUPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="23413-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23413-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="23413-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="23413-104">若要委派 Lync Server 2013 管理，可以将权限添加到指定的组织单位（Ou），以便由林准备创建的 RTC 通用组的成员无需成为 Domain Admins 组的成员即可访问 Ou。</span><span class="sxs-lookup"><span data-stu-id="23413-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="23413-105">**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="23413-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="23413-106">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="23413-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="23413-107">在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="23413-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="23413-108">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="23413-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23413-109">Group</span><span class="sxs-lookup"><span data-stu-id="23413-109">Group</span></span></th>
<th><span data-ttu-id="23413-110">权限</span><span class="sxs-lookup"><span data-stu-id="23413-110">Permission</span></span></th>
<th><span data-ttu-id="23413-111">适用于</span><span class="sxs-lookup"><span data-stu-id="23413-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23413-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="23413-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="23413-113">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="23413-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="23413-114">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-116">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-116">List contents</span></span></p>
<p><span data-ttu-id="23413-117">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-117">Read all properties</span></span></p>
<p><span data-ttu-id="23413-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-119">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-121">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-121">List contents</span></span></p>
<p><span data-ttu-id="23413-122">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-122">Read all properties</span></span></p>
<p><span data-ttu-id="23413-123">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-124">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-126">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-127">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-128">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-129">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-130">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="23413-130">Read General-Information</span></span></p>
<p><span data-ttu-id="23413-131">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="23413-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="23413-132">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="23413-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-134">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-135">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="23413-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="23413-136">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-137">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-138">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="23413-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="23413-139">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="23413-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="23413-140">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="23413-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="23413-141">在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="23413-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="23413-142">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="23413-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23413-143">Group</span><span class="sxs-lookup"><span data-stu-id="23413-143">Group</span></span></th>
<th><span data-ttu-id="23413-144">权限</span><span class="sxs-lookup"><span data-stu-id="23413-144">Permission</span></span></th>
<th><span data-ttu-id="23413-145">适用于</span><span class="sxs-lookup"><span data-stu-id="23413-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23413-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="23413-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="23413-147">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="23413-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="23413-148">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-150">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-150">List contents</span></span></p>
<p><span data-ttu-id="23413-151">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-151">Read all properties</span></span></p>
<p><span data-ttu-id="23413-152">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-153">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-155">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-155">List contents</span></span></p>
<p><span data-ttu-id="23413-156">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-156">Read all properties</span></span></p>
<p><span data-ttu-id="23413-157">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-158">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-160">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-161">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="23413-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="23413-162">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="23413-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-164">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-165">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="23413-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="23413-166">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="23413-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="23413-167">为联系人或 AppContact 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="23413-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="23413-168">在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="23413-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="23413-169">为联系人对象或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="23413-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23413-170">Group</span><span class="sxs-lookup"><span data-stu-id="23413-170">Group</span></span></th>
<th><span data-ttu-id="23413-171">权限</span><span class="sxs-lookup"><span data-stu-id="23413-171">Permission</span></span></th>
<th><span data-ttu-id="23413-172">适用于</span><span class="sxs-lookup"><span data-stu-id="23413-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23413-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="23413-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="23413-174">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="23413-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="23413-175">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-177">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-177">List contents</span></span></p>
<p><span data-ttu-id="23413-178">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-178">Read all properties</span></span></p>
<p><span data-ttu-id="23413-179">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-180">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-182">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-182">List contents</span></span></p>
<p><span data-ttu-id="23413-183">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-183">Read all properties</span></span></p>
<p><span data-ttu-id="23413-184">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-185">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-187">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-188">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-189">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-190">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-191">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="23413-191">Read General-Information</span></span></p>
<p><span data-ttu-id="23413-192">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="23413-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="23413-193">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="23413-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="23413-194">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="23413-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-196">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-197">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="23413-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="23413-198">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="23413-198">Write displayName</span></span></p>
<p><span data-ttu-id="23413-199">写入 description</span><span class="sxs-lookup"><span data-stu-id="23413-199">Write description</span></span></p>
<p><span data-ttu-id="23413-200">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="23413-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="23413-201">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="23413-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="23413-202">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-203">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-204">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="23413-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="23413-205">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="23413-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="23413-206">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="23413-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="23413-207">在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="23413-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="23413-208">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="23413-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23413-209">Group</span><span class="sxs-lookup"><span data-stu-id="23413-209">Group</span></span></th>
<th><span data-ttu-id="23413-210">权限</span><span class="sxs-lookup"><span data-stu-id="23413-210">Permission</span></span></th>
<th><span data-ttu-id="23413-211">适用于</span><span class="sxs-lookup"><span data-stu-id="23413-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23413-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="23413-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="23413-213">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="23413-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="23413-214">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-216">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-216">List contents</span></span></p>
<p><span data-ttu-id="23413-217">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-217">Read all properties</span></span></p>
<p><span data-ttu-id="23413-218">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-219">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-221">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-221">List contents</span></span></p>
<p><span data-ttu-id="23413-222">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-222">Read all properties</span></span></p>
<p><span data-ttu-id="23413-223">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-224">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-226">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-227">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-228">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-229">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-230">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="23413-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="23413-231">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="23413-231">Read General-Information</span></span></p>
<p><span data-ttu-id="23413-232">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="23413-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="23413-233">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="23413-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-235">创建子级</span><span class="sxs-lookup"><span data-stu-id="23413-235">Create child</span></span></p>
<p><span data-ttu-id="23413-236">删除子级</span><span class="sxs-lookup"><span data-stu-id="23413-236">Delete child</span></span></p>
<p><span data-ttu-id="23413-237">删除树</span><span class="sxs-lookup"><span data-stu-id="23413-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="23413-238">Contact</span><span class="sxs-lookup"><span data-stu-id="23413-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-240">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="23413-240">Write displayName</span></span></p>
<p><span data-ttu-id="23413-241">写入 description</span><span class="sxs-lookup"><span data-stu-id="23413-241">Write description</span></span></p>
<p><span data-ttu-id="23413-242">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="23413-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="23413-243">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="23413-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-245">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-246">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="23413-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="23413-247">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="23413-247">Write displayName</span></span></p>
<p><span data-ttu-id="23413-248">写入 description</span><span class="sxs-lookup"><span data-stu-id="23413-248">Write description</span></span></p>
<p><span data-ttu-id="23413-249">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="23413-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="23413-250">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="23413-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="23413-251">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-252">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-253">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="23413-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="23413-254">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="23413-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="23413-255">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="23413-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="23413-256">在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="23413-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="23413-257">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="23413-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23413-258">Group</span><span class="sxs-lookup"><span data-stu-id="23413-258">Group</span></span></th>
<th><span data-ttu-id="23413-259">权限</span><span class="sxs-lookup"><span data-stu-id="23413-259">Permission</span></span></th>
<th><span data-ttu-id="23413-260">适用于</span><span class="sxs-lookup"><span data-stu-id="23413-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23413-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="23413-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="23413-262">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="23413-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="23413-263">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-265">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-265">List contents</span></span></p>
<p><span data-ttu-id="23413-266">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-266">Read all properties</span></span></p>
<p><span data-ttu-id="23413-267">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-268">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-270">列出内容</span><span class="sxs-lookup"><span data-stu-id="23413-270">List contents</span></span></p>
<p><span data-ttu-id="23413-271">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="23413-271">Read all properties</span></span></p>
<p><span data-ttu-id="23413-272">读取权限</span><span class="sxs-lookup"><span data-stu-id="23413-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="23413-273">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="23413-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23413-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="23413-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="23413-275">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-276">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-277">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-278">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="23413-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="23413-279">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="23413-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="23413-280">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="23413-280">Read General-Information</span></span></p>
<p><span data-ttu-id="23413-281">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="23413-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="23413-282">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="23413-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23413-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="23413-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="23413-284">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="23413-285">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="23413-286">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="23413-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="23413-287">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="23413-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="23413-288">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="23413-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

