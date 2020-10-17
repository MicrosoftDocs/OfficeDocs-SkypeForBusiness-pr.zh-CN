---
title: Lync Server 2013： Lync Server 2013 中的架构更改
description: Lync Server 2013： Lync Server 2013 中的架构更改。
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
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557148"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="f173a-103">Lync Server 2013 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="f173a-103">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f173a-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f173a-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f173a-105">在部署和操作 Lync Server 2013 之前，必须通过扩展架构来准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="f173a-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="f173a-106">架构扩展添加了 Lync Server 2013 所需的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f173a-106">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="f173a-107">Lync Server 2013 需要几个新的类和属性，并修改一些现有的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f173a-107">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="f173a-108">此外，Lync Server 2013 的很多配置信息存储在中央管理存储中，而不是在 AD DS 中，就像在以前的版本中一样。</span><span class="sxs-lookup"><span data-stu-id="f173a-108">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="f173a-109">以下信息仍存储在 Lync Server 2013 中的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="f173a-109">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="f173a-110">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="f173a-110">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="f173a-111">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="f173a-111">User object extensions</span></span>
    
      - <span data-ttu-id="f173a-112">Office 通信服务器2007和 Office 通信服务器 2007 R2 类的扩展，以保持与受支持的早期版本的向后兼容</span><span class="sxs-lookup"><span data-stu-id="f173a-112">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="f173a-113">存储在 Lync Server 扩展架构和现有架构类中的**数据** () ：</span><span class="sxs-lookup"><span data-stu-id="f173a-113">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="f173a-114">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="f173a-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="f173a-115">应用程序（如响应组和会议助理）的联系人对象</span><span class="sxs-lookup"><span data-stu-id="f173a-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="f173a-116">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="f173a-116">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="f173a-117">Kerberos 身份验证帐户（可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="f173a-117">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="f173a-118">本主题介绍 Lync Server 2013 所需的 Active Directory 架构更改。</span><span class="sxs-lookup"><span data-stu-id="f173a-118">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="f173a-119">它不会描述由早期版本的 Office 通信服务器引入的架构更改。</span><span class="sxs-lookup"><span data-stu-id="f173a-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="f173a-120">有关类及其说明的列表，请参阅 [Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="f173a-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="f173a-121">有关属性及其说明的列表，请参阅 [Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="f173a-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="f173a-122">有关它们可能包含的属性的类的列表，请参阅 [在 Lync Server 2013 中按类列出的架构属性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="f173a-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="f173a-123">MsRTCSIP 前缀标识特定于 Lync Server 的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f173a-123">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="f173a-124">新增 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="f173a-124">New Active Directory Attributes</span></span>

<span data-ttu-id="f173a-125">下表介绍了由 Lync Server 2013 添加的 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="f173a-125">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="f173a-126">由 Lync Server 2013 添加的属性</span><span class="sxs-lookup"><span data-stu-id="f173a-126">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f173a-127">属性</span><span class="sxs-lookup"><span data-stu-id="f173a-127">Attribute</span></span></th>
<th><span data-ttu-id="f173a-128">说明</span><span class="sxs-lookup"><span data-stu-id="f173a-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f173a-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f173a-129">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="f173a-130">此多值属性可保存应用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="f173a-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="f173a-131">保留策略会在保留持续时间内保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="f173a-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="f173a-132">此属性与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="f173a-132">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f173a-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f173a-133">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="f173a-p105">这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="f173a-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f173a-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="f173a-136">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="f173a-137">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="f173a-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="f173a-138">修改的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="f173a-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="f173a-139">下表介绍了由 Lync Server 2013 修改的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="f173a-139">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="f173a-140">由 Lync Server 2013 修改的类</span><span class="sxs-lookup"><span data-stu-id="f173a-140">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f173a-141">Class</span><span class="sxs-lookup"><span data-stu-id="f173a-141">Class</span></span></th>
<th><span data-ttu-id="f173a-142">更改</span><span class="sxs-lookup"><span data-stu-id="f173a-142">Change</span></span></th>
<th><span data-ttu-id="f173a-143">类或属性</span><span class="sxs-lookup"><span data-stu-id="f173a-143">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f173a-144">用户</span><span class="sxs-lookup"><span data-stu-id="f173a-144">User</span></span></p></td>
<td><p><span data-ttu-id="f173a-145">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-145">add: mayContain</span></span></p>
<p><span data-ttu-id="f173a-146">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-146">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="f173a-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f173a-147">ProxyAddresses</span></span></p>
<p><span data-ttu-id="f173a-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f173a-148">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f173a-149">Contact</span><span class="sxs-lookup"><span data-stu-id="f173a-149">Contact</span></span></p></td>
<td><p><span data-ttu-id="f173a-150">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-150">add: mayContain</span></span></p>
<p><span data-ttu-id="f173a-151">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-151">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="f173a-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f173a-152">ProxyAddresses</span></span></p>
<p><span data-ttu-id="f173a-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f173a-153">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f173a-154">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="f173a-154">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="f173a-155">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-155">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="f173a-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f173a-156">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f173a-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="f173a-157">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="f173a-158">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f173a-158">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="f173a-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="f173a-159">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

