---
title: Lync Server 2013： Lync Server 2013 中的架构更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a3fd5f18785a649803cc6f9a0a56d7b98a2ee6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="fe4f0-102">Lync Server 2013 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="fe4f0-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe4f0-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fe4f0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fe4f0-104">在部署和操作 Lync Server 2013 之前，必须通过扩展架构来准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="fe4f0-105">架构扩展添加 Lync Server 2013 所需的类和属性。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="fe4f0-106">Lync Server 2013 需要多个新的类和属性，并修改一些现有的类和属性。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="fe4f0-107">此外，Lync Server 2013 的许多配置信息存储在中央管理存储中，而不是在 AD DS 中，就像在以前的版本中一样。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="fe4f0-108">以下信息仍存储在 Lync Server 2013 中的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="fe4f0-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="fe4f0-109">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="fe4f0-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="fe4f0-110">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="fe4f0-110">User object extensions</span></span>
    
      - <span data-ttu-id="fe4f0-111">Office 通信服务器2007和 Office 通信服务器 2007 R2 类的扩展，以保持受支持的早期版本的向后兼容性</span><span class="sxs-lookup"><span data-stu-id="fe4f0-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="fe4f0-112">**数据**（存储在 Lync Server 扩展架构和现有架构类中）：</span><span class="sxs-lookup"><span data-stu-id="fe4f0-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="fe4f0-113">用户 SIP 统一资源标识符（URI）和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="fe4f0-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="fe4f0-114">响应组和会议助理等应用程序的联系人对象</span><span class="sxs-lookup"><span data-stu-id="fe4f0-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="fe4f0-115">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="fe4f0-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="fe4f0-116">Kerberos 身份验证帐户（可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="fe4f0-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="fe4f0-117">本主题介绍 Lync Server 2013 所需的 Active Directory 架构更改。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="fe4f0-118">它不会描述以前版本的 Office 通信服务器引入的架构更改。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="fe4f0-119">有关类及其说明的列表，请参阅[Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="fe4f0-120">有关属性及其说明的列表，请参阅[Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="fe4f0-121">有关它们可能包含的属性的类的列表，请参阅[Lync Server 2013 中按类列出的架构属性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="fe4f0-122">MsRTCSIP 前缀标识特定于 Lync Server 的类和属性。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="fe4f0-123">新的 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="fe4f0-123">New Active Directory Attributes</span></span>

<span data-ttu-id="fe4f0-124">下表描述了 Lync Server 2013 添加的 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="fe4f0-125">Lync Server 2013 添加的属性</span><span class="sxs-lookup"><span data-stu-id="fe4f0-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe4f0-126">属性</span><span class="sxs-lookup"><span data-stu-id="fe4f0-126">Attribute</span></span></th>
<th><span data-ttu-id="fe4f0-127">描述</span><span class="sxs-lookup"><span data-stu-id="fe4f0-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe4f0-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fe4f0-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-129">此多值属性包含适用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="fe4f0-130">保留策略在保留期间保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="fe4f0-131">此属性是与 Exchange 2013 共享的。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe4f0-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe4f0-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-133">这是 SIP 路由组 ID。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="fe4f0-134">同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe4f0-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fe4f0-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-136">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="fe4f0-137">已修改的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="fe4f0-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="fe4f0-138">下表介绍了由 Lync Server 2013 修改的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="fe4f0-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="fe4f0-139">Lync Server 2013 修改的类</span><span class="sxs-lookup"><span data-stu-id="fe4f0-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe4f0-140">种类</span><span class="sxs-lookup"><span data-stu-id="fe4f0-140">Class</span></span></th>
<th><span data-ttu-id="fe4f0-141">更改</span><span class="sxs-lookup"><span data-stu-id="fe4f0-141">Change</span></span></th>
<th><span data-ttu-id="fe4f0-142">类或属性</span><span class="sxs-lookup"><span data-stu-id="fe4f0-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe4f0-143">用户</span><span class="sxs-lookup"><span data-stu-id="fe4f0-143">User</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-144">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-144">add: mayContain</span></span></p>
<p><span data-ttu-id="fe4f0-145">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fe4f0-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="fe4f0-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe4f0-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe4f0-148">联系人</span><span class="sxs-lookup"><span data-stu-id="fe4f0-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-149">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-149">add: mayContain</span></span></p>
<p><span data-ttu-id="fe4f0-150">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fe4f0-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="fe4f0-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe4f0-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe4f0-153">邮件-收件人</span><span class="sxs-lookup"><span data-stu-id="fe4f0-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-154">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fe4f0-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe4f0-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="fe4f0-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-157">add： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe4f0-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="fe4f0-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fe4f0-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

