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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="43d4a-102">Lync Server 2013 中的 CsOUPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43d4a-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="43d4a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="43d4a-104">若要委派 Lync Server 2013 管理，可以将权限添加到指定的组织单位（Ou），以便由林准备创建的 RTC 通用组的成员无需成为 Domain Admins 组的成员即可访问 Ou。</span><span class="sxs-lookup"><span data-stu-id="43d4a-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="43d4a-105">**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="43d4a-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="43d4a-106">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="43d4a-107">在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="43d4a-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="43d4a-108">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d4a-109">Group</span><span class="sxs-lookup"><span data-stu-id="43d4a-109">Group</span></span></th>
<th><span data-ttu-id="43d4a-110">权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-110">Permission</span></span></th>
<th><span data-ttu-id="43d4a-111">适用于</span><span class="sxs-lookup"><span data-stu-id="43d4a-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="43d4a-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="43d4a-113">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="43d4a-114">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-116">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-116">List contents</span></span></p>
<p><span data-ttu-id="43d4a-117">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-117">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-119">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-121">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-121">List contents</span></span></p>
<p><span data-ttu-id="43d4a-122">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-122">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-123">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-124">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-126">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-127">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-128">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-129">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-130">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-130">Read General-Information</span></span></p>
<p><span data-ttu-id="43d4a-131">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="43d4a-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-132">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-134">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-135">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="43d4a-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="43d4a-136">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-137">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-138">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43d4a-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="43d4a-139">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="43d4a-140">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="43d4a-141">在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="43d4a-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="43d4a-142">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d4a-143">Group</span><span class="sxs-lookup"><span data-stu-id="43d4a-143">Group</span></span></th>
<th><span data-ttu-id="43d4a-144">权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-144">Permission</span></span></th>
<th><span data-ttu-id="43d4a-145">适用于</span><span class="sxs-lookup"><span data-stu-id="43d4a-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="43d4a-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="43d4a-147">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="43d4a-148">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-150">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-150">List contents</span></span></p>
<p><span data-ttu-id="43d4a-151">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-151">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-152">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-153">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-155">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-155">List contents</span></span></p>
<p><span data-ttu-id="43d4a-156">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-156">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-157">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-158">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-160">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-161">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="43d4a-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="43d4a-162">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-164">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-165">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="43d4a-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="43d4a-166">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="43d4a-167">为联系人或 AppContact 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="43d4a-168">在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="43d4a-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="43d4a-169">为联系人对象或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d4a-170">Group</span><span class="sxs-lookup"><span data-stu-id="43d4a-170">Group</span></span></th>
<th><span data-ttu-id="43d4a-171">权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-171">Permission</span></span></th>
<th><span data-ttu-id="43d4a-172">适用于</span><span class="sxs-lookup"><span data-stu-id="43d4a-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="43d4a-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="43d4a-174">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="43d4a-175">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-177">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-177">List contents</span></span></p>
<p><span data-ttu-id="43d4a-178">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-178">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-179">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-180">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-182">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-182">List contents</span></span></p>
<p><span data-ttu-id="43d4a-183">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-183">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-184">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-185">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-187">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-188">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-189">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-190">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-191">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-191">Read General-Information</span></span></p>
<p><span data-ttu-id="43d4a-192">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="43d4a-193">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="43d4a-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-194">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-196">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-197">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="43d4a-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="43d4a-198">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="43d4a-198">Write displayName</span></span></p>
<p><span data-ttu-id="43d4a-199">写入 description</span><span class="sxs-lookup"><span data-stu-id="43d4a-199">Write description</span></span></p>
<p><span data-ttu-id="43d4a-200">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="43d4a-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="43d4a-201">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="43d4a-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="43d4a-202">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-203">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-204">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43d4a-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="43d4a-205">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="43d4a-206">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="43d4a-207">在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="43d4a-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="43d4a-208">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d4a-209">Group</span><span class="sxs-lookup"><span data-stu-id="43d4a-209">Group</span></span></th>
<th><span data-ttu-id="43d4a-210">权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-210">Permission</span></span></th>
<th><span data-ttu-id="43d4a-211">适用于</span><span class="sxs-lookup"><span data-stu-id="43d4a-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="43d4a-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="43d4a-213">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="43d4a-214">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-216">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-216">List contents</span></span></p>
<p><span data-ttu-id="43d4a-217">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-217">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-218">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-219">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-221">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-221">List contents</span></span></p>
<p><span data-ttu-id="43d4a-222">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-222">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-223">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-224">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-226">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-227">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-228">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-229">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-230">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="43d4a-231">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-231">Read General-Information</span></span></p>
<p><span data-ttu-id="43d4a-232">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="43d4a-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-233">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-235">创建子级</span><span class="sxs-lookup"><span data-stu-id="43d4a-235">Create child</span></span></p>
<p><span data-ttu-id="43d4a-236">删除子级</span><span class="sxs-lookup"><span data-stu-id="43d4a-236">Delete child</span></span></p>
<p><span data-ttu-id="43d4a-237">删除树</span><span class="sxs-lookup"><span data-stu-id="43d4a-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="43d4a-238">Contact</span><span class="sxs-lookup"><span data-stu-id="43d4a-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-240">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="43d4a-240">Write displayName</span></span></p>
<p><span data-ttu-id="43d4a-241">写入 description</span><span class="sxs-lookup"><span data-stu-id="43d4a-241">Write description</span></span></p>
<p><span data-ttu-id="43d4a-242">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="43d4a-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="43d4a-243">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-245">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-246">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="43d4a-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="43d4a-247">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="43d4a-247">Write displayName</span></span></p>
<p><span data-ttu-id="43d4a-248">写入 description</span><span class="sxs-lookup"><span data-stu-id="43d4a-248">Write description</span></span></p>
<p><span data-ttu-id="43d4a-249">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="43d4a-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="43d4a-250">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="43d4a-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="43d4a-251">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-252">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-253">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43d4a-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="43d4a-254">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="43d4a-255">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="43d4a-256">在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="43d4a-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="43d4a-257">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d4a-258">Group</span><span class="sxs-lookup"><span data-stu-id="43d4a-258">Group</span></span></th>
<th><span data-ttu-id="43d4a-259">权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-259">Permission</span></span></th>
<th><span data-ttu-id="43d4a-260">适用于</span><span class="sxs-lookup"><span data-stu-id="43d4a-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="43d4a-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="43d4a-262">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="43d4a-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="43d4a-263">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-265">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-265">List contents</span></span></p>
<p><span data-ttu-id="43d4a-266">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-266">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-267">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-268">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-270">列出内容</span><span class="sxs-lookup"><span data-stu-id="43d4a-270">List contents</span></span></p>
<p><span data-ttu-id="43d4a-271">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="43d4a-271">Read all properties</span></span></p>
<p><span data-ttu-id="43d4a-272">读取权限</span><span class="sxs-lookup"><span data-stu-id="43d4a-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-273">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d4a-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="43d4a-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="43d4a-275">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-276">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-277">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-278">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="43d4a-279">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="43d4a-280">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="43d4a-280">Read General-Information</span></span></p>
<p><span data-ttu-id="43d4a-281">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="43d4a-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="43d4a-282">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d4a-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="43d4a-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="43d4a-284">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-285">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-286">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="43d4a-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="43d4a-287">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="43d4a-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="43d4a-288">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="43d4a-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

