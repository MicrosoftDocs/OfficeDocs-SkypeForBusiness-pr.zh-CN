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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="6eb9d-102">Lync Server 2013 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="6eb9d-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eb9d-103">_**主题上次修改时间：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6eb9d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6eb9d-104">本部分介绍 Lync Server 2013 使用的所有架构属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="6eb9d-105">对于与属性相关联的类，请参阅[Lync Server 2013 中的 "按类架构属性](lync-server-2013-schema-attributes-by-class.md)"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="6eb9d-106">有关 Lync Server 2013 中新增的类和属性的列表，请参阅[Lync server 2013 中的架构更改](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="6eb9d-107">链接对的属性指定为 "前进链接" 或 "反向链接"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="6eb9d-108">引用另一个对象的属性是前向链接;引用第一个对象的其他对象的属性是 "后退" 链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="6eb9d-109">正向链接是可更新的，而反向链接是只读的。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="6eb9d-110">某些属性具有位掩码值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="6eb9d-111">对于这些属性，每个设置都由一个位表示，显示的十进制值表示位位置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="6eb9d-112">位位置从位0开始。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="6eb9d-113">例如，1（binary）是位0集，10000（二进制）是位4设置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="6eb9d-114">每个位表示一个属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-114">Each bit represents a property.</span></span> <span data-ttu-id="6eb9d-115">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-115">The following are some examples:</span></span>

  - <span data-ttu-id="6eb9d-116">10000（binary）具有十进制值16（即设置了位4）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="6eb9d-117">100000000（binary）的十进制值为256（即，设置了位8）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="6eb9d-118">1100（binary）具有十进制值12（即，第2位和第3位）; 已启用两位数字表示的属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="6eb9d-119">1111000001（binary）的十进制值为961（即位0、6、7、8和9）; 每个位的属性均已启用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="6eb9d-120">Lync Server 2013 的架构属性</span><span class="sxs-lookup"><span data-stu-id="6eb9d-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb9d-121">属性</span><span class="sxs-lookup"><span data-stu-id="6eb9d-121">Attribute</span></span></th>
