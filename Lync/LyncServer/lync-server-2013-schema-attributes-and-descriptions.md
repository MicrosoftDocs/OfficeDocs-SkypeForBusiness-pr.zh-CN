---
title: Lync Server 2013：架构属性和说明
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
ms.openlocfilehash: c95fa0450a85aea4ffdd53dfcb61ddb5b97ed532
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="0125a-102">Lync Server 2013 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="0125a-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0125a-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0125a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0125a-104">本节介绍 Lync Server 2013 使用的所有架构属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="0125a-105">对于与属性相关联的类，请参阅[在 Lync Server 2013 中按类架构属性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="0125a-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="0125a-106">有关 Lync Server 2013 中新增的类和属性的列表，请参阅[Lync server 2013 中的架构更改](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="0125a-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="0125a-p102">将链接为一对的属性指定为正向链接或反向链接。指向另一个对象的属性为正向链接；向回指向第一个对象的其他对象的属性为反向链接。正向链接可更新，而反向链接为只读。</span><span class="sxs-lookup"><span data-stu-id="0125a-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="0125a-p103">有些属性具有位掩码值。对于这些属性，每项设置均由位表示，所显示的十进制值表示各个位的位置。位的位置从第 0 位开始。例如，1（二进制）设置了第 0 位，10000（二进制）设置了第 4 位。每位表示一个属性。下面给出了一些示例：</span><span class="sxs-lookup"><span data-stu-id="0125a-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="0125a-116">10000（二进制）的十进制值为 16（即设置了第 4 位）。</span><span class="sxs-lookup"><span data-stu-id="0125a-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="0125a-117">100000000（二进制）的十进制值为 256（即设置了第 8 位）。</span><span class="sxs-lookup"><span data-stu-id="0125a-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="0125a-118">1100（二进制）的十进制值为 12（即设置了第 2 位和第 3 位；这两位表示的属性已启用）。</span><span class="sxs-lookup"><span data-stu-id="0125a-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="0125a-119">1111000001（二进制）的十进制值为 961（即设置了第 0、6、7、8 和 9 位；这些位中每位表示的属性已启用）。</span><span class="sxs-lookup"><span data-stu-id="0125a-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="0125a-120">Lync Server 2013 的架构属性</span><span class="sxs-lookup"><span data-stu-id="0125a-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0125a-121">属性</span><span class="sxs-lookup"><span data-stu-id="0125a-121">Attribute</span></span></th>
<th><span data-ttu-id="0125a-122">说明</span><span class="sxs-lookup"><span data-stu-id="0125a-122">Description</span></span></th>
<th><span data-ttu-id="0125a-123">注释</span><span class="sxs-lookup"><span data-stu-id="0125a-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0125a-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="0125a-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="0125a-125">Active Directory 域服务中当前与<strong>msRTCSIP</strong>和<strong>msRTCSIP</strong>类关联的现有属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="0125a-126">此属性指定池或监视服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="0125a-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="0125a-127">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-128">Microsoft Office Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-129">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="0125a-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-p105">此属性包含一个字符串，表示另一个林中与此对象相对应的对象的可分辨名称 (DN)。此属性用于通讯组扩展和自动助理。此属性是在 Windows Server 2003 R2 的默认 Active Directory 架构中定义的。</span><span class="sxs-lookup"><span data-stu-id="0125a-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="0125a-133">为了省去将 AD DS 升级到 Windows Server 2003 R2 的麻烦，Active Directory 架构准备使用此属性定义扩展 Windows Server 2003 架构。</span><span class="sxs-lookup"><span data-stu-id="0125a-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="0125a-134">Microsoft Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="0125a-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="0125a-136">此多值属性保存语音邮件设置。</span><span class="sxs-lookup"><span data-stu-id="0125a-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="0125a-137">此属性与 Exchange 统一消息（UM）共享。</span><span class="sxs-lookup"><span data-stu-id="0125a-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="0125a-138">Microsoft Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0125a-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="0125a-140">此多值属性可保存应用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="0125a-141">保留策略会在保留持续时间内保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="0125a-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="0125a-142">此属性与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="0125a-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="0125a-143">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="0125a-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="0125a-145">此属性存储用户的音频会议提供商信息。</span><span class="sxs-lookup"><span data-stu-id="0125a-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="0125a-146">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="0125a-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="0125a-148">此属性指向应用程序联系人的受信任的服务项。</span><span class="sxs-lookup"><span data-stu-id="0125a-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="0125a-149">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="0125a-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="0125a-151">此属性包含应用程序服务器上所承载的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="0125a-152">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="0125a-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="0125a-154">此属性指定应用程序联系人的选项。</span><span class="sxs-lookup"><span data-stu-id="0125a-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="0125a-155">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="0125a-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="0125a-157">此属性包含应用程序联系人的主要语言。</span><span class="sxs-lookup"><span data-stu-id="0125a-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="0125a-158">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="0125a-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="0125a-160">此多值属性包含应用程序联系人的辅助语言。</span><span class="sxs-lookup"><span data-stu-id="0125a-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="0125a-161">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="0125a-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="0125a-p108">此属性包含属于此池的应用程序服务器的列表。此反向链接属性相应的正向链接为 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-165">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="0125a-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="0125a-167">此属性指向此应用程序服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="0125a-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="0125a-168">它属于正向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-168">This is the forward link.</span></span> <span data-ttu-id="0125a-169">相应的反向链接为 <strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-170">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-171">msRTCSIP-ArchiveDefault（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-172">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-173">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-174">msRTCSIP-ArchiveDefaultFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p110">此属性指定林边界内用于对所有用户通信进行存档的全局默认设置。这由存档代理层强制执行。此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-178"><strong>TRUE</strong>：存档所有用户</span><span class="sxs-lookup"><span data-stu-id="0125a-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="0125a-179"><strong>FALSE</strong>：不存档所有用户</span><span class="sxs-lookup"><span data-stu-id="0125a-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="0125a-180">此属性在林边界内对内部网络中的用户通信存档方式进行全局控制。</span><span class="sxs-lookup"><span data-stu-id="0125a-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="0125a-181"><strong>Live Communications Server 2005 行为（现已撤销）</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="0125a-182">此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-183">0: 对消息正文进行存档 [0 位]</span><span class="sxs-lookup"><span data-stu-id="0125a-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="0125a-184">1: 不对消息正文进行存档 [0 位]</span><span class="sxs-lookup"><span data-stu-id="0125a-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="0125a-185"><strong>Office Communications Server 2007 行为</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="0125a-186">此属性的值范围如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-187">0: ArchiveFederationDefaultWithoutBody（已撤销）</span><span class="sxs-lookup"><span data-stu-id="0125a-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="0125a-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="0125a-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="0125a-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="0125a-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="0125a-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="0125a-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="0125a-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="0125a-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="0125a-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="0125a-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="0125a-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="0125a-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="0125a-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="0125a-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="0125a-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="0125a-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="0125a-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="0125a-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-202">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-203">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-204">msRTCSIP-ArchiveFederationDefault（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-205">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-206">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-207">msRTCSIP-ArchiveFederationDefaultFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-208">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-209">在 Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="0125a-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="0125a-p111">此属性是一个用作位字段的整数，用于控制是否要对单个用户的通信进行存档。这种控制由存档代理层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-214">此属性的作用域特定于单个用户或联系人。</span><span class="sxs-lookup"><span data-stu-id="0125a-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="0125a-215">Lync Server 中的有效值（以及关联的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="0125a-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-216">0: 不存档（未设置位）</span><span class="sxs-lookup"><span data-stu-id="0125a-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="0125a-217">1: 已撤销（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="0125a-218">2: 已撤销（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="0125a-219">4: 对内部通信进行存档（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-220">8: 对联盟通信进行存档（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="0125a-221">Live 通信服务器2005中以前的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="0125a-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-222">0：按以下优先顺序使用由 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 定义的默认值：</span><span class="sxs-lookup"><span data-stu-id="0125a-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-223">1: 存档</span><span class="sxs-lookup"><span data-stu-id="0125a-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="0125a-224">2: 不存档</span><span class="sxs-lookup"><span data-stu-id="0125a-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="0125a-225">3: 存档，但不包括消息正文</span><span class="sxs-lookup"><span data-stu-id="0125a-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="0125a-226">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-227">msRTCSIP-ArchivingServerData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-228">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-229">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-230">msRTCSIP-ArchivingServerVersion（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p113">此属性定义存档服务的版本。此属性属于单调递增的整数类型，它随每次正式产品发布而递增。可能的有效值为：</span><span class="sxs-lookup"><span data-stu-id="0125a-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-234">未定义： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="0125a-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="0125a-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="0125a-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="0125a-236">                 具有 SP1 的 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="0125a-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="0125a-237">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="0125a-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="0125a-238">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0125a-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-239">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-240">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="0125a-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="0125a-p114">此属性指定池的后端服务器的 FQDN。因为每个池只能有一个后端服务器，所以这是一个单值属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="0125a-244">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-245">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="0125a-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="0125a-247">此属性包含承载会议目录的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="0125a-248">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="0125a-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="0125a-250">此属性包含会议目录的标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="0125a-251">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="0125a-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="0125a-253">此属性包含要向其移动会议目录的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="0125a-254">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-255">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="0125a-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="0125a-256">此布尔属性定义电话用法是否为默认用法。</span><span class="sxs-lookup"><span data-stu-id="0125a-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="0125a-257">如果此属性设置为 <strong>TRUE</strong>，则电话用法为默认用法，且管理员无法删除该用法。</span><span class="sxs-lookup"><span data-stu-id="0125a-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="0125a-258">如果此属性设置为 <strong>FALSE</strong>，则可以删除该用法。</span><span class="sxs-lookup"><span data-stu-id="0125a-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="0125a-259">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="0125a-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="0125a-261">此属性标识组织外部用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="0125a-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="0125a-262">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="0125a-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="0125a-264">此属性标识组织内的用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="0125a-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="0125a-265">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-266">msRTCSIP-DefaultLocationProfileLink（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-267">此单值属性包含分配给它的位置配置文件类对象的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="0125a-268">正向链接：<strong>链接 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="0125a-269">相应的反向链接为 <strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-270">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-271">msRTCSIP-DefaultPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-272">此布尔属性指定策略是否为默认策略。</span><span class="sxs-lookup"><span data-stu-id="0125a-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="0125a-273">当此属性设置为 <strong>TRUE</strong> 时，策略为默认策略。</span><span class="sxs-lookup"><span data-stu-id="0125a-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-274">Office 通信服务器2007中的新增项</span><span class="sxs-lookup"><span data-stu-id="0125a-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="0125a-275">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-276">msRTCSIP-DefaultRouteToEdgeProxy（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-277">此属性指定运行访问边缘服务的边缘服务器的 FQDN （如果可以直接访问），或指定运行访问边缘服务的服务器池的硬件负载平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0125a-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="0125a-278">如果只能通过一个或多个控制器访问运行访问边缘服务的服务器，则此属性指定 FQDN 和（可选）控制器的端口号，或者为控制器池提供服务的硬件负载平衡器的端口号。</span><span class="sxs-lookup"><span data-stu-id="0125a-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="0125a-279">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-280">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-281">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-282">msRTCSIP-DefaultRouteToEdgeProxyPort（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-283">此属性表示应用于连接到运行访问边缘服务的服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="0125a-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="0125a-284">有效值为指定要使用的端口的整数值。</span><span class="sxs-lookup"><span data-stu-id="0125a-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="0125a-285">默认值为 5061。</span><span class="sxs-lookup"><span data-stu-id="0125a-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="0125a-286">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-287">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-288">msRTCSIP-DefPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-289">此属性表示默认的状态订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="0125a-290">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-291">msRTCSIP-DefRegistrationTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-292">此属性表示默认的注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-293">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-295">此属性表示默认的漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-296">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="0125a-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="0125a-298">此属性在拆分域拓扑中使用，并且包含完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="0125a-299">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-300">msRTCSIP-Description（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-301">此单值 UNICODE 字符串属性包含对此电话路由或规范化规则的友好描述。</span><span class="sxs-lookup"><span data-stu-id="0125a-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="0125a-302">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-303">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="0125a-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="0125a-305">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-306">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="0125a-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="0125a-307">此属性表示为注册器配置的域。</span><span class="sxs-lookup"><span data-stu-id="0125a-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="0125a-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="0125a-309">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-310">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-312">此属性指定运行访问边缘服务的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0125a-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="0125a-313">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-314">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-315">msRTCSIP-EnableBestEffortNotify（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p119">此属性控制服务器是否生成 Best Effort NOTIFY (BENOTIFY) 请求（而不是 NOTIFY 请求）以响应来自客户端的 SUBSCRIBE 请求。BENOTIFY 是对订阅通知握手的性能增强扩展，在此过程中，服务器将生成 BENOTIFY 请求，而不是通常的 NOTIFY 请求。其性能优点在于，BENOTIFY 请求不需要来自客户端的 200 OK 响应，而 NOTIFY 请求则需要。</span><span class="sxs-lookup"><span data-stu-id="0125a-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="0125a-319">有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0125a-320">Live 通信服务器2003不支持 BENOTIFY 请求。</span><span class="sxs-lookup"><span data-stu-id="0125a-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="0125a-321">若要与在实时通信服务器2005和第三方服务器上运行的实时通信服务器2003服务器 API 编写的服务器应用程序互操作，可以通过将 BENOTIFY 请求的值设置为<STRONG>FALSE</STRONG>来禁用这些请求。</span><span class="sxs-lookup"><span data-stu-id="0125a-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="0125a-322">BENOTIFY 目前不是 IETF（Internet 工程任务组）SIP 标准化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="0125a-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="0125a-323">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-324">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-325">msRTCSIP-EnableFederation（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p121">此属性是供 IT 管理员使用的全局开关，用于配置是否允许用户与其他组织的用户进行通信。管理员可使用此属性覆盖单个用户的 <strong>FederationEnabled</strong> 属性。此属性有助于保护内部网络免受蠕虫和病毒导致的 Internet 攻击，或针对公司的各种攻击。</span><span class="sxs-lookup"><span data-stu-id="0125a-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="0125a-329">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-330">1: 启用公共 IM 连接（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="0125a-331">2: 保留（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="0125a-332">4: 保留（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-333">8: 保留（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="0125a-334">16: 启用了远程呼叫控制 [电话]（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="0125a-335">64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="0125a-336">128: UCEnabled（为用户启用统一通信）（第 7 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="0125a-337">256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="0125a-338">512: RemoteCallControlDualMode（第 9 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-339">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-340">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="0125a-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="0125a-342">此属性指示给定服务器上是否已加载企业服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="0125a-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="0125a-344">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="0125a-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="0125a-346">此属性包含用于外部访问的拨号代码。</span><span class="sxs-lookup"><span data-stu-id="0125a-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="0125a-347">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="0125a-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="0125a-p122">此属性控制是否为单个用户启用联盟。它由企业服务层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-352">有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-353">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="0125a-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="0125a-355">此属性是一个多值列表，其中包含与池关联的所有 Enterprise Edition Server 的域名。</span><span class="sxs-lookup"><span data-stu-id="0125a-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="0125a-356">反向链接：<strong>链接 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="0125a-357">此反向链接相应的正向链接为 <strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-358">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-359">msRTCSIP-Gateways（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-360">此多值字符串属性包含网关和端口的列表（每个网关）。</span><span class="sxs-lookup"><span data-stu-id="0125a-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="0125a-361">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-362">msRTCSIP-GlobalSettingsData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p123">此属性存储“名称:值”对。已定义的“名称:值”对用于“允许轮询状态”<strong></strong>设置。</span><span class="sxs-lookup"><span data-stu-id="0125a-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="0125a-365">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-366">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="0125a-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="0125a-367">此属性是用于归类组通讯簿条目的组的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="0125a-368">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-369">msRTCSIP-HomeServer（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-370">Live 通信服务器2003中的新增（未使用）。</span><span class="sxs-lookup"><span data-stu-id="0125a-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="0125a-371">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-372">msRTCSIP-HomeServerString（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-373">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="0125a-374">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-375">msRTCSIP-HomeUsers（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-376">Live 通信服务器2003中的新增（未使用）。</span><span class="sxs-lookup"><span data-stu-id="0125a-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="0125a-377">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="0125a-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="0125a-p124">此属性控制是否为单个用户启用外部用户访问。它由企业服务层强制执行。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-382">有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-383">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-384">msRTCSIP-IsMaster（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-385">Live 通信服务器2003中的新增</span><span class="sxs-lookup"><span data-stu-id="0125a-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="0125a-386">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-387">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="0125a-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="0125a-388">此单值属性包含 Lync for 电话服务使用的设备 ID （用户控制的电话的 SIP URI 或电话 URI）。</span><span class="sxs-lookup"><span data-stu-id="0125a-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="0125a-389">此属性标记为进行全局编录复制，并且已编入索引。</span><span class="sxs-lookup"><span data-stu-id="0125a-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="0125a-390">如果为用户启用了企业语音，则此属性存储该用户的电话号码的 E.164 规范化版本。</span><span class="sxs-lookup"><span data-stu-id="0125a-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="0125a-391">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="0125a-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="0125a-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="0125a-p126">此单值属性包含 CSTA-SIP 网关服务器的 SIP URI。此属性标记为进行全局编录复制，但未编入索引。</span><span class="sxs-lookup"><span data-stu-id="0125a-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="0125a-395">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="0125a-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-396">msRTCSIP-LocalNormalizationData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-397">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-398">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-399">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-400">msRTCSIP-LocalNormalizationLinks（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p127">此多值属性包含与此位置配置文件关联的本地规范化可分辨名称 (DN) 列表。此属性的类型是 DN 二进制值。位置配置文件和本地规范化规则之间存在一对多关系。必须按照管理员指定的顺序维护本地规范化 DN 列表的顺序。顺序的保持是由 DN 二进制值的二进制值部分维护的，该部分指定了顺序索引。</span><span class="sxs-lookup"><span data-stu-id="0125a-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="0125a-406">正向链接：<strong>链接 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="0125a-407">此正向链接属性相应的反向链接为 <strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-408">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-409">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="0125a-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="0125a-411">此属性包含规范化规则的选项列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="0125a-412">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-413">msRTCSIP-LocationName（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p128">此单值属性包含位置配置文件的友好名称，用于指示此配置文件所表示的位置。因为可能有多个位置配置文件，所以管理员需要一种方法来区分不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0125a-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="0125a-416">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-417">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-418">msRTCSIP-locationProfileBL（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p129">此多值属性包含位置配置文件可分辨名称的列表。此属性指定一个或多个位置配置文件的反向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="0125a-421">反向链接：<strong>链接 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="0125a-422">此属性对应于正向链接 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-423">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-424">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-425">msRTCSIP-LocationProfileData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-426">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-427">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-428">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="0125a-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="0125a-430">此属性包含位置配置文件的选项。</span><span class="sxs-lookup"><span data-stu-id="0125a-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="0125a-431">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="0125a-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="0125a-433">此多值属性包含应用程序联系人的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="0125a-434">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="0125a-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="0125a-436">此多值属性包含位置配置文件的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="0125a-437">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-438">msRTCSIP-MaxNumOutstandingSearchPerServer（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-439">此属性表示每台服务器未处理搜索请求的最大数量。</span><span class="sxs-lookup"><span data-stu-id="0125a-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="0125a-440">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-441">msRTCSIP-MaxNumSubscriptionsPerUser（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-442">该属性表示每个用户的最大订阅数。</span><span class="sxs-lookup"><span data-stu-id="0125a-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="0125a-443">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-444">msRTCSIP-MaxPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-445">此属性表示最大订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-446">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-447">msRTCSIP-MaxRegistrationsTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-448">此属性表示最大注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-449">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-451">此属性表示最大漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-452">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="0125a-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="0125a-454">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-455">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="0125a-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="0125a-p130">此属性是计算机类下属的一个服务控制点属性，该计算机类指定指向其所属多点控制单元 (MCU) 中心的反向链接。此服务控制点和属性是为每一个 Microsoft MCU 创建的。每个 Microsoft MCU 都必须找到其所属池的后端服务器，才能从中检索池级设置。</span><span class="sxs-lookup"><span data-stu-id="0125a-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="0125a-p131">此属性的值是 MCU 中心的可分辨名称 (DN)。此属性是单值属性，并且标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-462">正向链接：<strong>链接 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="0125a-463">此正向链接属性相应的反向链接为 <strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-464">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="0125a-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="0125a-p132">此属性是多字符串保留属性。存储在此属性中的设置表示为“名称=值”对。当前定义的“名称=值”对如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="0125a-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-470">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="0125a-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="0125a-472">这是一个单值属性，包含与池关联的单个 MCU 中心的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="0125a-473">正向链接：<strong>链接 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="0125a-474">此正向链接属性相应的反向链接为 <strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-475">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="0125a-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="0125a-477">此属性为单值字符串，用于指定 MCU 中心提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0125a-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="0125a-478">根据该 GUID 值，MCU 中心进程可确定是否向此 MCU 类型提供服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="0125a-479">如果 GUID 值为<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，则 MCU 工厂进程（在 Lync Server 中默认可用）将对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="0125a-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="0125a-480">对于任何其他 GUID 值，MCU 中心进程不会向该 MCU 类型提供服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="0125a-481">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="0125a-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="0125a-p134">此属性为可分辨名称 (DN) 的多值列表。此属性包含一个列表，其中列出了与此 MCU 中心关联的供应商的所有 MCU 服务器，且这些服务器属于同一类型。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="0125a-486">反向链接：链接 ID 11027</span><span class="sxs-lookup"><span data-stu-id="0125a-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="0125a-487">此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-488">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="0125a-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="0125a-490">此属性为单值字符串，用于指定 MCU 可处理的媒体。</span><span class="sxs-lookup"><span data-stu-id="0125a-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="0125a-491">受支持的有效类型如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-492">要求</span><span class="sxs-lookup"><span data-stu-id="0125a-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="0125a-493">音频-视频</span><span class="sxs-lookup"><span data-stu-id="0125a-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="0125a-494">聊天</span><span class="sxs-lookup"><span data-stu-id="0125a-494">chat</span></span></p></li>
<li><p><span data-ttu-id="0125a-495">电话会议</span><span class="sxs-lookup"><span data-stu-id="0125a-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-496">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="0125a-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="0125a-p135">此属性为指定 MCU 供应商名称的单值字符串。所有 Microsoft MCU 都将此属性指定为 <strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-500">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-501">msRTCSIP-MeetingFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p136">此属性定义为所有用户或联系对象在全局范围启用的各种会议选项。此属性为整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="0125a-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="0125a-504">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-505">0: AllowOrganizeMeetingWithAnonymousParticipants 为 None（不允许用户邀请匿名用户加入会议）（未设置位）</span><span class="sxs-lookup"><span data-stu-id="0125a-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="0125a-506">4： AllowOrganizeMeetingWithAnonymousParticipants 为 Everyone （允许所有用户邀请匿名用户参加会议）（bit 位置2）</span><span class="sxs-lookup"><span data-stu-id="0125a-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-507">8: AllowOrganizeMeetingWithAnonymousParticipants 为 UsePerUserSetting（根据每用户设置允许用户邀请匿名用户加入会议）（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="0125a-508">16: UserPerUserMeetingPolicy（按用户定义会议策略）（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-509">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-510">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-511">msRTCSIP-MeetingPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-512">此属性以单值属性的形式指定管理员已为此用户分配的策略的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="0125a-513">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-514">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-515">msRTCSIP-MinPresenceSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-516">此属性表示最小状态订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-517">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-518">msRTCSIP-MinRegistrationTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-519">此属性表示最小注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-520">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-521">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-523">此属性表示最小漫游数据订阅超时时段。</span><span class="sxs-lookup"><span data-stu-id="0125a-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="0125a-524">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-525">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="0125a-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="0125a-527">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="0125a-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="0125a-528">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="0125a-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="0125a-530">此属性包含用于定义移动性设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="0125a-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="0125a-531">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="0125a-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="0125a-533">此属性包含移动性策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="0125a-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="0125a-534">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-535">msRTCSIP-NumDevicesPerUser（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-536">此属性表示用户可在其中注册 SIP 通信和订阅状态的设备数。</span><span class="sxs-lookup"><span data-stu-id="0125a-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="0125a-537">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-538">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="0125a-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="0125a-p137">此属性指定为用户或联系对象启用的选项。此属性为整数类型的位掩码值。每个选项都由位表示。此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-544">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-545">1: 启用公共即时消息 (IM) 连接（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="0125a-546">2: 保留（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="0125a-547">4: 保留（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-548">8: 保留（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="0125a-549">16: 启用了远程呼叫控制 [电话]（第 4 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="0125a-550">64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="0125a-551">128: UCEnabled（为用户启用 UC）（第 7 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="0125a-552">256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="0125a-553">512: RemoteCallControlDualMode（第 9 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-554">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="0125a-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="0125a-556">当用户的 ObjectSID 从 Windows NT Server 主体帐户复制到资源林或中央林中相应用户或联系人对象的此属性中时，此属性在资源林拓扑和中央林拓扑中用于实现单一登录。</span><span class="sxs-lookup"><span data-stu-id="0125a-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="0125a-557">Communicator Web Access 使用此属性或用户的 ObjectSID 搜索 AD DS 中的用户。</span><span class="sxs-lookup"><span data-stu-id="0125a-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="0125a-558">此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="0125a-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="0125a-560">此属性为应用程序联系人所有者的统一资源名称 (URN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="0125a-561">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-562">msRTCSIP-Pattern（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p139">此单值字符串属性包含用于将拨号号码匹配为 E.164 格式的模式。如果拨号号码与此模式匹配，则对所拨号码应用转换。</span><span class="sxs-lookup"><span data-stu-id="0125a-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="0125a-565">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-566">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-567">msRTCSIP-PhoneRouteBL（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p140">此多值属性包含电话路由可分辨名称 (DN) 的列表。此属性指定一个或多个电话路由的反向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="0125a-570">反向链接：<strong>链接 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="0125a-571">此属性对应于正向链接 <strong>msRTCSIP-RouteUsageLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-572">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-573">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-574">msRTCSIP-PhoneRouteData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-575">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-576">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-577">msRTCSIP-PhoneRouteName（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-578">此单值 UNICODE 字符串属性指定电话路由的友好名称，以便于管理员引用。</span><span class="sxs-lookup"><span data-stu-id="0125a-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="0125a-579">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-580">msRTCSIP-PhoneUsageData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-581">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-582">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-583">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-584">msRTCSIP-PolicyContent（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p141">此属性为单值 Unicode 字符串。此字符串属性包含 XML 格式的策略定义。对于不同的策略类型，该 XML 架构定义是共用的，只有设置因每种策略类型而异。</span><span class="sxs-lookup"><span data-stu-id="0125a-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="0125a-588">下面定义了 XML 架构定义 (XSD)：</span><span class="sxs-lookup"><span data-stu-id="0125a-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="0125a-589">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-590">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-591">msRTCSIP-PolicyData（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-592">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-593">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-594">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-595">msRTCSIP-PolicyType（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p142">此单值 Unicode 字符串属性包含策略类型。有效策略类型如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-598">要求</span><span class="sxs-lookup"><span data-stu-id="0125a-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="0125a-599">电话</span><span class="sxs-lookup"><span data-stu-id="0125a-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-600">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-601">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="0125a-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="0125a-603">此属性指定指向计算机所属池的反向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="0125a-604">无论计算机运行的是标准版 Lync Server 还是企业版 Lync Server，都会设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="0125a-605">此属性标记为进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="0125a-606">有效值为池的域名。</span><span class="sxs-lookup"><span data-stu-id="0125a-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="0125a-607">正向链接：<strong>链接 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="0125a-608">此正向链接属性相应的反向链接为 <strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-609">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="0125a-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="0125a-611">这是一个多值属性，包含与 MCU 中心关联的池的可分辨名称 (DN) 的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="0125a-612">反向链接：<strong>链接 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="0125a-613">此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-614">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="0125a-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="0125a-616">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-617">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="0125a-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="0125a-p144">此属性指定管理控制台显示的池的任意名称。管理员可以更改此名称。</span><span class="sxs-lookup"><span data-stu-id="0125a-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="0125a-621">有效值为表示池名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0125a-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="0125a-622">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-p145">此属性为单值字符串值。如果管理员要创建的前端池的 FQDN 不符合从中创建该前端池的 Active Directory 域结构（例如 SIP 命名空间与域名系统 (DNS) 命名空间分离），则此属性的值（如果存在）表示该池的域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0125a-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="0125a-p146">我们建议将前端池域 FQDN 映射到该池所在的 Active Directory 域的域名部分。因此，当此属性中不存在值时，前端池 FQDN 将默认为 <strong>dnsHostName</strong> 属性所表示的 Active Directory 域名结构。</span><span class="sxs-lookup"><span data-stu-id="0125a-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="0125a-628">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="0125a-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="0125a-630">与池关联的所有 Lync Server、Enterprise Edition 服务器的域名的多值列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="0125a-631">此属性为整数类型，它定义池是否支持即时消息 (IM)、状态和会议。</span><span class="sxs-lookup"><span data-stu-id="0125a-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="0125a-632">可能的有效值类型如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-633">未定义：IM 和状态服务（Live Communications Server 2005 和 2003）</span><span class="sxs-lookup"><span data-stu-id="0125a-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="0125a-634">1： IM 和状态服务（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="0125a-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="0125a-635">2： IM 和状态和会议服务（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="0125a-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-636">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="0125a-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="0125a-p148">此属性指定服务器池运行的是 Standard Edition Server 还是 Enterprise Edition Server。此属性为整数类型的位掩码值。每个选项都由位表示。</span><span class="sxs-lookup"><span data-stu-id="0125a-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="0125a-641">此属性的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-642">1: Standard Edition Server，承载用户（第 0 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="0125a-643">2: Enterprise Edition Server，承载用户（第 1 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="0125a-644">4: Standard Edition Server，承载应用程序（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-645">8: Enterprise Edition Server，承载应用程序（第 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="0125a-646">由于 Lync Server 不支持仅托管应用程序的池，因此唯一有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="0125a-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-647">5: Standard Edition Server，承载用户和应用程序（第 0 和 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="0125a-648">10: Enterprise Edition Server，承载用户和应用程序（第 1 和 3 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-649">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="0125a-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="0125a-p149">此属性定义池版本。它为整数类型，在每次主要产品发布时递增。</span><span class="sxs-lookup"><span data-stu-id="0125a-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="0125a-653">可能的有效值类型如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-654">0： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="0125a-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="0125a-655">1： Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="0125a-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="0125a-656">2：使用 SP1 的 Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="0125a-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="0125a-657">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="0125a-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="0125a-658">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0125a-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="0125a-659">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0125a-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-660">使用 SP1 的 Live 通信服务器2005。</span><span class="sxs-lookup"><span data-stu-id="0125a-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="0125a-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="0125a-662">此属性包含用于定义状态设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="0125a-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="0125a-663">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="0125a-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="0125a-665">此属性包含状态策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="0125a-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="0125a-666">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="0125a-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="0125a-p150">此属性为用户或联系人启用 SIP 消息。它添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</span><span class="sxs-lookup"><span data-stu-id="0125a-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="0125a-670">有效值为用户所在 Standard Edition Server 或 Enterprise Edition 前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="0125a-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="0125a-671">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="0125a-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="0125a-673">此属性包含给定用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0125a-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="0125a-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="0125a-675">此属性包含专线设备的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="0125a-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="0125a-676">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-677">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="0125a-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="0125a-678">此属性是一个布尔属性，用于确定是否已授权 Lync Server 使用其 GRUU 地址路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="0125a-679">如果此值设置为<strong>TRUE</strong>，则表示已授权 Lync Server 路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="0125a-680">如果此值设置为<strong>FALSE</strong>，则 Lync Server 无权路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="0125a-681">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-682">msRTCSIP-RouteUsageAttribute（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p152">此单值 UNICODE 字符串属性定义限定电话路由用法的属性。电话路由的选择基于两个元素确定：一是分配给电话路由的用法属性，二是经允许的主叫方的策略用法属性。将选择用法属性与主叫方允许的用法相匹配的第一个电话路由。</span><span class="sxs-lookup"><span data-stu-id="0125a-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="0125a-686">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-687">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-688">msRTCSIP-RouteUsageLinks（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-689">此多值可分辨名称 (DN) 属性包含路由用法可分辨名称的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="0125a-690">正向链接：<strong>链接 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="0125a-691">此属性是反向链接 <strong>msRTCSIP-PhoneRouteBL</strong> 对应的正向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-692">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="0125a-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-694">此属性包含指向发往此 MCU 或受信任服务的所有 SIP 流量都必须通过的池的 DN。</span><span class="sxs-lookup"><span data-stu-id="0125a-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="0125a-695">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-696">msRTCSIP-RuleName（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-697">此单值 UNICODE 字符串属性指定规范化规则的友好名称，以方便管理员进行引用。</span><span class="sxs-lookup"><span data-stu-id="0125a-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="0125a-698">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-699">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="0125a-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="0125a-701">此属性表示组织中当前部署的架构版本。</span><span class="sxs-lookup"><span data-stu-id="0125a-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-702">msRTCSIP-SearchMaxRequests（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-703">此属性限制当用户使用 Communicator 搜索联系人时，要从目录搜索返回的搜索结果的数量。</span><span class="sxs-lookup"><span data-stu-id="0125a-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="0125a-704">此属性将覆盖客户端提供的值。</span><span class="sxs-lookup"><span data-stu-id="0125a-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="0125a-705">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-706">msRTCSIP-SearchMaxResults（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-707">此属性限制所返回的搜索请求数。</span><span class="sxs-lookup"><span data-stu-id="0125a-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="0125a-708">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="0125a-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="0125a-p154">此多值属性为包含可分辨名称 (DN) 列表的反向链接。这些 DN 指向池或 <strong>TrustedService</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="0125a-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="0125a-712">此属性对应于正向链接 <strong>msRTCSIP-TrustedServiceLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-713">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="0125a-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="0125a-715">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-716">msRTCSIP-ServerReferenceBL（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p155">此多值属性包含可分辨名称的列表。这些可分辨名称是引用可分配默认位置配置文件的其他服务器对象的反向链接。</span><span class="sxs-lookup"><span data-stu-id="0125a-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="0125a-719">反向链接：<strong>链接 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="0125a-720">此反向链接对应的正向链接为 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="0125a-721">此反向链接属性仅引用池和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0125a-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="0125a-722">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-723">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="0125a-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="0125a-p156">此属性定义服务器的版本信息。此版本号应用于所有服务器角色。它是一个单调递增的整数，并且随每一次正式产品发布而递增。</span><span class="sxs-lookup"><span data-stu-id="0125a-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="0125a-728">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-729">未定义： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="0125a-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="0125a-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="0125a-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="0125a-731">                 具有 SP1 的 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="0125a-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="0125a-732">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="0125a-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="0125a-733">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0125a-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="0125a-734">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0125a-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="0125a-735">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0125a-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-736">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="0125a-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="0125a-738">此整数类型的单值属性指定 <strong>msDS-SourceObjectDN</strong> 所指对象的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0125a-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-739">null | 0x00000001:表示来自另一个林的 Windows NT Server 主体用户对象</span><span class="sxs-lookup"><span data-stu-id="0125a-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="0125a-740">下面的属性表示来自另一个林的用于通讯组扩展的组类型：</span><span class="sxs-lookup"><span data-stu-id="0125a-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-741">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="0125a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="0125a-742">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="0125a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="0125a-743">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="0125a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="0125a-744">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="0125a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="0125a-745">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="0125a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="0125a-746">0x90000000：表示同一个林或另一个林中的自动助理或订阅者访问对象</span><span class="sxs-lookup"><span data-stu-id="0125a-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="0125a-747">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-748">msRTCSIP-SubscriptionAuthRequired（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-749">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="0125a-750">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="0125a-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="0125a-752">此属性使您可以将用户或联系人对象从一个 Lync Server 池移动到另一个池。</span><span class="sxs-lookup"><span data-stu-id="0125a-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="0125a-753">此属性添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</span><span class="sxs-lookup"><span data-stu-id="0125a-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="0125a-754">有效值为用户要移至的目标 Standard Edition Server 或前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="0125a-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="0125a-755">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-756">msRTCSIP-TargetPhoneNumber（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-757">此单值字符串属性包含要路由到 <strong>msRTCSIP-Gateways</strong> 中定义的指定网关的电话号码模式或范围。</span><span class="sxs-lookup"><span data-stu-id="0125a-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-758">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="0125a-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="0125a-760">此属性存储 Lync Server 用户的目标策略的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="0125a-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="0125a-761">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="0125a-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="0125a-763">此属性存储租户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0125a-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="0125a-764">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-765">msRTCSIP-Translation（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-766">如果找到匹配项，Lync Server 的语音功能将使用此属性，并且包含要应用于所拨号码的转换字符串。</span><span class="sxs-lookup"><span data-stu-id="0125a-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="0125a-767">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="0125a-768">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="0125a-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="0125a-770">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-771">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-p158">此属性是包含 MCU 的 FQDN 的字符串值。这是一个单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-776">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="0125a-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="0125a-778">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-779">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-p159">此属性是一个字符串值，其中包含运行代理服务器的服务器的 FQDN。此属性为单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-784">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="0125a-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="0125a-786">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-788">此属性是表示受信任服务器的 FQDN 的单值属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="0125a-789">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="0125a-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="0125a-791">此属性指定受信任服务器列表中的服务器的版本号。</span><span class="sxs-lookup"><span data-stu-id="0125a-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="0125a-792">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-793">NULL： Live 通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="0125a-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="0125a-794">2： Live 通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="0125a-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="0125a-795">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="0125a-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="0125a-796">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0125a-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="0125a-797">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0125a-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="0125a-798">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0125a-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-799">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="0125a-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="0125a-801">此属性定义为受信任的服务启用的选项。</span><span class="sxs-lookup"><span data-stu-id="0125a-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="0125a-802">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="0125a-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="0125a-804">此多值属性包含可分辨名称 (DN) 的列表，这些名称引用受信任的服务对象，如媒体中继身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="0125a-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="0125a-805">媒体中继身份验证服务（运行 A/V 会议服务的边缘服务器上的物理并置）必须与一个池相关联，以支持远程用户的音频方案。</span><span class="sxs-lookup"><span data-stu-id="0125a-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="0125a-806">此正向链接属性相应的反向链接为 <strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-807">全</span><span class="sxs-lookup"><span data-stu-id="0125a-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="0125a-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="0125a-809">此属性是一个整数，它定义用于连接到此 GRUU 服务的端口号。</span><span class="sxs-lookup"><span data-stu-id="0125a-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="0125a-810">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="0125a-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="0125a-812">此属性是一个字符串值，用于定义它所表示的 GRUU 服务的类型。</span><span class="sxs-lookup"><span data-stu-id="0125a-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="0125a-813">有效的 GRUU 服务类型如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0125a-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="0125a-815">网关</span><span class="sxs-lookup"><span data-stu-id="0125a-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="0125a-816">媒体中继身份验证服务 (MRAS)</span><span class="sxs-lookup"><span data-stu-id="0125a-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="0125a-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="0125a-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="0125a-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="0125a-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-819">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="0125a-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="0125a-821">此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-822">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="0125a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="0125a-824">此属性是一个字符串值，其中包含运行 Lync Server Web 服务的 IIS 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0125a-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="0125a-825">这是一个单值属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-825">This is a single-valued attribute.</span></span> <span data-ttu-id="0125a-826">每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0125a-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="0125a-827">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-828">msRTCSIP-UCFlags（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p162">此属性定义对所有用户或联系对象在全局范围启用的各种 UC 选项。此属性为整数类型的位掩码值。每个选项均由位表示。</span><span class="sxs-lookup"><span data-stu-id="0125a-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="0125a-832">此属性可能的有效值（和相关位的位置）如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-833">4: UsePerUserUCPolicy（第 2 位）</span><span class="sxs-lookup"><span data-stu-id="0125a-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="0125a-834">设置此位后，将按用户分别定义 UC 策略。</span><span class="sxs-lookup"><span data-stu-id="0125a-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="0125a-835">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-836">msRTCSIP-UCPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-837">此单值属性包含管理员已为此用户分配的 UC 策略的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="0125a-838">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-839">msRTCSIP-UserDomainList（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="0125a-p163">此属性提供林中承载启用 SIP 的用户的所有域的列表。默认为空列表，表示林中的所有域都已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="0125a-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="0125a-842">有效值为表示各个域的域名的多个字符串。</span><span class="sxs-lookup"><span data-stu-id="0125a-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="0125a-843">Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="0125a-844">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-845">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="0125a-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="0125a-846">此属性确定当前是否为 Lync Server 启用了用户。</span><span class="sxs-lookup"><span data-stu-id="0125a-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="0125a-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="0125a-848">此多值属性包含名称 = 值格式&quot;的名称-值对列表。&quot;此属性被标记为要进行全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="0125a-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="0125a-849">使用 SP1 的 Live 通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="0125a-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="0125a-851">此属性包含指向位置配置文件对象的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="0125a-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="0125a-852">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="0125a-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="0125a-854">此属性存储用户策略的名称值对。</span><span class="sxs-lookup"><span data-stu-id="0125a-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="0125a-855">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="0125a-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="0125a-p164">这是一个多值属性，包含带二进制值的可分辨名称 (DN_WITH_BINARY) 的列表，这些名称指向不同类型的全局用户策略。二进制值部分则指示 DN 部分所指向的策略的类型。</span><span class="sxs-lookup"><span data-stu-id="0125a-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="0125a-859">有效的二进制值如下：</span><span class="sxs-lookup"><span data-stu-id="0125a-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-860">0x00000001：会议策略</span><span class="sxs-lookup"><span data-stu-id="0125a-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="0125a-861">0x00000002：UC 策略</span><span class="sxs-lookup"><span data-stu-id="0125a-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="0125a-862">0x00000005：状态策略</span><span class="sxs-lookup"><span data-stu-id="0125a-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-863">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="0125a-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="0125a-p165">这是 SIP 路由组 ID。相同组中的用户将注册到相同的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="0125a-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="0125a-867">Lync Server 2013 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="0125a-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="0125a-p166">这是一个多值属性。此属性留作将来使用。</span><span class="sxs-lookup"><span data-stu-id="0125a-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="0125a-871">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="0125a-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="0125a-873">此单值属性指向 Web 组件所属的池或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="0125a-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="0125a-874">正向链接：<strong>链接 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="0125a-875">此正向链接属性相应的反向链接为 <strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-876">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="0125a-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="0125a-p167">此属性为可分辨名称的多值列表。此属性包含与此池关联的所有 Web 服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="0125a-880">反向链接：<strong>链接 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="0125a-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="0125a-881">此反向链接相应的正向链接为 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="0125a-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="0125a-882">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-883">msRTCSIP-WMIInstanceId（作废）</span><span class="sxs-lookup"><span data-stu-id="0125a-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0125a-884">Live 通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="0125a-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="0125a-885">在 Live 通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="0125a-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="0125a-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="0125a-887">电话使用此现有 Active Directory 属性指定电话的备用 TCP/IP 地址列表。</span><span class="sxs-lookup"><span data-stu-id="0125a-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="0125a-888">Windows Server 2008 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="0125a-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="0125a-890">Lync Server 中的语音组件使用此现有 Active Directory 属性，仅用于联系人对象，用于将呼叫路由到统一消息自动助理和订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="0125a-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="0125a-891">无条件呼叫转移地址存储在此多值属性中。</span><span class="sxs-lookup"><span data-stu-id="0125a-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="0125a-892">此帐户专为自动助理和订阅者访问的特定用途而创建。</span><span class="sxs-lookup"><span data-stu-id="0125a-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="0125a-893">管理员不应修改此帐户的属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="0125a-894">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0125a-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0125a-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="0125a-896">此现有 Active Directory 多值属性是 Windows 2000 中引入的基本 Active Directory 架构的一部分。</span><span class="sxs-lookup"><span data-stu-id="0125a-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="0125a-897">此属性包含用户电子邮件的各种 X400、X500 和 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0125a-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="0125a-898">在 Live 通信服务器2003及更高版本中，将使用&quot;sip：&quot;标记将用户的 SIP URI 添加到此列表中。</span><span class="sxs-lookup"><span data-stu-id="0125a-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="0125a-899">下列应用程序从此属性搜索用户的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="0125a-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="0125a-900">Microsoft Office Outlook 2003 消息和协作客户端</span><span class="sxs-lookup"><span data-stu-id="0125a-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="0125a-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="0125a-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0125a-902">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0125a-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="0125a-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="0125a-904">此现有 Active Directory 属性包含用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0125a-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="0125a-905">Windows 2000 操作系统中的新增属性。</span><span class="sxs-lookup"><span data-stu-id="0125a-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

