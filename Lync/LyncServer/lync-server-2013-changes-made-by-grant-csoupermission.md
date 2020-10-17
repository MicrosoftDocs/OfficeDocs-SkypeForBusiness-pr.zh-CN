---
title: Lync Server 2013： Grant-CsOUPermission 所做的更改
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529429"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="08d97-102">Lync Server 2013 中 Grant-CsOUPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="08d97-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08d97-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="08d97-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="08d97-104">若要委派 Lync Server 2013 管理，可以将权限添加到指定的组织单位 (Ou 中) 以便由林准备创建的 RTC 通用组的成员可以访问 Ou，而无需成为 Domain Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="08d97-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="08d97-105">**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="08d97-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="08d97-106">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="08d97-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="08d97-107">在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="08d97-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="08d97-108">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="08d97-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08d97-109">Group</span><span class="sxs-lookup"><span data-stu-id="08d97-109">Group</span></span></th>
<th><span data-ttu-id="08d97-110">权限</span><span class="sxs-lookup"><span data-stu-id="08d97-110">Permission</span></span></th>
<th><span data-ttu-id="08d97-111">适用于</span><span class="sxs-lookup"><span data-stu-id="08d97-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d97-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="08d97-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="08d97-113">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="08d97-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="08d97-114">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-116">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-116">List contents</span></span></p>
<p><span data-ttu-id="08d97-117">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-117">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-119">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-121">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-121">List contents</span></span></p>
<p><span data-ttu-id="08d97-122">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-122">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-123">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-124">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-126">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-127">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-128">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-129">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-130">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-130">Read General-Information</span></span></p>
<p><span data-ttu-id="08d97-131">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="08d97-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="08d97-132">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="08d97-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-134">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-135">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="08d97-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="08d97-136">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-137">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-138">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="08d97-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="08d97-139">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="08d97-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="08d97-140">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="08d97-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="08d97-141">在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="08d97-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="08d97-142">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="08d97-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08d97-143">Group</span><span class="sxs-lookup"><span data-stu-id="08d97-143">Group</span></span></th>
<th><span data-ttu-id="08d97-144">权限</span><span class="sxs-lookup"><span data-stu-id="08d97-144">Permission</span></span></th>
<th><span data-ttu-id="08d97-145">适用于</span><span class="sxs-lookup"><span data-stu-id="08d97-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d97-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="08d97-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="08d97-147">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="08d97-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="08d97-148">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-150">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-150">List contents</span></span></p>
<p><span data-ttu-id="08d97-151">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-151">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-152">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-153">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-155">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-155">List contents</span></span></p>
<p><span data-ttu-id="08d97-156">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-156">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-157">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-158">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-160">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-161">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="08d97-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="08d97-162">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="08d97-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-164">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-165">读取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="08d97-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="08d97-166">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="08d97-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="08d97-167">为联系人或 AppContact 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="08d97-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="08d97-168">在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="08d97-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="08d97-169">为联系人对象或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="08d97-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08d97-170">Group</span><span class="sxs-lookup"><span data-stu-id="08d97-170">Group</span></span></th>
<th><span data-ttu-id="08d97-171">权限</span><span class="sxs-lookup"><span data-stu-id="08d97-171">Permission</span></span></th>
<th><span data-ttu-id="08d97-172">适用于</span><span class="sxs-lookup"><span data-stu-id="08d97-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d97-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="08d97-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="08d97-174">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="08d97-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="08d97-175">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-177">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-177">List contents</span></span></p>
<p><span data-ttu-id="08d97-178">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-178">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-179">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-180">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-182">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-182">List contents</span></span></p>
<p><span data-ttu-id="08d97-183">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-183">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-184">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-185">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-187">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-188">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-189">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-190">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-191">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-191">Read General-Information</span></span></p>
<p><span data-ttu-id="08d97-192">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="08d97-193">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="08d97-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="08d97-194">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="08d97-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-196">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-197">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="08d97-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="08d97-198">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="08d97-198">Write displayName</span></span></p>
<p><span data-ttu-id="08d97-199">写入 description</span><span class="sxs-lookup"><span data-stu-id="08d97-199">Write description</span></span></p>
<p><span data-ttu-id="08d97-200">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="08d97-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="08d97-201">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="08d97-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="08d97-202">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-203">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-204">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="08d97-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="08d97-205">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="08d97-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="08d97-206">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="08d97-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="08d97-207">在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="08d97-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="08d97-208">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="08d97-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08d97-209">Group</span><span class="sxs-lookup"><span data-stu-id="08d97-209">Group</span></span></th>
<th><span data-ttu-id="08d97-210">权限</span><span class="sxs-lookup"><span data-stu-id="08d97-210">Permission</span></span></th>
<th><span data-ttu-id="08d97-211">适用于</span><span class="sxs-lookup"><span data-stu-id="08d97-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d97-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="08d97-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="08d97-213">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="08d97-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="08d97-214">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-216">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-216">List contents</span></span></p>
<p><span data-ttu-id="08d97-217">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-217">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-218">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-219">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-221">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-221">List contents</span></span></p>
<p><span data-ttu-id="08d97-222">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-222">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-223">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-224">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-226">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-227">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-228">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-229">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-230">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="08d97-231">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-231">Read General-Information</span></span></p>
<p><span data-ttu-id="08d97-232">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="08d97-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="08d97-233">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="08d97-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-235">创建子级</span><span class="sxs-lookup"><span data-stu-id="08d97-235">Create child</span></span></p>
<p><span data-ttu-id="08d97-236">删除子级</span><span class="sxs-lookup"><span data-stu-id="08d97-236">Delete child</span></span></p>
<p><span data-ttu-id="08d97-237">删除树</span><span class="sxs-lookup"><span data-stu-id="08d97-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="08d97-238">Contact</span><span class="sxs-lookup"><span data-stu-id="08d97-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-240">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="08d97-240">Write displayName</span></span></p>
<p><span data-ttu-id="08d97-241">写入 description</span><span class="sxs-lookup"><span data-stu-id="08d97-241">Write description</span></span></p>
<p><span data-ttu-id="08d97-242">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="08d97-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="08d97-243">后代用户对象</span><span class="sxs-lookup"><span data-stu-id="08d97-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-245">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-246">写入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="08d97-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="08d97-247">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="08d97-247">Write displayName</span></span></p>
<p><span data-ttu-id="08d97-248">写入 description</span><span class="sxs-lookup"><span data-stu-id="08d97-248">Write description</span></span></p>
<p><span data-ttu-id="08d97-249">写入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="08d97-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="08d97-250">写入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="08d97-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="08d97-251">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-252">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-253">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="08d97-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="08d97-254">后代联系人对象</span><span class="sxs-lookup"><span data-stu-id="08d97-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="08d97-255">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="08d97-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="08d97-256">在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。</span><span class="sxs-lookup"><span data-stu-id="08d97-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="08d97-257">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="08d97-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08d97-258">Group</span><span class="sxs-lookup"><span data-stu-id="08d97-258">Group</span></span></th>
<th><span data-ttu-id="08d97-259">权限</span><span class="sxs-lookup"><span data-stu-id="08d97-259">Permission</span></span></th>
<th><span data-ttu-id="08d97-260">适用于</span><span class="sxs-lookup"><span data-stu-id="08d97-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d97-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="08d97-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="08d97-262">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="08d97-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="08d97-263">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-265">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-265">List contents</span></span></p>
<p><span data-ttu-id="08d97-266">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-266">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-267">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-268">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-270">列出内容</span><span class="sxs-lookup"><span data-stu-id="08d97-270">List contents</span></span></p>
<p><span data-ttu-id="08d97-271">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="08d97-271">Read all properties</span></span></p>
<p><span data-ttu-id="08d97-272">读取权限</span><span class="sxs-lookup"><span data-stu-id="08d97-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="08d97-273">仅限此对象</span><span class="sxs-lookup"><span data-stu-id="08d97-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d97-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="08d97-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="08d97-275">读取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-276">读取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-277">读取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-278">读取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="08d97-279">读取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="08d97-280">读取 General-Information</span><span class="sxs-lookup"><span data-stu-id="08d97-280">Read General-Information</span></span></p>
<p><span data-ttu-id="08d97-281">读取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="08d97-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="08d97-282">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="08d97-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d97-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="08d97-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="08d97-284">写入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="08d97-285">写入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="08d97-286">写入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="08d97-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="08d97-287">写入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="08d97-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="08d97-288">后代 InetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="08d97-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

