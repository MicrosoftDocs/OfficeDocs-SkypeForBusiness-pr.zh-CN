---
title: Lync Server 2013：架构属性和说明
description: Lync Server 2013：架构属性和说明。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557188"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="7dc67-103">Lync Server 2013 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="7dc67-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dc67-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7dc67-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7dc67-105">本节介绍 Lync Server 2013 使用的所有架构属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="7dc67-106">对于与属性相关联的类，请参阅 [在 Lync Server 2013 中按类架构属性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="7dc67-107">有关 Lync Server 2013 中新增的类和属性的列表，请参阅 [Lync server 2013 中的架构更改](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="7dc67-p102">将链接为一对的属性指定为正向链接或反向链接。指向另一个对象的属性为正向链接；向回指向第一个对象的其他对象的属性为反向链接。正向链接可更新，而反向链接为只读。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="7dc67-p103">有些属性具有位掩码值。对于这些属性，每项设置均由位表示，所显示的十进制值表示各个位的位置。位的位置从第 0 位开始。例如，1（二进制）设置了第 0 位，10000（二进制）设置了第 4 位。每位表示一个属性。下面给出了一些示例：</span><span class="sxs-lookup"><span data-stu-id="7dc67-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="7dc67-117">10000（二进制）的十进制值为 16（即设置了第 4 位）。</span><span class="sxs-lookup"><span data-stu-id="7dc67-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="7dc67-118">100000000（二进制）的十进制值为 256（即设置了第 8 位）。</span><span class="sxs-lookup"><span data-stu-id="7dc67-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="7dc67-119">1100（二进制）的十进制值为 12（即设置了第 2 位和第 3 位；这两位表示的属性已启用）。</span><span class="sxs-lookup"><span data-stu-id="7dc67-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="7dc67-120">1111000001（二进制）的十进制值为 961（即设置了第 0、6、7、8 和 9 位；这些位中每位表示的属性已启用）。</span><span class="sxs-lookup"><span data-stu-id="7dc67-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="7dc67-121">Lync Server 2013 的架构属性</span><span class="sxs-lookup"><span data-stu-id="7dc67-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dc67-122">属性</span><span class="sxs-lookup"><span data-stu-id="7dc67-122">Attribute</span></span></th>
<th><span data-ttu-id="7dc67-123">说明</span><span class="sxs-lookup"><span data-stu-id="7dc67-123">Description</span></span></th>
<th><span data-ttu-id="7dc67-124">Comments</span><span class="sxs-lookup"><span data-stu-id="7dc67-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="7dc67-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="7dc67-126">Active Directory 域服务中当前与 <strong>msRTCSIP</strong> 和 <strong>msRTCSIP</strong> 类关联的现有属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="7dc67-127">此属性指定池或监视服务器 (FQDN) 的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7dc67-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="7dc67-128">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-129">Microsoft Office Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-130">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p105">此属性包含一个字符串，表示另一个林中与此对象相对应的对象的可分辨名称 (DN)。此属性用于通讯组扩展和自动助理。此属性是在 Windows Server 2003 R2 的默认 Active Directory 架构中定义的。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="7dc67-134">为了省去将 AD DS 升级到 Windows Server 2003 R2 的麻烦，Active Directory 架构准备使用此属性定义扩展 Windows Server 2003 架构。</span><span class="sxs-lookup"><span data-stu-id="7dc67-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-135">Microsoft Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="7dc67-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="7dc67-137">此多值属性保存语音邮件设置。</span><span class="sxs-lookup"><span data-stu-id="7dc67-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="7dc67-138">此属性与 Exchange 统一消息 (UM) 共享。</span><span class="sxs-lookup"><span data-stu-id="7dc67-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="7dc67-139">Microsoft Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7dc67-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="7dc67-141">此多值属性可保存应用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="7dc67-142">保留策略会在保留持续时间内保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="7dc67-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="7dc67-143">此属性与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="7dc67-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-144">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="7dc67-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="7dc67-146">此属性存储用户的音频会议提供商信息。</span><span class="sxs-lookup"><span data-stu-id="7dc67-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-147">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="7dc67-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="7dc67-149">此属性指向应用程序联系人的受信任的服务项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-150">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-151">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="7dc67-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="7dc67-152">此属性包含应用程序服务器上所承载的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-153">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="7dc67-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="7dc67-155">此属性指定应用程序联系人的选项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-156">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="7dc67-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="7dc67-158">此属性包含应用程序联系人的主要语言。</span><span class="sxs-lookup"><span data-stu-id="7dc67-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-159">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="7dc67-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="7dc67-161">此多值属性包含应用程序联系人的辅助语言。</span><span class="sxs-lookup"><span data-stu-id="7dc67-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-162">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="7dc67-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p108">此属性包含属于此池的应用程序服务器的列表。此反向链接属性相应的正向链接为 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-166">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="7dc67-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="7dc67-168">此属性指向此应用程序服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="7dc67-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="7dc67-169">它属于正向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-169">This is the forward link.</span></span> <span data-ttu-id="7dc67-170">相应的反向链接为 <strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-171">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-172">msRTCSIP-ArchiveDefault（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-173">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-174">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-175">msRTCSIP-ArchiveDefaultFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p110">此属性指定林边界内用于对所有用户通信进行存档的全局默认设置。这由存档代理层强制执行。此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-179"><strong>TRUE</strong>：存档所有用户</span><span class="sxs-lookup"><span data-stu-id="7dc67-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="7dc67-180"><strong>FALSE</strong>：不存档所有用户</span><span class="sxs-lookup"><span data-stu-id="7dc67-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="7dc67-181">此属性在林边界内对内部网络中的用户通信存档方式进行全局控制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="7dc67-182"><strong>Live Communications Server 2005 行为（现已撤销）</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="7dc67-183">此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-184">0: 对消息正文进行存档 [0 位]</span><span class="sxs-lookup"><span data-stu-id="7dc67-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="7dc67-185">1: 不对消息正文进行存档 [0 位]</span><span class="sxs-lookup"><span data-stu-id="7dc67-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="7dc67-186"><strong>Office Communications Server 2007 行为</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="7dc67-187">此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-188">0: ArchiveFederationDefaultWithoutBody（已撤销）</span><span class="sxs-lookup"><span data-stu-id="7dc67-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="7dc67-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="7dc67-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="7dc67-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="7dc67-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="7dc67-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="7dc67-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="7dc67-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="7dc67-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="7dc67-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="7dc67-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="7dc67-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="7dc67-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="7dc67-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="7dc67-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="7dc67-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="7dc67-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="7dc67-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-203">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-204">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-205">msRTCSIP-ArchiveFederationDefault（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-206">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-207">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-208">msRTCSIP-ArchiveFederationDefaultFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-209">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-210">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="7dc67-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p111">此属性是一个用作位字段的整数，用于控制是否要对单个用户的通信进行存档。这种控制由存档代理层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-215">此属性的作用域特定于单个用户或联系人。</span><span class="sxs-lookup"><span data-stu-id="7dc67-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="7dc67-216">Lync Server 中的有效值 (和关联的位位置) 如下所示：</span><span class="sxs-lookup"><span data-stu-id="7dc67-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-217">0: 不存档（未设置位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-218">1: 已撤销（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-219">2: 已撤销（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-220">4: 对内部通信进行存档（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-221">8: 对联盟通信进行存档（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="7dc67-222">Live 通信服务器2005中以前的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="7dc67-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-223">0：按以下优先顺序使用由 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 定义的默认值：</span><span class="sxs-lookup"><span data-stu-id="7dc67-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-224">1: 存档</span><span class="sxs-lookup"><span data-stu-id="7dc67-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="7dc67-225">2: 不存档</span><span class="sxs-lookup"><span data-stu-id="7dc67-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="7dc67-226">3: 存档，但不包括消息正文</span><span class="sxs-lookup"><span data-stu-id="7dc67-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-227">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-228">msRTCSIP-ArchivingServerData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-229">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-230">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-231">msRTCSIP-ArchivingServerVersion（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p113">此属性定义存档服务的版本。此属性属于单调递增的整数类型，它随每次正式产品发布而递增。可能的有效值为：</span><span class="sxs-lookup"><span data-stu-id="7dc67-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-235">未定义： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="7dc67-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="7dc67-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="7dc67-237">                 具有 SP1 的 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="7dc67-238">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="7dc67-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="7dc67-239">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7dc67-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-240">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-241">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p114">此属性指定池的后端服务器的 FQDN。因为每个池只能有一个后端服务器，所以这是一个单值属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="7dc67-245">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-246">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="7dc67-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="7dc67-248">此属性包含承载会议目录的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-249">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="7dc67-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="7dc67-251">此属性包含会议目录的标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-252">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="7dc67-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="7dc67-254">此属性包含要向其移动会议目录的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-255">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-256">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="7dc67-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="7dc67-257">此布尔属性定义电话用法是否为默认用法。</span><span class="sxs-lookup"><span data-stu-id="7dc67-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="7dc67-258">如果此属性设置为 <strong>TRUE</strong>，则电话用法为默认用法，且管理员无法删除该用法。</span><span class="sxs-lookup"><span data-stu-id="7dc67-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="7dc67-259">如果此属性设置为 <strong>FALSE</strong>，则可以删除该用法。</span><span class="sxs-lookup"><span data-stu-id="7dc67-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-260">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="7dc67-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="7dc67-262">此属性标识组织外部用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="7dc67-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-263">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="7dc67-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="7dc67-265">此属性标识组织内的用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="7dc67-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-266">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-267">msRTCSIP-DefaultLocationProfileLink（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-268">此单值属性包含分配给它的位置配置文件类对象的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="7dc67-269">正向链接：<strong>链接 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="7dc67-270">相应的反向链接为 <strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-271">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-272">msRTCSIP-DefaultPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-273">此布尔属性指定策略是否为默认策略。</span><span class="sxs-lookup"><span data-stu-id="7dc67-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="7dc67-274">当此属性设置为 <strong>TRUE</strong> 时，策略为默认策略。</span><span class="sxs-lookup"><span data-stu-id="7dc67-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-275">Office 通信服务器2007中的新增项</span><span class="sxs-lookup"><span data-stu-id="7dc67-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="7dc67-276">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-277">msRTCSIP-DefaultRouteToEdgeProxy（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-278">此属性指定运行访问边缘服务的边缘服务器的 FQDN （如果可以直接访问），或指定运行访问边缘服务的服务器池的硬件负载平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="7dc67-279">如果只能通过一个或多个控制器访问运行访问边缘服务的服务器，则此属性指定 FQDN 和（可选）控制器的端口号，或者为控制器池提供服务的硬件负载平衡器的端口号。</span><span class="sxs-lookup"><span data-stu-id="7dc67-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="7dc67-280">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-281">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-282">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-283">msRTCSIP-DefaultRouteToEdgeProxyPort（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-284">此属性表示应用于连接到运行访问边缘服务的服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="7dc67-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="7dc67-285">有效值为指定要使用的端口的整数值。</span><span class="sxs-lookup"><span data-stu-id="7dc67-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="7dc67-286">默认值为 5061。</span><span class="sxs-lookup"><span data-stu-id="7dc67-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-287">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-288">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-289">msRTCSIP-DefPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-290">此属性表示默认的状态订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-291">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-292">msRTCSIP-DefRegistrationTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-293">此属性表示默认的注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-294">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-295">msRTCSIP-DefRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-296">此属性表示默认的漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-297">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="7dc67-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="7dc67-299">此属性在拆分域拓扑中使用，并且包含完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="7dc67-300">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-301">msRTCSIP-Description（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-302">此单值 UNICODE 字符串属性包含对此电话路由或规范化规则的友好描述。</span><span class="sxs-lookup"><span data-stu-id="7dc67-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-303">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-304">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="7dc67-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-306">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-307">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="7dc67-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="7dc67-308">此属性表示为注册器配置的域。</span><span class="sxs-lookup"><span data-stu-id="7dc67-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="7dc67-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-310">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-311">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-313">此属性指定运行访问边缘服务的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="7dc67-314">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-315">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-316">msRTCSIP-EnableBestEffortNotify（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p119">此属性控制服务器是否生成 Best Effort NOTIFY (BENOTIFY) 请求（而不是 NOTIFY 请求）以响应来自客户端的 SUBSCRIBE 请求。BENOTIFY 是对订阅通知握手的性能增强扩展，在此过程中，服务器将生成 BENOTIFY 请求，而不是通常的 NOTIFY 请求。其性能优点在于，BENOTIFY 请求不需要来自客户端的 200 OK 响应，而 NOTIFY 请求则需要。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="7dc67-320">有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7dc67-321">Live 通信服务器2003不支持 BENOTIFY 请求。</span><span class="sxs-lookup"><span data-stu-id="7dc67-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="7dc67-322">若要与在实时通信服务器2005和第三方服务器上运行的实时通信服务器2003服务器 API 编写的服务器应用程序互操作，可以通过将 BENOTIFY 请求的值设置为 <STRONG>FALSE</STRONG>来禁用这些请求。</span><span class="sxs-lookup"><span data-stu-id="7dc67-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="7dc67-323">BENOTIFY 目前不是 IETF（Internet 工程任务组）SIP 标准化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="7dc67-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="7dc67-324">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-325">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-326">msRTCSIP-EnableFederation（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p121">此属性是供 IT 管理员使用的全局开关，用于配置是否允许用户与其他组织的用户进行通信。管理员可使用此属性覆盖单个用户的 <strong>FederationEnabled</strong> 属性。此属性有助于保护内部网络免受蠕虫和病毒导致的 Internet 攻击，或针对公司的各种攻击。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="7dc67-330">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-331">1: 启用公共 IM 连接（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-332">2: 保留（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-333">4: 保留（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-334">8: 保留（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-335">16: 启用了远程呼叫控制 [电话]（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-336">64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-337">128: UCEnabled（为用户启用统一通信）（第 7 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-338">256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-339">512: RemoteCallControlDualMode（第 9 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-340">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-341">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="7dc67-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="7dc67-343">此属性指示给定服务器上是否已加载企业服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="7dc67-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-345">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="7dc67-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="7dc67-347">此属性包含用于外部访问的拨号代码。</span><span class="sxs-lookup"><span data-stu-id="7dc67-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-348">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="7dc67-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p122">此属性控制是否为单个用户启用联盟。它由企业服务层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-353">有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-354">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="7dc67-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="7dc67-356">此属性是一个多值列表，其中包含与池关联的所有 Enterprise Edition Server 的域名。</span><span class="sxs-lookup"><span data-stu-id="7dc67-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="7dc67-357">反向链接：<strong>链接 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="7dc67-358">此反向链接相应的正向链接为 <strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-359">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-360">msRTCSIP-Gateways（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-361">此多值字符串属性包含网关和端口的列表（每个网关）。</span><span class="sxs-lookup"><span data-stu-id="7dc67-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="7dc67-362">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-363">msRTCSIP-GlobalSettingsData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p123">此属性存储“名称:值”对。已定义的“名称:值”对用于“允许轮询状态”<strong></strong>设置。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-366">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-367">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="7dc67-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="7dc67-368">此属性是用于归类组通讯簿条目的组的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-369">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-370">msRTCSIP-HomeServer（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-371">Live 通信服务器2003中的新增 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="7dc67-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="7dc67-372">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-373">msRTCSIP-HomeServerString（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-374">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="7dc67-375">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-376">msRTCSIP-HomeUsers（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-377">Live 通信服务器2003中的新增 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="7dc67-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="7dc67-378">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="7dc67-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p124">此属性控制是否为单个用户启用外部用户访问。它由企业服务层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-383">有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-384">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-385">msRTCSIP-IsMaster（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-386">Live 通信服务器2003中的新增</span><span class="sxs-lookup"><span data-stu-id="7dc67-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="7dc67-387">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-388">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="7dc67-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="7dc67-389">此单值属性包含设备 ID (由 Lync for 电话服务) 用户控制的电话的 SIP URI 或电话 URI。</span><span class="sxs-lookup"><span data-stu-id="7dc67-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="7dc67-390">此属性标记为进行全局编录复制，并且已编入索引。</span><span class="sxs-lookup"><span data-stu-id="7dc67-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="7dc67-391">如果为用户启用了企业语音，则此属性存储该用户的电话号码的 E.164 规范化版本。</span><span class="sxs-lookup"><span data-stu-id="7dc67-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-392">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="7dc67-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p126">此单值属性包含 CSTA-SIP 网关服务器的 SIP URI。此属性标记为进行全局编录复制，但未编入索引。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-396">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="7dc67-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-397">msRTCSIP-LocalNormalizationData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-398">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-399">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-400">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-401">msRTCSIP-LocalNormalizationLinks（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p127">此多值属性包含与此位置配置文件关联的本地规范化可分辨名称 (DN) 列表。此属性的类型是 DN 二进制值。位置配置文件和本地规范化规则之间存在一对多关系。必须按照管理员指定的顺序维护本地规范化 DN 列表的顺序。顺序的保持是由 DN 二进制值的二进制值部分维护的，该部分指定了顺序索引。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="7dc67-407">正向链接：<strong>链接 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="7dc67-408">此正向链接属性相应的反向链接为 <strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-409">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-410">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="7dc67-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="7dc67-412">此属性包含规范化规则的选项列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-413">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-414">msRTCSIP-LocationName（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p128">此单值属性包含位置配置文件的友好名称，用于指示此配置文件所表示的位置。因为可能有多个位置配置文件，所以管理员需要一种方法来区分不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-417">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-418">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-419">msRTCSIP-locationProfileBL（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p129">此多值属性包含位置配置文件可分辨名称的列表。此属性指定一个或多个位置配置文件的反向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="7dc67-422">反向链接：<strong>链接 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="7dc67-423">此属性对应于正向链接 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-424">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-425">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-426">msRTCSIP-LocationProfileData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-427">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-428">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-429">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="7dc67-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="7dc67-431">此属性包含位置配置文件的选项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-432">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="7dc67-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="7dc67-434">此多值属性包含应用程序联系人的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-435">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="7dc67-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="7dc67-437">此多值属性包含位置配置文件的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-438">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-439">msRTCSIP-MaxNumOutstandingSearchPerServer（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-440">此属性表示每台服务器未处理搜索请求的最大数量。</span><span class="sxs-lookup"><span data-stu-id="7dc67-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-441">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-442">msRTCSIP-MaxNumSubscriptionsPerUser（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-443">该属性表示每个用户的最大订阅数。</span><span class="sxs-lookup"><span data-stu-id="7dc67-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-444">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-445">msRTCSIP-MaxPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-446">此属性表示最大订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-447">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-448">msRTCSIP-MaxRegistrationsTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-449">此属性表示最大注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-450">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-452">此属性表示最大漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-453">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="7dc67-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-455">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-456">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="7dc67-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p130">此属性是计算机类下属的一个服务控制点属性，该计算机类指定指向其所属多点控制单元 (MCU) 中心的反向链接。此服务控制点和属性是为每一个 Microsoft MCU 创建的。每个 Microsoft MCU 都必须找到其所属池的后端服务器，才能从中检索池级设置。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="7dc67-p131">此属性的值是 MCU 中心的可分辨名称 (DN)。此属性是单值属性，并且标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-463">正向链接：<strong>链接 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="7dc67-464">此正向链接属性相应的反向链接为 <strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-465">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="7dc67-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p132">此属性是多字符串保留属性。存储在此属性中的设置表示为“名称=值”对。当前定义的“名称=值”对如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="7dc67-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-471">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="7dc67-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="7dc67-473">这是一个单值属性，包含与池关联的单个 MCU 中心的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="7dc67-474">正向链接：<strong>链接 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="7dc67-475">此正向链接属性相应的反向链接为 <strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-476">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="7dc67-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="7dc67-478">此属性为单值字符串，用于指定 MCU 中心提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7dc67-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="7dc67-479">根据该 GUID 值，MCU 中心进程可确定是否向此 MCU 类型提供服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="7dc67-480">如果 GUID 值为 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，则默认情况下，在 Lync Server 中 (提供 MCU factory 过程) 将对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="7dc67-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="7dc67-481">对于任何其他 GUID 值，MCU 中心进程不会向该 MCU 类型提供服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-482">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="7dc67-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p134">此属性为可分辨名称 (DN) 的多值列表。此属性包含一个列表，其中列出了与此 MCU 中心关联的供应商的所有 MCU 服务器，且这些服务器属于同一类型。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="7dc67-487">反向链接：链接 ID 11027</span><span class="sxs-lookup"><span data-stu-id="7dc67-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="7dc67-488">此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-489">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="7dc67-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="7dc67-491">此属性为单值字符串，用于指定 MCU 可处理的媒体。</span><span class="sxs-lookup"><span data-stu-id="7dc67-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="7dc67-492">受支持的有效类型如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-493">要求</span><span class="sxs-lookup"><span data-stu-id="7dc67-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="7dc67-494">音频-视频</span><span class="sxs-lookup"><span data-stu-id="7dc67-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="7dc67-495">聊天</span><span class="sxs-lookup"><span data-stu-id="7dc67-495">chat</span></span></p></li>
<li><p><span data-ttu-id="7dc67-496">电话会议</span><span class="sxs-lookup"><span data-stu-id="7dc67-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-497">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="7dc67-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p135">此属性为指定 MCU 供应商名称的单值字符串。所有 Microsoft MCU 都将此属性指定为 <strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-501">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-502">msRTCSIP-MeetingFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p136">此属性定义为所有用户或联系对象在全局范围启用的各种会议选项。此属性为整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="7dc67-505">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-506">0: AllowOrganizeMeetingWithAnonymousParticipants 为 None（不允许用户邀请匿名用户加入会议）（未设置位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-507">4： AllowOrganizeMeetingWithAnonymousParticipants 是每个人 (允许所有用户邀请匿名用户加入会议)  (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="7dc67-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-508">8: AllowOrganizeMeetingWithAnonymousParticipants 为 UsePerUserSetting（根据每用户设置允许用户邀请匿名用户加入会议）（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-509">16: UserPerUserMeetingPolicy（按用户定义会议策略）（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-510">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-511">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-512">msRTCSIP-MeetingPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-513">此属性以单值属性的形式指定管理员已为此用户分配的策略的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-514">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-515">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-516">msRTCSIP-MinPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-517">此属性表示最小状态订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-518">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-519">msRTCSIP-MinRegistrationTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-520">此属性表示最小注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-521">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-522">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-523">msRTCSIP-MinRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-524">此属性表示最小漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="7dc67-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-525">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-526">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="7dc67-528">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="7dc67-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-529">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="7dc67-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="7dc67-531">此属性包含用于定义移动性设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="7dc67-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-532">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7dc67-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="7dc67-534">此属性包含移动性策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-535">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-536">msRTCSIP-NumDevicesPerUser（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-537">此属性表示用户可在其中注册 SIP 通信和订阅状态的设备数。</span><span class="sxs-lookup"><span data-stu-id="7dc67-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-538">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-539">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="7dc67-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p137">此属性指定为用户或联系对象启用的选项。此属性为整数类型的位掩码值。每个选项都由位表示。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-545">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-546">1: 启用公共即时消息 (IM) 连接（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-547">2: 保留（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-548">4: 保留（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-549">8: 保留（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-550">16: 启用了远程呼叫控制 [电话]（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-551">64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-552">128: UCEnabled（为用户启用 UC）（第 7 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-553">256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-554">512: RemoteCallControlDualMode（第 9 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-555">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="7dc67-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="7dc67-557">当用户的 ObjectSID 从 Windows NT Server 主体帐户复制到资源林或中央林中相应用户或联系人对象的此属性中时，此属性在资源林拓扑和中央林拓扑中用于实现单一登录。</span><span class="sxs-lookup"><span data-stu-id="7dc67-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="7dc67-558">Communicator Web Access 使用此属性或用户的 ObjectSID 搜索 AD DS 中的用户。</span><span class="sxs-lookup"><span data-stu-id="7dc67-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="7dc67-559">此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="7dc67-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="7dc67-561">此属性为应用程序联系人所有者的统一资源名称 (URN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-562">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-563">msRTCSIP-Pattern（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p139">此单值字符串属性包含用于将拨号号码匹配为 E.164 格式的模式。如果拨号号码与此模式匹配，则对所拨号码应用转换。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-566">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-567">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-568">msRTCSIP-PhoneRouteBL（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p140">此多值属性包含电话路由可分辨名称 (DN) 的列表。此属性指定一个或多个电话路由的反向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="7dc67-571">反向链接：<strong>链接 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="7dc67-572">此属性对应于正向链接 <strong>msRTCSIP-RouteUsageLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-573">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-574">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-575">msRTCSIP-PhoneRouteData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-576">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-577">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-578">msRTCSIP-PhoneRouteName（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-579">此单值 UNICODE 字符串属性指定电话路由的友好名称，以便于管理员引用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-580">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-581">msRTCSIP-PhoneUsageData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-582">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-583">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-584">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-585">msRTCSIP-PolicyContent（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p141">此属性为单值 Unicode 字符串。此字符串属性包含 XML 格式的策略定义。对于不同的策略类型，该 XML 架构定义是共用的，只有设置因每种策略类型而异。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="7dc67-589">下面定义了 XML 架构定义 (XSD)：</span><span class="sxs-lookup"><span data-stu-id="7dc67-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="7dc67-590">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-591">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-592">msRTCSIP-PolicyData（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-593">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-594">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-595">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-596">msRTCSIP-PolicyType（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p142">此单值 Unicode 字符串属性包含策略类型。有效策略类型如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-599">要求</span><span class="sxs-lookup"><span data-stu-id="7dc67-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="7dc67-600">电话</span><span class="sxs-lookup"><span data-stu-id="7dc67-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-601">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-602">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="7dc67-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="7dc67-604">此属性指定指向计算机所属池的反向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="7dc67-605">无论计算机运行的是标准版 Lync Server 还是企业版 Lync Server，都会设置此属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="7dc67-606">此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="7dc67-607">有效值为池的域名。</span><span class="sxs-lookup"><span data-stu-id="7dc67-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="7dc67-608">正向链接：<strong>链接 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="7dc67-609">此正向链接属性相应的反向链接为 <strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-610">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="7dc67-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="7dc67-612">这是一个多值属性，包含与 MCU 中心关联的池的可分辨名称 (DN) 的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="7dc67-613">反向链接：<strong>链接 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="7dc67-614">此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-615">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="7dc67-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-617">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-618">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="7dc67-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p144">此属性指定管理控制台显示的池的任意名称。管理员可以更改此名称。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="7dc67-622">有效值为表示池名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="7dc67-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-623">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p145">此属性为单值字符串值。如果管理员要创建的前端池的 FQDN 不符合从中创建该前端池的 Active Directory 域结构（例如 SIP 命名空间与域名系统 (DNS) 命名空间分离），则此属性的值（如果存在）表示该池的域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="7dc67-p146">我们建议将前端池域 FQDN 映射到该池所在的 Active Directory 域的域名部分。因此，当此属性中不存在值时，前端池 FQDN 将默认为 <strong>dnsHostName</strong> 属性所表示的 Active Directory 域名结构。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-629">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="7dc67-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="7dc67-631">与池关联的所有 Lync Server、Enterprise Edition 服务器的域名的多值列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="7dc67-632">此属性为整数类型，它定义池是否支持即时消息 (IM)、状态和会议。</span><span class="sxs-lookup"><span data-stu-id="7dc67-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="7dc67-633">可能的有效值类型如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-634">未定义：IM 和状态服务（Live Communications Server 2005 和 2003）</span><span class="sxs-lookup"><span data-stu-id="7dc67-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-635">1： IM 和状态服务 (Lync Server) </span><span class="sxs-lookup"><span data-stu-id="7dc67-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-636">2： (Lync Server) 的 IM 和状态和会议服务</span><span class="sxs-lookup"><span data-stu-id="7dc67-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-637">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-638">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="7dc67-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p148">此属性指定服务器池运行的是 Standard Edition Server 还是 Enterprise Edition Server。此属性为整数类型的位掩码值。每个选项都由位表示。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="7dc67-642">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-643">1: Standard Edition Server，承载用户（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-644">2: Enterprise Edition Server，承载用户（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-645">4: Standard Edition Server，承载应用程序（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-646">8: Enterprise Edition Server，承载应用程序（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="7dc67-647">由于 Lync Server 不支持仅托管应用程序的池，因此唯一有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="7dc67-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-648">5: Standard Edition Server，承载用户和应用程序（第 0 和 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-649">10: Enterprise Edition Server，承载用户和应用程序（第 1 和 3 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-650">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="7dc67-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p149">此属性定义池版本。它为整数类型，在每次主要产品发布时递增。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="7dc67-654">可能的有效值类型如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-655">0： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="7dc67-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="7dc67-656">1： Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="7dc67-657">2：使用 SP1 的 Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="7dc67-658">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="7dc67-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="7dc67-659">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7dc67-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="7dc67-660">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7dc67-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-661">使用 SP1 的 Live 通信服务器2005。</span><span class="sxs-lookup"><span data-stu-id="7dc67-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="7dc67-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="7dc67-663">此属性包含用于定义状态设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="7dc67-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-664">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="7dc67-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="7dc67-666">此属性包含状态策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-667">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p150">此属性为用户或联系人启用 SIP 消息。它添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="7dc67-671">有效值为用户所在 Standard Edition Server 或 Enterprise Edition 前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-672">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="7dc67-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="7dc67-674">此属性包含给定用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="7dc67-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="7dc67-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="7dc67-676">此属性包含专线设备的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="7dc67-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-677">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-678">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="7dc67-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="7dc67-679">此属性是一个布尔属性，用于确定是否已授权 Lync Server 使用其 GRUU 地址路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="7dc67-680">如果此值设置为 <strong>TRUE</strong>，则表示已授权 Lync Server 路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="7dc67-681">如果此值设置为 <strong>FALSE</strong>，则 Lync Server 无权路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-682">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-683">msRTCSIP-RouteUsageAttribute（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p152">此单值 UNICODE 字符串属性定义限定电话路由用法的属性。电话路由的选择基于两个元素确定：一是分配给电话路由的用法属性，二是经允许的主叫方的策略用法属性。将选择用法属性与主叫方允许的用法相匹配的第一个电话路由。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-687">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-688">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-689">msRTCSIP-RouteUsageLinks（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-690">此多值可分辨名称 (DN) 属性包含路由用法可分辨名称的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="7dc67-691">正向链接：<strong>链接 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="7dc67-692">此属性是反向链接 <strong>msRTCSIP-PhoneRouteBL</strong> 对应的正向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-693">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-695">此属性包含指向发往此 MCU 或受信任服务的所有 SIP 流量都必须通过的池的 DN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-696">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-697">msRTCSIP-RuleName（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-698">此单值 UNICODE 字符串属性指定规范化规则的友好名称，以方便管理员进行引用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-699">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-700">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="7dc67-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="7dc67-702">此属性表示组织中当前部署的架构版本。</span><span class="sxs-lookup"><span data-stu-id="7dc67-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-703">msRTCSIP-SearchMaxRequests（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-704">此属性限制当用户使用 Communicator 搜索联系人时，要从目录搜索返回的搜索结果的数量。</span><span class="sxs-lookup"><span data-stu-id="7dc67-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="7dc67-705">此属性将覆盖客户端提供的值。</span><span class="sxs-lookup"><span data-stu-id="7dc67-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-706">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-707">msRTCSIP-SearchMaxResults（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-708">此属性限制所返回的搜索请求数。</span><span class="sxs-lookup"><span data-stu-id="7dc67-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-709">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="7dc67-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p154">此多值属性为包含可分辨名称 (DN) 列表的反向链接。这些 DN 指向池或 <strong>TrustedService</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="7dc67-713">此属性对应于正向链接 <strong>msRTCSIP-TrustedServiceLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-714">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-715">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="7dc67-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-716">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-717">msRTCSIP-ServerReferenceBL（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p155">此多值属性包含可分辨名称的列表。这些可分辨名称是引用可分配默认位置配置文件的其他服务器对象的反向链接。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="7dc67-720">反向链接：<strong>链接 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="7dc67-721">此反向链接对应的正向链接为 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="7dc67-722">此反向链接属性仅引用池和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="7dc67-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-723">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-724">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="7dc67-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p156">此属性定义服务器的版本信息。此版本号应用于所有服务器角色。它是一个单调递增的整数，并且随每一次正式产品发布而递增。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="7dc67-729">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-730">未定义： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="7dc67-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="7dc67-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="7dc67-732">                 具有 SP1 的 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="7dc67-733">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="7dc67-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="7dc67-734">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7dc67-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="7dc67-735">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7dc67-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="7dc67-736">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dc67-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-737">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-738">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="7dc67-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="7dc67-739">此整数类型的单值属性指定 <strong>msDS-SourceObjectDN</strong> 所指对象的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7dc67-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-740">null | 0x00000001:表示来自另一个林的 Windows NT Server 主体用户对象</span><span class="sxs-lookup"><span data-stu-id="7dc67-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="7dc67-741">下面的属性表示来自另一个林的用于通讯组扩展的组类型：</span><span class="sxs-lookup"><span data-stu-id="7dc67-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-742">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="7dc67-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="7dc67-743">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="7dc67-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="7dc67-744">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="7dc67-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="7dc67-745">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="7dc67-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="7dc67-746">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="7dc67-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="7dc67-747">0x90000000：表示同一个林或另一个林中的自动助理或订阅者访问对象</span><span class="sxs-lookup"><span data-stu-id="7dc67-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-748">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-749">msRTCSIP-SubscriptionAuthRequired（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-750">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="7dc67-751">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="7dc67-753">此属性使您可以将用户或联系人对象从一个 Lync Server 池移动到另一个池。</span><span class="sxs-lookup"><span data-stu-id="7dc67-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="7dc67-754">此属性添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</span><span class="sxs-lookup"><span data-stu-id="7dc67-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="7dc67-755">有效值为用户要移至的目标 Standard Edition Server 或前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-756">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-757">msRTCSIP-TargetPhoneNumber（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-758">此单值字符串属性包含要路由到 <strong>msRTCSIP-Gateways</strong> 中定义的指定网关的电话号码模式或范围。</span><span class="sxs-lookup"><span data-stu-id="7dc67-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-759">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="7dc67-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="7dc67-761">此属性存储 Lync Server 用户的目标策略的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="7dc67-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-762">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-763">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="7dc67-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="7dc67-764">此属性存储租户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-765">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-766">msRTCSIP-Translation（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-767">如果找到匹配项，Lync Server 的语音功能将使用此属性，并且包含要应用于所拨号码的转换字符串。</span><span class="sxs-lookup"><span data-stu-id="7dc67-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-768">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="7dc67-769">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="7dc67-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-771">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-772">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p158">此属性是包含 MCU 的 FQDN 的字符串值。这是一个单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-777">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="7dc67-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-779">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-780">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p159">此属性是一个字符串值，其中包含运行代理服务器的服务器的 FQDN。此属性为单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-785">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="7dc67-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-787">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-789">此属性是表示受信任服务器的 FQDN 的单值属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-790">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="7dc67-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="7dc67-792">此属性指定受信任服务器列表中的服务器的版本号。</span><span class="sxs-lookup"><span data-stu-id="7dc67-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="7dc67-793">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-794">NULL： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="7dc67-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="7dc67-795">2： Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="7dc67-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="7dc67-796">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="7dc67-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="7dc67-797">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7dc67-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="7dc67-798">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7dc67-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="7dc67-799">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dc67-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-800">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="7dc67-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="7dc67-802">此属性定义为受信任的服务启用的选项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-803">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="7dc67-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="7dc67-805">此多值属性包含可分辨名称 (DN) 的列表，这些名称引用受信任的服务对象，如媒体中继身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="7dc67-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="7dc67-806">媒体中继身份验证服务在运行 A/V 会议服务的边缘服务器上 (物理并置) 必须与一个池关联，以支持远程用户的音频方案。</span><span class="sxs-lookup"><span data-stu-id="7dc67-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="7dc67-807">此正向链接属性相应的反向链接为 <strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-808">全</span><span class="sxs-lookup"><span data-stu-id="7dc67-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="7dc67-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="7dc67-810">此属性是一个整数，它定义用于连接到此 GRUU 服务的端口号。</span><span class="sxs-lookup"><span data-stu-id="7dc67-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-811">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="7dc67-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="7dc67-813">此属性是一个字符串值，用于定义它所表示的 GRUU 服务的类型。</span><span class="sxs-lookup"><span data-stu-id="7dc67-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="7dc67-814">有效的 GRUU 服务类型如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="7dc67-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="7dc67-816">网关</span><span class="sxs-lookup"><span data-stu-id="7dc67-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="7dc67-817">媒体中继身份验证服务 (MRAS)</span><span class="sxs-lookup"><span data-stu-id="7dc67-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="7dc67-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="7dc67-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="7dc67-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="7dc67-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-820">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="7dc67-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-822">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-823">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="7dc67-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="7dc67-825">此属性是一个字符串值，其中包含运行 Lync Server Web 服务的 IIS 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7dc67-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="7dc67-826">这是一个单值属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-826">This is a single-valued attribute.</span></span> <span data-ttu-id="7dc67-827">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="7dc67-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-828">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-829">msRTCSIP-UCFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p162">此属性定义对所有用户或联系对象在全局范围启用的各种 UC 选项。此属性为整数类型的位掩码值。每个选项均由位表示。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="7dc67-833">此属性可能的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-834">4: UsePerUserUCPolicy（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="7dc67-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="7dc67-835">设置此位后，将按用户分别定义 UC 策略。</span><span class="sxs-lookup"><span data-stu-id="7dc67-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-836">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-837">msRTCSIP-UCPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-838">此单值属性包含管理员已为此用户分配的 UC 策略的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-839">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-840">msRTCSIP-UserDomainList（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p163">此属性提供林中承载启用 SIP 的用户的所有域的列表。默认为空列表，表示林中的所有域都已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="7dc67-843">有效值为表示各个域的域名的多个字符串。</span><span class="sxs-lookup"><span data-stu-id="7dc67-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-844">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="7dc67-845">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-846">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="7dc67-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="7dc67-847">此属性确定当前是否为 Lync Server 启用了用户。</span><span class="sxs-lookup"><span data-stu-id="7dc67-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="7dc67-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="7dc67-849">此多值属性包含名称 = 值格式的名称-值对列表 &quot; 。 &quot; 此属性被标记为要进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="7dc67-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-850">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="7dc67-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="7dc67-852">此属性包含指向位置配置文件对象的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="7dc67-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-853">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="7dc67-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="7dc67-855">此属性存储用户策略的名称值对。</span><span class="sxs-lookup"><span data-stu-id="7dc67-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-856">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="7dc67-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p164">这是一个多值属性，包含带二进制值的可分辨名称 (DN_WITH_BINARY) 的列表，这些名称指向不同类型的全局用户策略。二进制值部分则指示 DN 部分所指向的策略的类型。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="7dc67-860">有效的二进制值如下：</span><span class="sxs-lookup"><span data-stu-id="7dc67-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-861">0x00000001：会议策略</span><span class="sxs-lookup"><span data-stu-id="7dc67-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="7dc67-862">0x00000002：UC 策略</span><span class="sxs-lookup"><span data-stu-id="7dc67-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="7dc67-863">0x00000005：状态策略</span><span class="sxs-lookup"><span data-stu-id="7dc67-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-864">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7dc67-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p165">这是 SIP 路由组 ID。相同组中的用户将注册到相同的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-868">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="7dc67-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p166">这是一个多值属性。此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-872">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="7dc67-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="7dc67-874">此单值属性指向 Web 组件所属的池或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="7dc67-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="7dc67-875">正向链接：<strong>链接 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="7dc67-876">此正向链接属性相应的反向链接为 <strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-877">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="7dc67-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="7dc67-p167">此属性为可分辨名称的多值列表。此属性包含与此池关联的所有 Web 服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="7dc67-881">反向链接：<strong>链接 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="7dc67-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="7dc67-882">此反向链接相应的正向链接为 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="7dc67-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-883">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-884">msRTCSIP-WMIInstanceId（作废）</span><span class="sxs-lookup"><span data-stu-id="7dc67-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7dc67-885">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="7dc67-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="7dc67-886">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="7dc67-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="7dc67-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="7dc67-888">电话使用此现有 Active Directory 属性指定电话的备用 TCP/IP 地址列表。</span><span class="sxs-lookup"><span data-stu-id="7dc67-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-889">Windows Server 2008 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="7dc67-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="7dc67-891">Lync Server 中的语音组件使用此现有 Active Directory 属性，仅用于联系人对象，用于将呼叫路由到统一消息自动助理和订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="7dc67-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="7dc67-892">无条件呼叫转移地址存储在此多值属性中。</span><span class="sxs-lookup"><span data-stu-id="7dc67-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="7dc67-893">此帐户专为自动助理和订阅者访问的特定用途而创建。</span><span class="sxs-lookup"><span data-stu-id="7dc67-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="7dc67-894">管理员不应修改此帐户的属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-895">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dc67-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7dc67-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7dc67-897">此现有 Active Directory 多值属性是 Windows 2000 中引入的基本 Active Directory 架构的一部分。</span><span class="sxs-lookup"><span data-stu-id="7dc67-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="7dc67-898">此属性包含用户电子邮件的各种 X400、X500 和 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="7dc67-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="7dc67-899">在 Live 通信服务器2003及更高版本中，将使用 sip：标记将用户的 SIP URI 添加到此列表中 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="7dc67-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="7dc67-900">下列应用程序从此属性搜索用户的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="7dc67-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dc67-901">Microsoft Office Outlook 2003 消息和协作客户端</span><span class="sxs-lookup"><span data-stu-id="7dc67-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="7dc67-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="7dc67-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7dc67-903">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dc67-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="7dc67-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="7dc67-905">此现有 Active Directory 属性包含用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7dc67-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="7dc67-906">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="7dc67-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

