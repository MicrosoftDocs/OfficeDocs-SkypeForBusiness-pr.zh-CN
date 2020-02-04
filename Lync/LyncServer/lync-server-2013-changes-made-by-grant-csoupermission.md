---
title: Lync Server 2013：通过授予 CsOUPermission 进行的更改
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="3f069-102">Lync Server 2013 中的 "授权-CsOUPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="3f069-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f069-103">_**主题上次修改时间：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="3f069-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="3f069-104">若要委派 Lync Server 2013 管理，可以向指定的组织单位（Ou）添加权限，以便林准备创建的 RTC 通用组的成员无需成为域管理员组的成员即可访问 Ou。</span><span class="sxs-lookup"><span data-stu-id="3f069-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="3f069-105">**CsOuPermission** cmdlet 按下表中指定的方式向指定 OU 中的对象授予权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="3f069-106">为用户对象授予权限</span><span class="sxs-lookup"><span data-stu-id="3f069-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="3f069-107">在 OU 上运行用户对象的**CsOuPermission** cmdlet 时，将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="3f069-108">为用户对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f069-109">团队</span><span class="sxs-lookup"><span data-stu-id="3f069-109">Group</span></span></th>
<th><span data-ttu-id="3f069-110">权限</span><span class="sxs-lookup"><span data-stu-id="3f069-110">Permission</span></span></th>
<th><span data-ttu-id="3f069-111">适用于</span><span class="sxs-lookup"><span data-stu-id="3f069-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f069-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3f069-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3f069-113">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="3f069-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3f069-114">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-116">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-116">List contents</span></span></p>
<p><span data-ttu-id="3f069-117">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-117">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-119">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-121">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-121">List contents</span></span></p>
<p><span data-ttu-id="3f069-122">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-122">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-123">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-124">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-126">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-127">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-128">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-129">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-130">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="3f069-130">Read General-Information</span></span></p>
<p><span data-ttu-id="3f069-131">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="3f069-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3f069-132">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="3f069-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-134">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-135">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3f069-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3f069-136">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-137">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-138">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3f069-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3f069-139">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="3f069-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="3f069-140">为计算机对象授予权限</span><span class="sxs-lookup"><span data-stu-id="3f069-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="3f069-141">在 OU 上运行计算机对象的**CsOuPermission** cmdlet 时，将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="3f069-142">为计算机对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f069-143">团队</span><span class="sxs-lookup"><span data-stu-id="3f069-143">Group</span></span></th>
<th><span data-ttu-id="3f069-144">权限</span><span class="sxs-lookup"><span data-stu-id="3f069-144">Permission</span></span></th>
<th><span data-ttu-id="3f069-145">适用于</span><span class="sxs-lookup"><span data-stu-id="3f069-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f069-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3f069-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3f069-147">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="3f069-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3f069-148">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-150">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-150">List contents</span></span></p>
<p><span data-ttu-id="3f069-151">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-151">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-152">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-153">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-155">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-155">List contents</span></span></p>
<p><span data-ttu-id="3f069-156">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-156">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-157">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-158">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-160">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-161">读取已验证的 DNS 主机名</span><span class="sxs-lookup"><span data-stu-id="3f069-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="3f069-162">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="3f069-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-164">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-165">读取已验证的 DNS 主机名</span><span class="sxs-lookup"><span data-stu-id="3f069-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="3f069-166">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="3f069-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="3f069-167">授予联系人或 AppContact 对象的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="3f069-168">当你为某个 OU 上的 Contact 对象或 AppContact 对象运行**CsOuPermission** cmdlet 时，将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="3f069-169">为联系人或 AppContact 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f069-170">团队</span><span class="sxs-lookup"><span data-stu-id="3f069-170">Group</span></span></th>
<th><span data-ttu-id="3f069-171">权限</span><span class="sxs-lookup"><span data-stu-id="3f069-171">Permission</span></span></th>
<th><span data-ttu-id="3f069-172">适用于</span><span class="sxs-lookup"><span data-stu-id="3f069-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f069-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3f069-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3f069-174">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="3f069-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3f069-175">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-177">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-177">List contents</span></span></p>
<p><span data-ttu-id="3f069-178">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-178">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-179">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-180">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-182">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-182">List contents</span></span></p>
<p><span data-ttu-id="3f069-183">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-183">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-184">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-185">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-187">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-188">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-189">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-190">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-191">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="3f069-191">Read General-Information</span></span></p>
<p><span data-ttu-id="3f069-192">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="3f069-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3f069-193">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="3f069-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3f069-194">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="3f069-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-196">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-197">写 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="3f069-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="3f069-198">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="3f069-198">Write displayName</span></span></p>
<p><span data-ttu-id="3f069-199">写入说明</span><span class="sxs-lookup"><span data-stu-id="3f069-199">Write description</span></span></p>
<p><span data-ttu-id="3f069-200">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3f069-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="3f069-201">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3f069-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3f069-202">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-203">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-204">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3f069-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3f069-205">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="3f069-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="3f069-206">为设备对象授予权限</span><span class="sxs-lookup"><span data-stu-id="3f069-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="3f069-207">在 OU 上运行设备对象的**CsOuPermission** cmdlet 时，将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="3f069-208">为设备对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f069-209">团队</span><span class="sxs-lookup"><span data-stu-id="3f069-209">Group</span></span></th>
<th><span data-ttu-id="3f069-210">权限</span><span class="sxs-lookup"><span data-stu-id="3f069-210">Permission</span></span></th>
<th><span data-ttu-id="3f069-211">适用于</span><span class="sxs-lookup"><span data-stu-id="3f069-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f069-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3f069-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3f069-213">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="3f069-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3f069-214">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-216">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-216">List contents</span></span></p>
<p><span data-ttu-id="3f069-217">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-217">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-218">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-219">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-221">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-221">List contents</span></span></p>
<p><span data-ttu-id="3f069-222">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-222">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-223">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-224">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-226">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-227">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-228">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-229">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-230">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="3f069-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3f069-231">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="3f069-231">Read General-Information</span></span></p>
<p><span data-ttu-id="3f069-232">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="3f069-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3f069-233">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="3f069-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-235">创建子元素</span><span class="sxs-lookup"><span data-stu-id="3f069-235">Create child</span></span></p>
<p><span data-ttu-id="3f069-236">删除子元素</span><span class="sxs-lookup"><span data-stu-id="3f069-236">Delete child</span></span></p>
<p><span data-ttu-id="3f069-237">删除树</span><span class="sxs-lookup"><span data-stu-id="3f069-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="3f069-238">联系人</span><span class="sxs-lookup"><span data-stu-id="3f069-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-240">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="3f069-240">Write displayName</span></span></p>
<p><span data-ttu-id="3f069-241">写入说明</span><span class="sxs-lookup"><span data-stu-id="3f069-241">Write description</span></span></p>
<p><span data-ttu-id="3f069-242">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3f069-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="3f069-243">子代用户对象</span><span class="sxs-lookup"><span data-stu-id="3f069-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-245">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-246">写 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="3f069-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="3f069-247">写入 displayName</span><span class="sxs-lookup"><span data-stu-id="3f069-247">Write displayName</span></span></p>
<p><span data-ttu-id="3f069-248">写入说明</span><span class="sxs-lookup"><span data-stu-id="3f069-248">Write description</span></span></p>
<p><span data-ttu-id="3f069-249">写 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3f069-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="3f069-250">写 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3f069-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3f069-251">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-252">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-253">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3f069-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3f069-254">子代联系人对象</span><span class="sxs-lookup"><span data-stu-id="3f069-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="3f069-255">为 InetOrgPerson 对象授予权限</span><span class="sxs-lookup"><span data-stu-id="3f069-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="3f069-256">当你针对 OU 上的 InetOrgPerson 对象运行**CsOuPermission** cmdlet 时，将向组授予下表中所示的权限。</span><span class="sxs-lookup"><span data-stu-id="3f069-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="3f069-257">为 InetOrgPerson 对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="3f069-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f069-258">团队</span><span class="sxs-lookup"><span data-stu-id="3f069-258">Group</span></span></th>
<th><span data-ttu-id="3f069-259">权限</span><span class="sxs-lookup"><span data-stu-id="3f069-259">Permission</span></span></th>
<th><span data-ttu-id="3f069-260">适用于</span><span class="sxs-lookup"><span data-stu-id="3f069-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f069-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3f069-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3f069-262">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="3f069-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3f069-263">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-265">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-265">List contents</span></span></p>
<p><span data-ttu-id="3f069-266">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-266">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-267">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-268">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-270">列表内容</span><span class="sxs-lookup"><span data-stu-id="3f069-270">List contents</span></span></p>
<p><span data-ttu-id="3f069-271">读取所有属性</span><span class="sxs-lookup"><span data-stu-id="3f069-271">Read all properties</span></span></p>
<p><span data-ttu-id="3f069-272">读取权限</span><span class="sxs-lookup"><span data-stu-id="3f069-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3f069-273">仅此对象</span><span class="sxs-lookup"><span data-stu-id="3f069-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f069-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3f069-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3f069-275">阅读 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-276">阅读 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-277">阅读 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-278">阅读个人信息</span><span class="sxs-lookup"><span data-stu-id="3f069-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3f069-279">阅读公共信息</span><span class="sxs-lookup"><span data-stu-id="3f069-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="3f069-280">阅读常规信息</span><span class="sxs-lookup"><span data-stu-id="3f069-280">Read General-Information</span></span></p>
<p><span data-ttu-id="3f069-281">阅读用户-帐户限制</span><span class="sxs-lookup"><span data-stu-id="3f069-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3f069-282">子代 inetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="3f069-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f069-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3f069-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3f069-284">写 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3f069-285">写 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3f069-286">写 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3f069-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3f069-287">写 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3f069-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3f069-288">子代 inetOrgPerson 对象</span><span class="sxs-lookup"><span data-stu-id="3f069-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