<th><span data-ttu-id="6eb9d-122">描述</span><span class="sxs-lookup"><span data-stu-id="6eb9d-122">Description</span></span></th>
<th><span data-ttu-id="6eb9d-123">备注</span><span class="sxs-lookup"><span data-stu-id="6eb9d-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="6eb9d-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-125">Active Directory 域服务中现与<strong>msRTCSIP</strong>和<strong>msRTCSIP</strong>类相关联的现有属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="6eb9d-126">此属性指定池或监视服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="6eb9d-127">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-128">Microsoft Office Live 通信服务器2005中的新增新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-129">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-130">此属性包含另一个林中与此对象对应的对象的可分辨名称（DN）的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="6eb9d-131">此属性用于通讯组扩展和自动出席。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="6eb9d-132">此属性在 Windows Server 2003 R2 的默认 Active Directory 架构中定义。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="6eb9d-133">为避免需要将 AD DS 升级到 Windows Server 2003 R2，Active Directory 架构准备使用此属性定义扩展了 Windows Server 2003 架构。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-134">Microsoft Office 通信服务器2007中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="6eb9d-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-136">此多值属性包含语音邮件设置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="6eb9d-137">此属性与 Exchange 统一消息（UM）共享。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-138">Microsoft Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6eb9d-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-140">此多值属性包含适用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="6eb9d-141">保留策略在保留期间保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="6eb9d-142">此属性是与 Exchange 2013 共享的。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-143">Lync Server 2013 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="6eb9d-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-145">此属性存储用户的音频会议提供商信息。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-146">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="6eb9d-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-148">此属性指向应用程序联系人的受信任服务条目。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-149">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="6eb9d-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-151">此属性包含应用服务器上托管应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-152">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="6eb9d-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-154">此属性指定应用程序联系人的选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-155">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="6eb9d-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-157">此属性包含应用程序联系人的主要语言。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-158">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="6eb9d-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-160">此多值属性包含应用程序联系人的辅助语言。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-161">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="6eb9d-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-163">此属性包含属于此池的应用程序服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="6eb9d-164">指向此 back link 属性的相应正向链接是<strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-165">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="6eb9d-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-167">此属性指向应用服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="6eb9d-168">这是 "转发" 链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-168">This is the forward link.</span></span> <span data-ttu-id="6eb9d-169">相应的反向链接为<strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-170">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-171">msRTCSIP-ArchiveDefault （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-172">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-173">Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-174">msRTCSIP-ArchiveDefaultFlags （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-175">此属性指定林边界内用于存档所有用户通信的全局默认值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="6eb9d-176">这由存档代理层强制执行。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="6eb9d-177">此属性的值范围如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-178"><strong>TRUE</strong>：对所有用户进行存档</span><span class="sxs-lookup"><span data-stu-id="6eb9d-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-179"><strong>FALSE</strong>：不存档所有用户</span><span class="sxs-lookup"><span data-stu-id="6eb9d-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="6eb9d-180">此属性在林边界内对内部网络内的用户通信的存档方式进行全局控制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="6eb9d-181"><strong>实时通信服务器2005行为（现已停用）</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="6eb9d-182">此属性的值范围如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-183">0：将邮件正文存档 [位 0]</span><span class="sxs-lookup"><span data-stu-id="6eb9d-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-184">1：不存档邮件正文 [位 0]</span><span class="sxs-lookup"><span data-stu-id="6eb9d-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="6eb9d-185"><strong>Office 通信服务器2007行为</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="6eb9d-186">此属性的值范围如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-187">0： ArchiveFederationDefaultWithoutBody （已停用）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-188">1-2： ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="6eb9d-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-189">3-4： ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="6eb9d-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-190">5： RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="6eb9d-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-191">6： RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-192">7： RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-193">8： RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="6eb9d-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-194">9： RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-195">10： RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-196">11： RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-197">12： RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="6eb9d-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-198">13： RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="6eb9d-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-199">14： RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="6eb9d-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-200">15： RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="6eb9d-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-201">16： RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="6eb9d-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-202">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-203">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-204">msRTCSIP-ArchiveFederationDefault （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-205">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-206">Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-207">msRTCSIP-ArchiveFederationDefaultFlags （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-208">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-209">Office 通信服务器2007中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="6eb9d-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-211">此属性是一个整数，用作位域，用于控制是否要存档单个用户的通信。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="6eb9d-212">此控件由存档代理层强制执行。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="6eb9d-213">它标记为用于全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-214">此属性的范围特定于单个用户或联系人。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="6eb9d-215">Lync Server 中的有效值（和关联的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-216">0：不存档（无位集）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-217">1：已停用（位位置0）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-218">2：已停用（位位置1）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-219">4：存档内部通信（位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-220">8：存档联合通信（位位置3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="6eb9d-221">实时通信服务器2005中以前的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-222">0：使用<strong>msRTCSIP-ArchiveDefault</strong>和<strong>msRTCSIP-ArchiveFederation</strong>定义的默认值，按优先级顺序排列：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-223">1：存档</span><span class="sxs-lookup"><span data-stu-id="6eb9d-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-224">2：不存档</span><span class="sxs-lookup"><span data-stu-id="6eb9d-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-225">3：存档但不包含邮件正文</span><span class="sxs-lookup"><span data-stu-id="6eb9d-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-226">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-227">msRTCSIP-ArchivingServerData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-228">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-229">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-230">msRTCSIP-ArchivingServerVersion （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-231">此属性定义存档服务的版本。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="6eb9d-232">此属性是与每个正式产品版本递增的 monotonously 增加的整数类型。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="6eb9d-233">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-234">未定义：实时通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="6eb9d-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6eb9d-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6eb9d-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="6eb9d-236">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6eb9d-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-237">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="6eb9d-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-238">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6eb9d-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-239">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-240">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-242">此属性指定池后端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="6eb9d-243">由于每个池中只能有一个后端服务器，这是单值属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="6eb9d-244">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-245">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="6eb9d-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-247">此属性包含托管会议目录的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-248">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="6eb9d-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-250">此属性包含会议目录的标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-251">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="6eb9d-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-253">此属性包含要将会议目录移动到的池的标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-254">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-255">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="6eb9d-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-256">此布尔属性定义电话使用情况是否为默认用法。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="6eb9d-257">如果此属性设置为<strong>TRUE</strong>，则电话使用是默认用法，并且不能由管理员删除。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="6eb9d-258">如果此属性设置为<strong>FALSE</strong>，则可以删除用法。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-259">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="6eb9d-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-261">此属性标识组织外部用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-262">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="6eb9d-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-264">此属性标识组织内部用户的 Communicator Web 访问 URL。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-265">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-266">msRTCSIP-DefaultLocationProfileLink （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-267">此单值属性包含分配给它的位置配置文件类对象的识别名（DN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="6eb9d-268">转发链接：<strong>链接 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="6eb9d-269">相应的反向链接为<strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-270">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-271">msRTCSIP-DefaultPolicy （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-272">此布尔属性指定策略是否为默认策略。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="6eb9d-273">策略是设置为<strong>TRUE</strong>时的默认策略。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-274">Office 通信服务器2007中的新增</span><span class="sxs-lookup"><span data-stu-id="6eb9d-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="6eb9d-275">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-276">msRTCSIP-DefaultRouteToEdgeProxy （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-277">此属性指定运行访问边缘服务的边缘服务器的 FQDN （如果可直接访问），或者指定运行 Access Edge 服务的服务器池的硬件负载平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="6eb9d-278">如果运行 Access Edge 服务的服务器只能通过一个或多个控制器访问，则此属性指定 FQDN 和（可选）为控制器池提供服务的控制器或硬件负载平衡器的端口号。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="6eb9d-279">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-280">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-281">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-282">msRTCSIP-DefaultRouteToEdgeProxyPort （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-283">此属性表示应用于连接到运行 Access Edge 服务的服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="6eb9d-284">有效值是指定要使用的端口的整数值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="6eb9d-285">默认值为5061。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-286">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-287">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-288">msRTCSIP-DefPresenceSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-289">此属性表示默认状态订阅的超时期限。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-290">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-291">msRTCSIP-DefRegistrationTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-292">此属性表示默认的注册超时窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-293">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-294">msRTCSIP-DefRoamingDataSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-295">此属性表示默认的漫游数据订阅超时窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-296">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="6eb9d-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-298">此属性在拆分的域拓扑中使用，并且包含完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-299">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-300">msRTCSIP-说明（已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-301">此单值 UNICODE 字符串属性包含此电话路由或规范化规则的友好描述。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-302">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-303">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-305">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-306">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="6eb9d-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-307">此属性表示为注册机构配置的域。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-309">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-310">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-312">此属性指定运行访问边缘服务的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="6eb9d-313">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-314">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-315">msRTCSIP-EnableBestEffortNotify （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-316">此属性控制服务器是否生成最佳操作通知（BENOTIFY）请求（而不是通知请求）以响应来自客户端的订阅请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="6eb9d-317">BENOTIFY 是对订阅通知握手的性能增强扩展，服务器将生成 BENOTIFY 请求，而不是常规通知请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="6eb9d-318">性能好处是 BENOTIFY 请求不需要来自客户端的 200 OK 响应，因为通知请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="6eb9d-319">有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6eb9d-320">实时通信服务器2003不支持 BENOTIFY 请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="6eb9d-321">若要与在实时通信服务器2005和第三方服务器上运行的实时通信2003服务器 API 编写的服务器应用程序互操作，可通过将 BENOTIFY 请求的值设置为<STRONG>FALSE</STRONG>来禁用这些请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="6eb9d-322">BENOTIFY 当前不是 IETF （Internet 工程任务组） SIP 标准化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="6eb9d-323">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-324">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-325">msRTCSIP-EnableFederation （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-326">此属性是一个全局开关，IT 管理员使用它配置用户是否可以与其他组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="6eb9d-327">它使管理员能够覆盖单个用户的<strong>FederationEnabled</strong>属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="6eb9d-328">此属性可用于帮助保护内部网络免受受蠕虫、病毒或公司的目标攻击导致的网络攻击。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="6eb9d-329">有效值（及相关位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-330">1：已启用公用 IM 连接（位位置0）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-331">2：保留（位位置1）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-332">4：保留（位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-333">8：保留（位位置3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-334">16：启用远程呼叫控制 [电话] （位位置4）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-335">64： AllowOrganizeMeetingWithAnonymousParticipants （允许用户邀请匿名用户加入会议（位位置6）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-336">128： UCEnabled （启用统一通信的用户）（位位置7）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-337">256： EnabledForEnhancedPresence （启用公用 IM 连接的用户）（bit 位置8）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-338">512： RemoteCallControlDualMode （位位置9）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-339">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-340">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="6eb9d-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-342">此属性指示是否已在给定服务器上加载企业服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-344">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="6eb9d-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-346">此属性包含用于外部访问的拨号代码。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-347">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="6eb9d-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-349">此属性控制是否为单个用户启用联盟。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="6eb9d-350">它由企业服务层强制执行。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="6eb9d-351">它标记为用于全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-352">有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-353">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="6eb9d-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-355">此属性是与池关联的所有企业版服务器的域名的多值列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="6eb9d-356">反向链接：<strong>链接 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="6eb9d-357">指向此 back 链接的相应正向链接是<strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-358">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-359">msRTCSIP-网关（已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-360">此多值字符串属性包含网关和端口（每个网关）的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-361">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-362">msRTCSIP-GlobalSettingsData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-363">此属性存储 "名称：值" 对。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="6eb9d-364">已定义的名称：值对用于 "<strong>允许轮询状态</strong>" 设置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-365">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="6eb9d-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-367">此属性是用于分组通讯簿条目的组的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-368">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-369">msRTCSIP-HomeServer （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-370">实时通信服务器2003中的新增服务（未使用）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="6eb9d-371">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-372">msRTCSIP-HomeServerString （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-373">实时通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6eb9d-374">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-375">msRTCSIP-HomeUsers （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-376">实时通信服务器2003中的新增服务（未使用）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="6eb9d-377">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="6eb9d-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-379">此属性控制是否为单个用户启用外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="6eb9d-380">它由企业服务层强制执行。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="6eb9d-381">它标记为用于全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-382">有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-383">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-384">msRTCSIP-IsMaster （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-385">实时通信服务器2003中的新增</span><span class="sxs-lookup"><span data-stu-id="6eb9d-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6eb9d-386">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-387">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="6eb9d-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-388">此单值属性包含 Lync 用于电话服务的设备 ID （用户控制的电话的 SIP URI 或电话 URI）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="6eb9d-389">此属性标记为 "全局编录复制"，并且已编制索引。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="6eb9d-390">如果用户已启用企业语音，此属性将存储标准化的用户电话号码版本。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-391">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="6eb9d-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-393">此单值属性包含 CSTA 的 sip 网关服务器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="6eb9d-394">此属性标记为全局编录复制，但未编入索引。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-395">Microsoft Office Live 通信服务器2005中的新增 SP1</span><span class="sxs-lookup"><span data-stu-id="6eb9d-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-396">msRTCSIP-LocalNormalizationData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-397">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-398">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-399">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-400">msRTCSIP-LocalNormalizationLinks （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-401">此多值属性包含与此位置配置文件关联的本地规范化可分辨名称（DN）的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="6eb9d-402">此属性的类型是 DN 二进制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="6eb9d-403">位置配置文件与本地规范化规则之间存在一对多关系。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="6eb9d-404">本地规范化 DNs 列表的顺序必须按管理员指定的顺序进行维护。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="6eb9d-405">顺序保留由 DN 二进制部分的二进制部分进行维护，该二进制部分指定订单索引。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="6eb9d-406">转发链接：<strong>链接 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="6eb9d-407">此前向链接属性的对应反向链接是<strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-408">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-409">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="6eb9d-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-411">此属性包含规范化规则的选项列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-412">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-413">msRTCSIP-LocationName （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-414">此单值属性包含位置配置文件的友好名称，用于指示此配置文件所代表的位置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="6eb9d-415">由于可以有多个位置配置文件，因此管理员需要一种方式来区分不同的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-416">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-417">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-418">msRTCSIP-locationProfileBL （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-419">此多值属性包含位置配置文件的可分辨名称的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="6eb9d-420">此属性指定指向一个或多个位置配置文件的反向链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="6eb9d-421">反向链接：<strong>链接 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="6eb9d-422">此属性对应于<strong>msRTCSIP-LocalNormalizationLinks</strong>的前进链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-423">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-424">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-425">msRTCSIP-LocationProfileData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-426">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-427">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-428">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="6eb9d-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-430">此属性包含位置配置文件的选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-431">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="6eb9d-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-433">此多值属性包含应用程序联系人列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-434">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="6eb9d-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-436">此多值属性包含位置配置文件的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-437">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-438">msRTCSIP-MaxNumOutstandingSearchPerServer （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-439">此属性表示每台服务器的未完成搜索请求的最大数量。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-440">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-441">msRTCSIP-MaxNumSubscriptionsPerUser （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-442">该属性表示每个用户的最大订阅数。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-443">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-444">msRTCSIP-MaxPresenceSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-445">此属性表示最长订阅超时时间窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-446">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-447">msRTCSIP-MaxRegistrationsTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-448">此属性表示最大注册超时时段。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-449">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-451">此属性表示 "漫游数据订阅最大超时" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-452">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-454">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-455">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="6eb9d-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-457">此属性是计算机类下的服务控制点属性，用于指定返回到其所属 multipoint control 单元（MCU）工厂的链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="6eb9d-458">将为每个 Microsoft MCU 创建此服务控制点和属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="6eb9d-459">每个 Microsoft MCU 都必须找到其所属池的后端服务器，才能从中检索池级别的设置。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="6eb9d-460">此属性的值是 MCU 工厂的可分辨名称（DN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="6eb9d-461">这是单值属性，并标记为用于全局编录复制。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-462">转发链接：<strong>链接 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="6eb9d-463">此前向链接属性的对应反向链接是<strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-464">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-466">这是一个多字符串保留属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="6eb9d-467">存储在此属性中的设置表示为 name = value 对。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="6eb9d-468">当前定义的 name = value 对：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="6eb9d-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-470">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="6eb9d-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-472">这是一个单值属性，包含与池关联的单个 MCU 工厂的识别名（DN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="6eb9d-473">转发链接：<strong>链接 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="6eb9d-474">此前向链接属性的对应反向链接是<strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-475">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="6eb9d-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-477">此属性是一个单值字符串，用于指定 MCU 工厂提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="6eb9d-478">根据 GUID 值，MCU 工厂进程确定是否为此 MCU 类型服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="6eb9d-479">如果 GUID 值为<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，则 MCU 工厂进程（默认情况下在 Lync Server 中可用）将处理它。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="6eb9d-480">对于任何其他 GUID 值，MCU 工厂进程将不会为 MCU 类型提供服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-481">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="6eb9d-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-483">此属性是可分辨名称（DN）的多值列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="6eb9d-484">此属性包含与此 MCU 工厂关联的同一类型和供应商的所有 MCU 服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="6eb9d-485">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="6eb9d-486">反向链接：链接 ID 11027</span><span class="sxs-lookup"><span data-stu-id="6eb9d-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="6eb9d-487">指向此 back 链接的相应正向链接是<strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-488">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="6eb9d-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-490">此属性是一个单值字符串，用于指定 MCU 可以处理的媒介。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="6eb9d-491">受支持的有效类型包括：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-492">符合</span><span class="sxs-lookup"><span data-stu-id="6eb9d-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-493">音频视频</span><span class="sxs-lookup"><span data-stu-id="6eb9d-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-494">聊天</span><span class="sxs-lookup"><span data-stu-id="6eb9d-494">chat</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-495">电话会议</span><span class="sxs-lookup"><span data-stu-id="6eb9d-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-496">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="6eb9d-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-498">此属性是一个单值字符串，用于指定 MCU 供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="6eb9d-499">所有 Microsoft MCUs 都将此属性指定为<strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-500">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-501">msRTCSIP-MeetingFlags （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-502">此属性定义为所有用户或联系人对象全局启用的不同会议选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="6eb9d-503">此属性是整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="6eb9d-504">有效值（及相关位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-505">0： AllowOrganizeMeetingWithAnonymousParticipants 为 None （不允许用户邀请匿名用户加入会议）（未设置 bits）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-506">4： AllowOrganizeMeetingWithAnonymousParticipants 是每个人（允许所有用户邀请匿名用户加入会议）（位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-507">8： AllowOrganizeMeetingWithAnonymousParticipants 为 UsePerUserSetting （允许用户基于每个用户设置邀请匿名用户加入会议）（位位置3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-508">16： UserPerUserMeetingPolicy （会议策略按用户定义）（位位置4）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-509">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-510">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-511">msRTCSIP-MeetingPolicy （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-512">此属性指定管理员为此用户分配的策略的可分辨名称（DN）作为单值属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-513">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-514">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-515">msRTCSIP-MinPresenceSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-516">此属性表示最小联机状态订阅超时窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-517">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-518">msRTCSIP-MinRegistrationTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-519">此属性表示最小的注册超时窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-520">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-521">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-522">msRTCSIP-MinRoamingDataSubscriptionTimeout （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-523">此属性表示最少的漫游数据订阅超时窗口。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-524">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-525">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-527">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-528">Lync Server 2013 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="6eb9d-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-530">此属性包含用于定义移动设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-531">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="6eb9d-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-533">此属性包含移动策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-534">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-535">msRTCSIP-NumDevicesPerUser （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-536">此属性表示用户可以注册 SIP 通信和订阅状态的允许的设备数。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-537">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-538">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="6eb9d-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-540">此属性指定为用户或联系人对象启用的选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="6eb9d-541">此属性是整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="6eb9d-542">每个选项表示一个位。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-542">Each option is represented by a bit.</span></span> <span data-ttu-id="6eb9d-543">此属性标记为 "全局编录复制"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-544">有效值（及相关位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-545">1：已启用公共即时消息（IM）连接（位位置0）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-546">2：保留（位位置1）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-547">4：保留（位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-548">8：保留（位位置3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-549">16：启用远程呼叫控制 [电话] （位位置4）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-550">64： AllowOrganizeMeetingWithAnonymousParticipants （允许用户邀请匿名用户加入会议（位位置6）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-551">128： UCEnabled （启用 UC 的用户）（位位置7）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-552">256： EnabledForEnhancedPresence （启用公用 IM 连接的用户）（bit 位置8）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-553">512： RemoteCallControlDualMode （位位置9）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-554">SP1 的实时通信服务器2005中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="6eb9d-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-556">当从 Windows NT 服务器主体帐户中的用户的 ObjectSID 复制到资源或中央林中的相应用户或联系人对象的此属性时，在资源和中央林拓扑中使用此属性可启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="6eb9d-557">Communicator Web Access 使用此属性或用户的 ObjectSID 在 AD DS 中搜索用户。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="6eb9d-558">此属性标记为 "全局编录复制"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="6eb9d-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-560">此属性是应用程序联系人的所有者的统一资源名称（URN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-561">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-562">msRTCSIP 模式（已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-563">此单值字符串属性包含用于将拨号号码匹配到164格式的模式。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="6eb9d-564">如果拨号号码与此模式匹配，则转换将应用于已拨号码。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-565">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-566">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-567">msRTCSIP-PhoneRouteBL （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-568">此多值属性包含一个电话路由可分辨名称（DN）的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="6eb9d-569">此属性指定指向一个或多个电话路由的反向链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="6eb9d-570">反向链接：<strong>链接 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="6eb9d-571">此属性对应于<strong>msRTCSIP-RouteUsageLinks</strong>的前进链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-572">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-573">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-574">msRTCSIP-PhoneRouteData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-575">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-576">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-577">msRTCSIP-PhoneRouteName （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-578">此单值 UNICODE 字符串属性指定手机路由的友好名称，以便管理员可以轻松地引用它。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-579">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-580">msRTCSIP-PhoneUsageData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-581">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-582">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-583">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-584">msRTCSIP-PolicyContent （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-585">此属性是一个单值的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="6eb9d-586">此字符串属性包含 XML 格式的策略定义。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="6eb9d-587">XML 架构定义在不同的策略类型中是通用的，对于每个策略类型，仅这些设置是不同的。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="6eb9d-588">XML 架构定义（XSD）的定义如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="6eb9d-589">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-590">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-591">msRTCSIP-PolicyData （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-592">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-593">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-594">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-595">msRTCSIP-PolicyType （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-596">此单值 Unicode 字符串属性包含策略类型。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="6eb9d-597">有效的策略类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-598">符合</span><span class="sxs-lookup"><span data-stu-id="6eb9d-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-599">电话</span><span class="sxs-lookup"><span data-stu-id="6eb9d-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-600">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-601">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="6eb9d-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-603">此属性指定一个链接，该链接返回到计算机所属的池。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="6eb9d-604">无论计算机运行的是标准版 Lync Server 还是企业版 Lync Server，均会设置此属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="6eb9d-605">此属性标记为 "全局编录复制"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6eb9d-606">有效的值是池的域名。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="6eb9d-607">转发链接：<strong>链接 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="6eb9d-608">此前向链接属性的对应反向链接是<strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-609">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="6eb9d-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-611">这是一个多值属性，其中包含与 MCU 工厂关联的池的可分辨名称（DN）列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="6eb9d-612">反向链接：<strong>链接 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="6eb9d-613">指向此 back 链接的相应正向链接是<strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-614">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-616">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-617">SP1 的实时通信服务器2005中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="6eb9d-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-619">此属性为管理控制台显示的池指定任意名称。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="6eb9d-620">管理员可以更改此名称。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="6eb9d-621">有效值是表示池名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-622">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-624">此属性是单值字符串值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="6eb9d-625">此属性的值（如果存在）表示池的域 FQDN （如果管理员希望使用不符合在其中创建前端池的 Active Directory 域结构的 FQDN 创建前端池）（例如，SIP从域名系统（DNS）命名空间中脱离命名空间。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="6eb9d-626">我们建议你将前端池域 FQDN 映射到域名部分，作为池所在的 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="6eb9d-627">因此，当此属性中不存在值时，前端池 FQDN 将默认为 Active Directory 域名结构，由<strong>dnsHostName</strong>属性表示。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-628">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="6eb9d-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-630">与池关联的所有 Lync Server、企业版服务器的域名的多值列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="6eb9d-631">Type integer 的此属性定义池是否支持即时消息（IM）和状态以及会议。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="6eb9d-632">可能有效的值类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-633">未定义：即时消息和状态服务（实时通信服务器2005和2003）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-634">1：即时消息和状态服务（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-635">2：即时消息和状态和会议服务（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-636">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="6eb9d-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-638">此属性指定服务器池是否正在运行标准版服务器或企业版服务器。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="6eb9d-639">此属性是整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="6eb9d-640">每个选项表示一个位。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="6eb9d-641">有效值（及相关位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-642">1：标准版服务器，托管用户（位位置0）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-643">2：企业版服务器，托管用户（位位置1）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-644">4：标准版服务器，托管应用程序（位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-645">8：企业版服务器，托管应用程序（位位置3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="6eb9d-646">由于 Lync Server 不支持仅托管应用程序的池，因此唯一有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-647">5：标准版服务器、托管用户和应用程序（位位置0和2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-648">10：企业版服务器、托管用户和应用程序（位位置1和3）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-649">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="6eb9d-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-651">此属性定义池版本。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-651">This attribute defines the pool version.</span></span> <span data-ttu-id="6eb9d-652">它是一种与每个主要产品发布递增的整数类型。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="6eb9d-653">可能有效的值类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-654">0：实时通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="6eb9d-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-655">1：实时通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="6eb9d-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-656">2：实时通信服务器2005与 SP1</span><span class="sxs-lookup"><span data-stu-id="6eb9d-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-657">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="6eb9d-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-658">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6eb9d-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-659">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6eb9d-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-660">带有 SP1 的实时通信服务器2005。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="6eb9d-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-662">此属性包含用于定义联机状态设置的选项和标志。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-663">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="6eb9d-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-665">此属性包含状态策略对象的 DN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-666">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-668">此属性启用 SIP 消息的用户或联系人。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="6eb9d-669">它将添加到 contact 类，因为在中央林拓扑中，联系人对象（而不是用户对象）已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="6eb9d-670">有效值是用户托管的标准版服务器或企业版前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-671">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="6eb9d-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-673">此属性包含给定用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="6eb9d-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-675">此属性包含专用线路设备的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-676">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-677">msRTCSIP-可路由</span><span class="sxs-lookup"><span data-stu-id="6eb9d-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-678">此属性是一个布尔属性，用于确定是否授权 Lync 服务器使用其 GRUU 地址路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="6eb9d-679">如果此值设置为<strong>TRUE</strong>，则 Lync Server 有权路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="6eb9d-680">如果此值设置为<strong>FALSE</strong>，则 Lync Server 无权路由到此服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-681">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-682">msRTCSIP-RouteUsageAttribute （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-683">此单值 UNICODE 字符串属性定义了限定手机路由使用的属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="6eb9d-684">根据两个元素确定手机路线的选择：分配给电话路线的使用属性和呼叫者允许的策略使用情况属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="6eb9d-685">已选中与呼叫者允许的使用相匹配的第一条电话路由和使用情况属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-686">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-687">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-688">msRTCSIP-RouteUsageLinks （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-689">此多值可分辨名称（DN）属性包含路由使用可分辨名称的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="6eb9d-690">转发链接：<strong>链接 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="6eb9d-691">此属性是指向对应的 back link <strong>msRTCSIP-PhoneRouteBL</strong>的前向链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-692">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-694">此属性包含指向所有寻址到此 MCU 或受信任服务的 SIP 流量必须经过的池的 DN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-695">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-696">msRTCSIP-RuleName （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-697">此单值 UNICODE 字符串属性指定规范化规则的友好名称，因此它可以由管理员轻松引用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-698">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-699">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="6eb9d-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-701">此属性表示组织中当前部署的架构版本。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-702">msRTCSIP-SearchMaxRequests （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-703">此属性限制当用户使用 Communicator 搜索联系人时，将从目录搜索返回的搜索结果的数量。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="6eb9d-704">此属性将替代客户端提供的值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-705">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-706">msRTCSIP-SearchMaxResults （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-707">此属性限制返回的搜索请求数。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-708">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="6eb9d-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-710">此多值属性是一个后退链接，其中包含可分辨名称（DN）的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="6eb9d-711">这些 DNs 指向一个 pool 或<strong>TrustedService</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="6eb9d-712">此属性对应于<strong>msRTCSIP-TrustedServiceLinks</strong>的前进链接。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-713">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-715">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-716">msRTCSIP-ServerReferenceBL （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-717">此多值属性包含一个可分辨名称的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="6eb9d-718">这些可分辨名称是反向链接，这些链接引用可以为其分配默认位置配置文件的其他服务器对象。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="6eb9d-719">反向链接：<strong>链接 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="6eb9d-720">指向此 back 链接的相应正向链接是<strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="6eb9d-721">此 back link 属性仅引用池和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-722">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-723">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="6eb9d-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-725">此属性定义服务器的版本信息。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="6eb9d-726">此版本号适用于所有服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-726">This version number applies to all server roles.</span></span> <span data-ttu-id="6eb9d-727">这是一个 monotonously 增加的整数，每个官方产品版本增加。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="6eb9d-728">可能的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-729">未定义：实时通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="6eb9d-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6eb9d-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6eb9d-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="6eb9d-731">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6eb9d-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-732">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="6eb9d-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-733">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6eb9d-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-734">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6eb9d-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-735">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb9d-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-736">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="6eb9d-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-738">Integer 类型的此单值属性指定<strong>SourceObjectDN</strong>指向的对象的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-739">null |0x00000001：表示来自不同林中的 Windows NT 服务器主体用户对象</span><span class="sxs-lookup"><span data-stu-id="6eb9d-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-740">以下属性表示通讯组扩展来自不同林中的组类型：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-741">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6eb9d-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-742">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6eb9d-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-743">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6eb9d-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-744">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6eb9d-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-745">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="6eb9d-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-746">0x90000000：表示来自同一林或不同林中的自动助理或订阅者访问对象</span><span class="sxs-lookup"><span data-stu-id="6eb9d-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-747">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-748">msRTCSIP-SubscriptionAuthRequired （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-749">实时通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6eb9d-750">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-752">此属性使你能够将用户或联系人对象从一个 Lync 服务器池移动到另一个。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="6eb9d-753">此属性将添加到 contact 类，因为在中央林拓扑中，联系人对象（而不是用户对象）已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="6eb9d-754">有效值是要将用户移动到的目标标准版服务器或前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-755">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-756">msRTCSIP-TargetPhoneNumber （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-757">此单值字符串属性包含用于路由到在<strong>msRTCSIP-网关</strong>定义的指定网关的电话号码模式或范围。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-758">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="6eb9d-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-760">此属性存储 Lync Server 用户的目标策略的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-761">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="6eb9d-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-763">此属性存储租户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-764">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-765">msRTCSIP-翻译（已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-766">此属性由 Lync Server 的语音功能使用，并且包含要在已拨号码上应用的翻译字符串（如果找到匹配项）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-767">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6eb9d-768">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-770">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-771">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-773">此属性是一个字符串值，其中包含 MCU 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="6eb9d-774">这是单值属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-774">This is a single-valued attribute.</span></span> <span data-ttu-id="6eb9d-775">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-776">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-778">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-779">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-781">此属性是一个字符串值，其中包含运行代理服务器的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="6eb9d-782">此属性是单值的。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-782">This attribute is single-valued.</span></span> <span data-ttu-id="6eb9d-783">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-784">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-786">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-788">此属性是一个单值属性，表示受信任服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-789">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="6eb9d-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-791">此属性指定受信任服务器列表中服务器的版本号。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="6eb9d-792">可能的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-793">NULL：实时通信服务器2003</span><span class="sxs-lookup"><span data-stu-id="6eb9d-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-794">2：实时通信服务器2005</span><span class="sxs-lookup"><span data-stu-id="6eb9d-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-795">3： Office 通信服务器2007</span><span class="sxs-lookup"><span data-stu-id="6eb9d-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-796">4： Office 通信服务器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6eb9d-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-797">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6eb9d-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-798">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb9d-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-799">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="6eb9d-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-801">此属性定义为受信任的服务启用的选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-802">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="6eb9d-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-804">此多值属性包含引用受信任服务对象（如媒体中继身份验证服务）的可分辨名称（DN）的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="6eb9d-805">媒体中继身份验证服务（运行 A/V 会议服务的边缘服务器上的物理 collocated）必须与一个池相关联，以便为远程用户支持音频方案。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="6eb9d-806">此前向链接属性的对应反向链接是<strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-807">跨度</span><span class="sxs-lookup"><span data-stu-id="6eb9d-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="6eb9d-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-809">此属性是一个整数，用于定义用于连接到此 GRUU 服务的端口号。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-810">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="6eb9d-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-812">此属性是一个字符串值，用于定义它所表示的 GRUU 服务的类型。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="6eb9d-813">有效的 GRUU 服务类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6eb9d-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-815">网关</span><span class="sxs-lookup"><span data-stu-id="6eb9d-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-816">媒体中继身份验证服务（MRAS）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="6eb9d-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="6eb9d-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-819">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-821">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-822">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="6eb9d-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-824">此属性是一个字符串值，其中包含运行 Lync Server Web 服务的 IIS 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="6eb9d-825">这是单值属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-825">This is a single-valued attribute.</span></span> <span data-ttu-id="6eb9d-826">每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-827">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-828">msRTCSIP-UCFlags （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-829">此属性定义对所有用户或联系人对象全局启用的不同 UC 选项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="6eb9d-830">此属性是整数类型的位掩码值。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="6eb9d-831">每个选项都由存在一个位表示。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="6eb9d-832">可能的有效值（和关联的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-833">4： UsePerUserUCPolicy （位位置2）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="6eb9d-834">设置此位时，UC 策略按用户定义。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-835">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-836">msRTCSIP-UCPolicy （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-837">此单值属性包含管理员为此用户分配的 UC 策略的可分辨名称（DN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-838">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-839">msRTCSIP-UserDomainList （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-840">此属性提供林中托管启用了 SIP 的用户的所有域的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="6eb9d-841">默认值为空列表，表示林中的所有域均为 SIP 启用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="6eb9d-842">有效值是表示单个域的域名的多个字符串。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-843">实时通信服务器2005中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6eb9d-844">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="6eb9d-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-846">此属性确定用户当前是否已启用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="6eb9d-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-848">此多值属性包含名称 = 值格式&quot;的名称值对列表。&quot;此属性标记为 "全局编录复制"。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-849">SP1 的实时通信服务器2005中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="6eb9d-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-851">此属性包含指向位置配置文件对象的识别名（DN）。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-852">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="6eb9d-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-854">此属性存储用户策略的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-855">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="6eb9d-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-857">这是一个包含可分辨名称列表的多值属性，其中二进制（DN_WITH_BINARY）指向不同类型的全局用户策略。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="6eb9d-858">二进制部分指示 DN 部分指向的策略类型。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="6eb9d-859">有效的二进制值如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-860">0x00000001：会议策略</span><span class="sxs-lookup"><span data-stu-id="6eb9d-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-861">0x00000002： UC 策略</span><span class="sxs-lookup"><span data-stu-id="6eb9d-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-862">0x00000005：状态策略</span><span class="sxs-lookup"><span data-stu-id="6eb9d-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-863">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6eb9d-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-865">这是 SIP 路由组 ID。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="6eb9d-866">同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-867">Lync Server 2013 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="6eb9d-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-869">这是一个多值属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="6eb9d-870">保留此属性供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-871">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="6eb9d-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-873">此单值属性指向 web 组件所属的池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="6eb9d-874">转发链接：<strong>链接 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="6eb9d-875">此前向链接属性的对应反向链接是<strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-876">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="6eb9d-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-878">此属性是可分辨名称的多值列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="6eb9d-879">此属性包含与此池关联的所有 Web 服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="6eb9d-880">反向链接：<strong>链接 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="6eb9d-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="6eb9d-881">指向此 back 链接的相应正向链接是<strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-882">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-883">msRTCSIP-WMIInstanceId （已过时）</span><span class="sxs-lookup"><span data-stu-id="6eb9d-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6eb9d-884">实时通信服务器2003中的新增项。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6eb9d-885">在实时通信服务器2005中已过时。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="6eb9d-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-887">电话将使用此现有 Active Directory 属性指定手机的备用 TCP/IP 地址列表。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-888">Windows Server 2008 操作系统中的新增操作。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="6eb9d-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-890">Lync Server 中的语音组件使用此现有 Active Directory 属性，仅适用于联系人对象，目的是将呼叫路由到统一消息自动助理和订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="6eb9d-891">无条件呼叫转发地址存储在此多值属性中。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="6eb9d-892">此帐户是为自动助理和订阅者访问的特定用途而创建的。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="6eb9d-893">管理员不应修改此帐户的属性。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-894">Windows 2000 操作系统中的新增操作。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6eb9d-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6eb9d-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-896">此现有 Active Directory 多值属性是 Windows 2000 中引入的基本 Active Directory 架构的一部分。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="6eb9d-897">此属性包含用户电子邮件的各种 X400、X500 和 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="6eb9d-898">在实时通信服务器2003和更高版本中，使用&quot;sip：&quot;标记将用户的 SIP URI 添加到此列表中。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="6eb9d-899">以下应用程序从该属性中搜索用户的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="6eb9d-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9d-900">Microsoft Office Outlook 2003 消息传递和协作客户端</span><span class="sxs-lookup"><span data-stu-id="6eb9d-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="6eb9d-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="6eb9d-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6eb9d-902">Windows 2000 操作系统中的新增操作。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6eb9d-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="6eb9d-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-904">此现有 Active Directory 属性包含用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="6eb9d-905">Windows 2000 操作系统中的新增操作。</span><span class="sxs-lookup"><span data-stu-id="6eb9d-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

