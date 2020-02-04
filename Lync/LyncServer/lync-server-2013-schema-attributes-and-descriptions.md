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

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 中的架构属性和说明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

本部分介绍 Lync Server 2013 使用的所有架构属性。 对于与属性相关联的类，请参阅[Lync Server 2013 中的 "按类架构属性](lync-server-2013-schema-attributes-by-class.md)"。 有关 Lync Server 2013 中新增的类和属性的列表，请参阅[Lync server 2013 中的架构更改](lync-server-2013-schema-changes-in-lync-server-2013.md)。

链接对的属性指定为 "前进链接" 或 "反向链接"。 引用另一个对象的属性是前向链接;引用第一个对象的其他对象的属性是 "后退" 链接。 正向链接是可更新的，而反向链接是只读的。

某些属性具有位掩码值。 对于这些属性，每个设置都由一个位表示，显示的十进制值表示位位置。 位位置从位0开始。 例如，1（binary）是位0集，10000（二进制）是位4设置。 每个位表示一个属性。 下面是一些示例：

  - 10000（binary）具有十进制值16（即设置了位4）。

  - 100000000（binary）的十进制值为256（即，设置了位8）。

  - 1100（binary）具有十进制值12（即，第2位和第3位）; 已启用两位数字表示的属性。

  - 1111000001（binary）的十进制值为961（即位0、6、7、8和9）; 每个位的属性均已启用。

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Lync Server 2013 的架构属性

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>描述</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Active Directory 域服务中现与<strong>msRTCSIP</strong>和<strong>msRTCSIP</strong>类相关联的现有属性。 此属性指定池或监视服务器的完全限定的域名（FQDN）。</p>
<p>每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>Microsoft Office Live 通信服务器2005中的新增新增项。</p></td>
</tr>
<tr class="even">
<td><p>SourceObjectDN</p></td>
<td><p>此属性包含另一个林中与此对象对应的对象的可分辨名称（DN）的字符串表示形式。 此属性用于通讯组扩展和自动出席。 此属性在 Windows Server 2003 R2 的默认 Active Directory 架构中定义。</p>
<p>为避免需要将 AD DS 升级到 Windows Server 2003 R2，Active Directory 架构准备使用此属性定义扩展了 Windows Server 2003 架构。</p></td>
<td><p>Microsoft Office 通信服务器2007中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>此多值属性包含语音邮件设置。 此属性与 Exchange 统一消息（UM）共享。</p></td>
<td><p>Microsoft Lync Server 2010 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多值属性包含适用于用户的保留策略的标识符。 保留策略在保留期间保留用户的邮箱项目。 此属性是与 Exchange 2013 共享的。</p></td>
<td><p>Lync Server 2013 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>此属性存储用户的音频会议提供商信息。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>此属性指向应用程序联系人的受信任服务条目。</p></td>
<td><p>Microsoft Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>此属性包含应用服务器上托管应用程序的列表。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>此属性指定应用程序联系人的选项。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>此属性包含应用程序联系人的主要语言。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>此多值属性包含应用程序联系人的辅助语言。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>此属性包含属于此池的应用程序服务器的列表。 指向此 back link 属性的相应正向链接是<strong>msRTCSIP-ApplicationServerPoolLink</strong>。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>此属性指向应用服务器所属的池。 这是 "转发" 链接。 相应的反向链接为<strong>msRTCSIP-ApplicationServerBL</strong>。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>Office 通信服务器2007中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags （已过时）</p></td>
<td><p>此属性指定林边界内用于存档所有用户通信的全局默认值。 这由存档代理层强制执行。 此属性的值范围如下所示：</p>
<ul>
<li><p><strong>TRUE</strong>：对所有用户进行存档</p></li>
<li><p><strong>FALSE</strong>：不存档所有用户</p></li>
</ul>
<p>此属性在林边界内对内部网络内的用户通信的存档方式进行全局控制。</p>
<p><strong>实时通信服务器2005行为（现已停用）</strong></p>
<p>此属性的值范围如下所示：</p>
<ul>
<li><p>0：将邮件正文存档 [位 0]</p></li>
<li><p>1：不存档邮件正文 [位 0]</p></li>
</ul>
<p><strong>Office 通信服务器2007行为</strong></p>
<p>此属性的值范围如下所示：</p>
<ul>
<li><p>0： ArchiveFederationDefaultWithoutBody （已停用）</p></li>
<li><p>1-2： ArchiveInternalCommunications</p></li>
<li><p>3-4： ArchiveFederatedCommunications</p></li>
<li><p>5： RecordPresenceRegistrations</p></li>
<li><p>6： RecordIMCallDetails</p></li>
<li><p>7： RecordGroupIMCallDetails</p></li>
<li><p>8： RecordFileTransferInstances</p></li>
<li><p>9： RecordAudioCallDetails</p></li>
<li><p>10： RecordVideoCallDetails</p></li>
<li><p>11： RecordRemoteAssistanceCallDetails</p></li>
<li><p>12： RecordApplicationSharingDetails</p></li>
<li><p>13： RecordMeetingInstantiations</p></li>
<li><p>14： RecordMeetingJoins</p></li>
<li><p>15： RecordDataJoins</p></li>
<li><p>16： RecordAVJoins</p></li>
</ul></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>Office 通信服务器2007中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>Office 通信服务器2007中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>此属性是一个整数，用作位域，用于控制是否要存档单个用户的通信。 此控件由存档代理层强制执行。 它标记为用于全局编录复制。</p>
<p>此属性的范围特定于单个用户或联系人。 Lync Server 中的有效值（和关联的位位置）如下所示：</p>
<ul>
<li><p>0：不存档（无位集）</p></li>
<li><p>1：已停用（位位置0）</p></li>
<li><p>2：已停用（位位置1）</p></li>
<li><p>4：存档内部通信（位位置2）</p></li>
<li><p>8：存档联合通信（位位置3）</p></li>
</ul>
<p>实时通信服务器2005中以前的有效值如下所示：</p>
<ul>
<li><p>0：使用<strong>msRTCSIP-ArchiveDefault</strong>和<strong>msRTCSIP-ArchiveFederation</strong>定义的默认值，按优先级顺序排列：</p>
<ul>
<li><p>1：存档</p></li>
<li><p>2：不存档</p></li>
<li><p>3：存档但不包含邮件正文</p></li>
</ul></li>
</ul></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion （已过时）</p></td>
<td><p>此属性定义存档服务的版本。 此属性是与每个正式产品版本递增的 monotonously 增加的整数类型。 可能的有效值如下：</p>
<ul>
<li><p>未定义：实时通信服务器2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3： Office 通信服务器2007</p></li>
<li><p>4： Office 通信服务器 2007 R2</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>此属性指定池后端服务器的 FQDN。 由于每个池中只能有一个后端服务器，这是单值属性。</p>
<p>每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>此属性包含托管会议目录的池的标识符。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>此属性包含会议目录的标识符。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>此属性包含要将会议目录移动到的池的标识符。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-默认值</p></td>
<td><p>此布尔属性定义电话使用情况是否为默认用法。 如果此属性设置为<strong>TRUE</strong>，则电话使用是默认用法，并且不能由管理员删除。 如果此属性设置为<strong>FALSE</strong>，则可以删除用法。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>此属性标识组织外部用户的 Communicator Web 访问 URL。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>此属性标识组织内部用户的 Communicator Web 访问 URL。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink （已过时）</p></td>
<td><p>此单值属性包含分配给它的位置配置文件类对象的识别名（DN）。</p>
<p>转发链接：<strong>链接 ID 11036</strong></p>
<p>相应的反向链接为<strong>msRTCSIP-ServerReferenceBL</strong>。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy （已过时）</p></td>
<td><p>此布尔属性指定策略是否为默认策略。 策略是设置为<strong>TRUE</strong>时的默认策略。</p></td>
<td><p>Office 通信服务器2007中的新增</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy （已过时）</p></td>
<td><p>此属性指定运行访问边缘服务的边缘服务器的 FQDN （如果可直接访问），或者指定运行 Access Edge 服务的服务器池的硬件负载平衡器的 FQDN。 如果运行 Access Edge 服务的服务器只能通过一个或多个控制器访问，则此属性指定 FQDN 和（可选）为控制器池提供服务的控制器或硬件负载平衡器的端口号。</p>
<p>每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort （已过时）</p></td>
<td><p>此属性表示应用于连接到运行 Access Edge 服务的服务器的端口号。</p>
<p>有效值是指定要使用的端口的整数值。 默认值为5061。</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示默认状态订阅的超时期限。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout （已过时）</p></td>
<td><p>此属性表示默认的注册超时窗口。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示默认的漫游数据订阅超时窗口。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>此属性在拆分的域拓扑中使用，并且包含完全限定的域名（FQDN）。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-说明（已过时）</p></td>
<td><p>此单值 UNICODE 字符串属性包含此电话路由或规范化规则的友好描述。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-域名</p></td>
<td><p>此属性表示为注册机构配置的域。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>此属性指定运行访问边缘服务的服务器的 FQDN。</p>
<p>每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify （已过时）</p></td>
<td><p>此属性控制服务器是否生成最佳操作通知（BENOTIFY）请求（而不是通知请求）以响应来自客户端的订阅请求。 BENOTIFY 是对订阅通知握手的性能增强扩展，服务器将生成 BENOTIFY 请求，而不是常规通知请求。 性能好处是 BENOTIFY 请求不需要来自客户端的 200 OK 响应，因为通知请求。</p>
<p>有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</p>
<div>

> [!NOTE]  
> 实时通信服务器2003不支持 BENOTIFY 请求。 若要与在实时通信服务器2005和第三方服务器上运行的实时通信2003服务器 API 编写的服务器应用程序互操作，可通过将 BENOTIFY 请求的值设置为<STRONG>FALSE</STRONG>来禁用这些请求。 BENOTIFY 当前不是 IETF （Internet 工程任务组） SIP 标准化过程的一部分。


</div></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation （已过时）</p></td>
<td><p>此属性是一个全局开关，IT 管理员使用它配置用户是否可以与其他组织中的用户进行通信。 它使管理员能够覆盖单个用户的<strong>FederationEnabled</strong>属性。 此属性可用于帮助保护内部网络免受受蠕虫、病毒或公司的目标攻击导致的网络攻击。</p>
<p>有效值（及相关位位置）如下所示：</p>
<ul>
<li><p>1：已启用公用 IM 连接（位位置0）</p></li>
<li><p>2：保留（位位置1）</p></li>
<li><p>4：保留（位位置2）</p></li>
<li><p>8：保留（位位置3）</p></li>
<li><p>16：启用远程呼叫控制 [电话] （位位置4）</p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants （允许用户邀请匿名用户加入会议（位位置6）</p></li>
<li><p>128： UCEnabled （启用统一通信的用户）（位位置7）</p></li>
<li><p>256： EnabledForEnhancedPresence （启用公用 IM 连接的用户）（bit 位置8）</p></li>
<li><p>512： RemoteCallControlDualMode （位位置9）</p></li>
</ul></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>此属性指示是否已在给定服务器上加载企业服务。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>此属性包含用于外部访问的拨号代码。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>此属性控制是否为单个用户启用联盟。 它由企业服务层强制执行。 它标记为用于全局编录复制。</p>
<p>有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>此属性是与池关联的所有企业版服务器的域名的多值列表。</p>
<p>反向链接：<strong>链接 ID 11023</strong></p>
<p>指向此 back 链接的相应正向链接是<strong>msRTCSIP-PoolAddress</strong>。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-网关（已过时）</p></td>
<td><p>此多值字符串属性包含网关和端口（每个网关）的列表。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData （已过时）</p></td>
<td><p>此属性存储 "名称：值" 对。 已定义的名称：值对用于 "<strong>允许轮询状态</strong>" 设置。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>此属性是用于分组通讯簿条目的组的唯一标识符。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增服务（未使用）。</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增项。</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增服务（未使用）。</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>此属性控制是否为单个用户启用外部用户访问权限。 它由企业服务层强制执行。 它标记为用于全局编录复制。</p>
<p>有效值为<strong>TRUE</strong>或<strong>FALSE</strong>。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-行</p></td>
<td><p>此单值属性包含 Lync 用于电话服务的设备 ID （用户控制的电话的 SIP URI 或电话 URI）。 此属性标记为 "全局编录复制"，并且已编制索引。 如果用户已启用企业语音，此属性将存储标准化的用户电话号码版本。</p></td>
<td><p>Microsoft Office Live 通信服务器2005中的新增 SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>此单值属性包含 CSTA 的 sip 网关服务器的 SIP URI。 此属性标记为全局编录复制，但未编入索引。</p></td>
<td><p>Microsoft Office Live 通信服务器2005中的新增 SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks （已过时）</p></td>
<td><p>此多值属性包含与此位置配置文件关联的本地规范化可分辨名称（DN）的列表。 此属性的类型是 DN 二进制。 位置配置文件与本地规范化规则之间存在一对多关系。 本地规范化 DNs 列表的顺序必须按管理员指定的顺序进行维护。 顺序保留由 DN 二进制部分的二进制部分进行维护，该二进制部分指定订单索引。</p>
<p>转发链接：<strong>链接 ID 11034</strong></p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-LocationProfileBL</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>此属性包含规范化规则的选项列表。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName （已过时）</p></td>
<td><p>此单值属性包含位置配置文件的友好名称，用于指示此配置文件所代表的位置。 由于可以有多个位置配置文件，因此管理员需要一种方式来区分不同的配置文件。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL （已过时）</p></td>
<td><p>此多值属性包含位置配置文件的可分辨名称的列表。 此属性指定指向一个或多个位置配置文件的反向链接。</p>
<p>反向链接：<strong>链接 ID 11035</strong></p>
<p>此属性对应于<strong>msRTCSIP-LocalNormalizationLinks</strong>的前进链接。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>此属性包含位置配置文件的选项。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>此多值属性包含应用程序联系人列表。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>此多值属性包含位置配置文件的列表。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer （已过时）</p></td>
<td><p>此属性表示每台服务器的未完成搜索请求的最大数量。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser （已过时）</p></td>
<td><p>该属性表示每个用户的最大订阅数。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示最长订阅超时时间窗口。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout （已过时）</p></td>
<td><p>此属性表示最大注册超时时段。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示 "漫游数据订阅最大超时" 窗口。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>此属性是计算机类下的服务控制点属性，用于指定返回到其所属 multipoint control 单元（MCU）工厂的链接。 将为每个 Microsoft MCU 创建此服务控制点和属性。 每个 Microsoft MCU 都必须找到其所属池的后端服务器，才能从中检索池级别的设置。</p>
<p>此属性的值是 MCU 工厂的可分辨名称（DN）。 这是单值属性，并标记为用于全局编录复制。</p>
<p>转发链接：<strong>链接 ID 11026</strong></p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-MCUServers</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>这是一个多字符串保留属性。 存储在此属性中的设置表示为 name = value 对。 当前定义的 name = value 对：</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>这是一个单值属性，包含与池关联的单个 MCU 工厂的识别名（DN）。</p>
<p>转发链接：<strong>链接 ID 11024</strong></p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-PoolAddresses</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>此属性是一个单值字符串，用于指定 MCU 工厂提供程序的 GUID。 根据 GUID 值，MCU 工厂进程确定是否为此 MCU 类型服务。 如果 GUID 值为<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，则 MCU 工厂进程（默认情况下在 Lync Server 中可用）将处理它。 对于任何其他 GUID 值，MCU 工厂进程将不会为 MCU 类型提供服务。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>此属性是可分辨名称（DN）的多值列表。 此属性包含与此 MCU 工厂关联的同一类型和供应商的所有 MCU 服务器的列表。 每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p>
<p>反向链接：链接 ID 11027</p>
<p>指向此 back 链接的相应正向链接是<strong>msRTCSIP-MCUFactoryAddress</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>此属性是一个单值字符串，用于指定 MCU 可以处理的媒介。</p>
<p>受支持的有效类型包括：</p>
<ul>
<li><p>符合</p></li>
<li><p>音频视频</p></li>
<li><p>聊天</p></li>
<li><p>电话会议</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>此属性是一个单值字符串，用于指定 MCU 供应商的名称。 所有 Microsoft MCUs 都将此属性指定为<strong>Microsoft Corporation</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags （已过时）</p></td>
<td><p>此属性定义为所有用户或联系人对象全局启用的不同会议选项。 此属性是整数类型的位掩码值。</p>
<p>有效值（及相关位位置）如下所示：</p>
<ul>
<li><p>0： AllowOrganizeMeetingWithAnonymousParticipants 为 None （不允许用户邀请匿名用户加入会议）（未设置 bits）</p></li>
<li><p>4： AllowOrganizeMeetingWithAnonymousParticipants 是每个人（允许所有用户邀请匿名用户加入会议）（位位置2）</p></li>
<li><p>8： AllowOrganizeMeetingWithAnonymousParticipants 为 UsePerUserSetting （允许用户基于每个用户设置邀请匿名用户加入会议）（位位置3）</p></li>
<li><p>16： UserPerUserMeetingPolicy （会议策略按用户定义）（位位置4）</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy （已过时）</p></td>
<td><p>此属性指定管理员为此用户分配的策略的可分辨名称（DN）作为单值属性。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示最小联机状态订阅超时窗口。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout （已过时）</p></td>
<td><p>此属性表示最小的注册超时窗口。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout （已过时）</p></td>
<td><p>此属性表示最少的漫游数据订阅超时窗口。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>此属性用于存储前端池使用的镜像 SQL Server 后端。</p></td>
<td><p>Lync Server 2013 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>此属性包含用于定义移动设置的选项和标志。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>此属性包含移动策略对象的 DN。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser （已过时）</p></td>
<td><p>此属性表示用户可以注册 SIP 通信和订阅状态的允许的设备数。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>此属性指定为用户或联系人对象启用的选项。 此属性是整数类型的位掩码值。 每个选项表示一个位。 此属性标记为 "全局编录复制"。</p>
<p>有效值（及相关位位置）如下所示：</p>
<ul>
<li><p>1：已启用公共即时消息（IM）连接（位位置0）</p></li>
<li><p>2：保留（位位置1）</p></li>
<li><p>4：保留（位位置2）</p></li>
<li><p>8：保留（位位置3）</p></li>
<li><p>16：启用远程呼叫控制 [电话] （位位置4）</p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants （允许用户邀请匿名用户加入会议（位位置6）</p></li>
<li><p>128： UCEnabled （启用 UC 的用户）（位位置7）</p></li>
<li><p>256： EnabledForEnhancedPresence （启用公用 IM 连接的用户）（bit 位置8）</p></li>
<li><p>512： RemoteCallControlDualMode （位位置9）</p></li>
</ul></td>
<td><p>SP1 的实时通信服务器2005中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>当从 Windows NT 服务器主体帐户中的用户的 ObjectSID 复制到资源或中央林中的相应用户或联系人对象的此属性时，在资源和中央林拓扑中使用此属性可启用单一登录。 Communicator Web Access 使用此属性或用户的 ObjectSID 在 AD DS 中搜索用户。 此属性标记为 "全局编录复制"。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>此属性是应用程序联系人的所有者的统一资源名称（URN）。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 模式（已过时）</p></td>
<td><p>此单值字符串属性包含用于将拨号号码匹配到164格式的模式。 如果拨号号码与此模式匹配，则转换将应用于已拨号码。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL （已过时）</p></td>
<td><p>此多值属性包含一个电话路由可分辨名称（DN）的列表。 此属性指定指向一个或多个电话路由的反向链接。</p>
<p>反向链接：<strong>链接 ID 11033</strong></p>
<p>此属性对应于<strong>msRTCSIP-RouteUsageLinks</strong>的前进链接。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName （已过时）</p></td>
<td><p>此单值 UNICODE 字符串属性指定手机路由的友好名称，以便管理员可以轻松地引用它。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent （已过时）</p></td>
<td><p>此属性是一个单值的 Unicode 字符串。 此字符串属性包含 XML 格式的策略定义。 XML 架构定义在不同的策略类型中是通用的，对于每个策略类型，仅这些设置是不同的。</p>
<p>XML 架构定义（XSD）的定义如下所示：</p>
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
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData （已过时）</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType （已过时）</p></td>
<td><p>此单值 Unicode 字符串属性包含策略类型。 有效的策略类型如下所示：</p>
<ul>
<li><p>符合</p></li>
<li><p>电话</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>此属性指定一个链接，该链接返回到计算机所属的池。 无论计算机运行的是标准版 Lync Server 还是企业版 Lync Server，均会设置此属性。 此属性标记为 "全局编录复制"。</p>
<p>有效的值是池的域名。</p>
<p>转发链接：<strong>链接 ID 11022</strong></p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-FrontEndServers</strong>。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>这是一个多值属性，其中包含与 MCU 工厂关联的池的可分辨名称（DN）列表。</p>
<p>反向链接：<strong>链接 ID 11025</strong></p>
<p>指向此 back 链接的相应正向链接是<strong>msRTCSIP-MCUFactoryPath</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>SP1 的实时通信服务器2005中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>此属性为管理控制台显示的池指定任意名称。 管理员可以更改此名称。</p>
<p>有效值是表示池名称的字符串。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>此属性是单值字符串值。 此属性的值（如果存在）表示池的域 FQDN （如果管理员希望使用不符合在其中创建前端池的 Active Directory 域结构的 FQDN 创建前端池）（例如，SIP从域名系统（DNS）命名空间中脱离命名空间。</p>
<p>我们建议你将前端池域 FQDN 映射到域名部分，作为池所在的 Active Directory 域。 因此，当此属性中不存在值时，前端池 FQDN 将默认为 Active Directory 域名结构，由<strong>dnsHostName</strong>属性表示。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>与池关联的所有 Lync Server、企业版服务器的域名的多值列表。 Type integer 的此属性定义池是否支持即时消息（IM）和状态以及会议。</p>
<p>可能有效的值类型如下所示：</p>
<ul>
<li><p>未定义：即时消息和状态服务（实时通信服务器2005和2003）</p></li>
<li><p>1：即时消息和状态服务（Lync Server）</p></li>
<li><p>2：即时消息和状态和会议服务（Lync Server）</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>此属性指定服务器池是否正在运行标准版服务器或企业版服务器。 此属性是整数类型的位掩码值。 每个选项表示一个位。</p>
<p>有效值（及相关位位置）如下所示：</p>
<ul>
<li><p>1：标准版服务器，托管用户（位位置0）</p></li>
<li><p>2：企业版服务器，托管用户（位位置1）</p></li>
<li><p>4：标准版服务器，托管应用程序（位位置2）</p></li>
<li><p>8：企业版服务器，托管应用程序（位位置3）</p></li>
</ul>
<p>由于 Lync Server 不支持仅托管应用程序的池，因此唯一有效的值如下所示：</p>
<ul>
<li><p>5：标准版服务器、托管用户和应用程序（位位置0和2）</p></li>
<li><p>10：企业版服务器、托管用户和应用程序（位位置1和3）</p></li>
</ul></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>此属性定义池版本。 它是一种与每个主要产品发布递增的整数类型。</p>
<p>可能有效的值类型如下所示：</p>
<ul>
<li><p>0：实时通信服务器2003</p></li>
<li><p>1：实时通信服务器2005</p></li>
<li><p>2：实时通信服务器2005与 SP1</p></li>
<li><p>3： Office 通信服务器2007</p></li>
<li><p>4： Office 通信服务器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
</ul></td>
<td><p>带有 SP1 的实时通信服务器2005。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>此属性包含用于定义联机状态设置的选项和标志。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>此属性包含状态策略对象的 DN。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>此属性启用 SIP 消息的用户或联系人。 它将添加到 contact 类，因为在中央林拓扑中，联系人对象（而不是用户对象）已启用 SIP。</p>
<p>有效值是用户托管的标准版服务器或企业版前端池的 DN。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>此属性包含给定用户的 SIP 地址。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>此属性包含专用线路设备的设备 ID。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-可路由</p></td>
<td><p>此属性是一个布尔属性，用于确定是否授权 Lync 服务器使用其 GRUU 地址路由到此服务。 如果此值设置为<strong>TRUE</strong>，则 Lync Server 有权路由到此服务。 如果此值设置为<strong>FALSE</strong>，则 Lync Server 无权路由到此服务。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute （已过时）</p></td>
<td><p>此单值 UNICODE 字符串属性定义了限定手机路由使用的属性。 根据两个元素确定手机路线的选择：分配给电话路线的使用属性和呼叫者允许的策略使用情况属性。 已选中与呼叫者允许的使用相匹配的第一条电话路由和使用情况属性。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks （已过时）</p></td>
<td><p>此多值可分辨名称（DN）属性包含路由使用可分辨名称的列表。</p>
<p>转发链接：<strong>链接 ID 11032</strong></p>
<p>此属性是指向对应的 back link <strong>msRTCSIP-PhoneRouteBL</strong>的前向链接。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>此属性包含指向所有寻址到此 MCU 或受信任服务的 SIP 流量必须经过的池的 DN。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName （已过时）</p></td>
<td><p>此单值 UNICODE 字符串属性指定规范化规则的友好名称，因此它可以由管理员轻松引用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>此属性表示组织中当前部署的架构版本。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests （已过时）</p></td>
<td><p>此属性限制当用户使用 Communicator 搜索联系人时，将从目录搜索返回的搜索结果的数量。 此属性将替代客户端提供的值。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults （已过时）</p></td>
<td><p>此属性限制返回的搜索请求数。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>此多值属性是一个后退链接，其中包含可分辨名称（DN）的列表。 这些 DNs 指向一个 pool 或<strong>TrustedService</strong>对象。</p>
<p>此属性对应于<strong>msRTCSIP-TrustedServiceLinks</strong>的前进链接。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL （已过时）</p></td>
<td><p>此多值属性包含一个可分辨名称的列表。 这些可分辨名称是反向链接，这些链接引用可以为其分配默认位置配置文件的其他服务器对象。</p>
<p>反向链接：<strong>链接 ID 11037</strong></p>
<p>指向此 back 链接的相应正向链接是<strong>msRTCSIP-DefaultLocationProfileLink</strong>。</p>
<p>此 back link 属性仅引用池和中介服务器。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>此属性定义服务器的版本信息。 此版本号适用于所有服务器角色。 这是一个 monotonously 增加的整数，每个官方产品版本增加。</p>
<p>可能的有效值如下所示：</p>
<ul>
<li><p>未定义：实时通信服务器2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3： Office 通信服务器2007</p></li>
<li><p>4： Office 通信服务器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Integer 类型的此单值属性指定<strong>SourceObjectDN</strong>指向的对象的类型，如下所示：</p>
<ul>
<li><p>null |0x00000001：表示来自不同林中的 Windows NT 服务器主体用户对象</p></li>
<li><p>以下属性表示通讯组扩展来自不同林中的组类型：</p>
<ul>
<li><p>0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000：表示来自同一林或不同林中的自动助理或订阅者访问对象</p></li>
</ul></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增项。</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>此属性使你能够将用户或联系人对象从一个 Lync 服务器池移动到另一个。 此属性将添加到 contact 类，因为在中央林拓扑中，联系人对象（而不是用户对象）已启用 SIP。</p>
<p>有效值是要将用户移动到的目标标准版服务器或前端池的 DN。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber （已过时）</p></td>
<td><p>此单值字符串属性包含用于路由到在<strong>msRTCSIP-网关</strong>定义的指定网关的电话号码模式或范围。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>此属性存储 Lync Server 用户的目标策略的名称/值对。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>此属性存储租户的唯一标识符。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-翻译（已过时）</p></td>
<td><p>此属性由 Lync Server 的语音功能使用，并且包含要在已拨号码上应用的翻译字符串（如果找到匹配项）。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>此属性是一个字符串值，其中包含 MCU 的 FQDN。 这是单值属性。 每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>此属性是一个字符串值，其中包含运行代理服务器的服务器的 FQDN。 此属性是单值的。 每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>此属性是一个单值属性，表示受信任服务器的 FQDN。</p></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>此属性指定受信任服务器列表中服务器的版本号。</p>
<p>可能的有效值如下所示：</p>
<ul>
<li><p>NULL：实时通信服务器2003</p></li>
<li><p>2：实时通信服务器2005</p></li>
<li><p>3： Office 通信服务器2007</p></li>
<li><p>4： Office 通信服务器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>实时通信服务器2005中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>此属性定义为受信任的服务启用的选项。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>此多值属性包含引用受信任服务对象（如媒体中继身份验证服务）的可分辨名称（DN）的列表。 媒体中继身份验证服务（运行 A/V 会议服务的边缘服务器上的物理 collocated）必须与一个池相关联，以便为远程用户支持音频方案。</p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-ServerBL</strong>。</p></td>
<td><p>跨度</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>此属性是一个整数，用于定义用于连接到此 GRUU 服务的端口号。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>此属性是一个字符串值，用于定义它所表示的 GRUU 服务的类型。</p>
<p>有效的 GRUU 服务类型如下所示：</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>网关</p></li>
<li><p>媒体中继身份验证服务（MRAS）</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>此属性是一个字符串值，其中包含运行 Lync Server Web 服务的 IIS 的 FQDN。 这是单值属性。 每个段的有效值为63个字符;整个 FQDN 的有效值为255个字符。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags （已过时）</p></td>
<td><p>此属性定义对所有用户或联系人对象全局启用的不同 UC 选项。 此属性是整数类型的位掩码值。 每个选项都由存在一个位表示。</p>
<p>可能的有效值（和关联的位位置）如下所示：</p>
<ul>
<li><p>4： UsePerUserUCPolicy （位位置2）</p></li>
</ul>
<p>设置此位时，UC 策略按用户定义。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy （已过时）</p></td>
<td><p>此单值属性包含管理员为此用户分配的 UC 策略的可分辨名称（DN）。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList （已过时）</p></td>
<td><p>此属性提供林中托管启用了 SIP 的用户的所有域的列表。 默认值为空列表，表示林中的所有域均为 SIP 启用。</p>
<p>有效值是表示单个域的域名的多个字符串。</p></td>
<td><p>实时通信服务器2005中的新增项。</p>
<p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>此属性确定用户当前是否已启用 Lync Server。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>此多值属性包含名称 = 值格式&quot;的名称值对列表。&quot;此属性标记为 "全局编录复制"。</p></td>
<td><p>SP1 的实时通信服务器2005中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>此属性包含指向位置配置文件对象的识别名（DN）。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>此属性存储用户策略的名称/值对。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>这是一个包含可分辨名称列表的多值属性，其中二进制（DN_WITH_BINARY）指向不同类型的全局用户策略。 二进制部分指示 DN 部分指向的策略类型。</p>
<p>有效的二进制值如下所示：</p>
<ul>
<li><p>0x00000001：会议策略</p></li>
<li><p>0x00000002： UC 策略</p></li>
<li><p>0x00000005：状态策略</p></li>
</ul></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>这是 SIP 路由组 ID。 同一组中的用户将注册到同一前端服务器。</p></td>
<td><p>Lync Server 2013 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>这是一个多值属性。 保留此属性供将来使用。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>此单值属性指向 web 组件所属的池或标准版服务器。</p>
<p>转发链接：<strong>链接 ID 11028</strong></p>
<p>此前向链接属性的对应反向链接是<strong>msRTCSIP-WebComponentsServers</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>此属性是可分辨名称的多值列表。 此属性包含与此池关联的所有 Web 服务器的列表。</p>
<p>反向链接：<strong>链接 ID 11029</strong></p>
<p>指向此 back 链接的相应正向链接是<strong>msRTCSIP-WebComponentsPoolAddress</strong>。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId （已过时）</p></td>
<td><p>-</p></td>
<td><p>实时通信服务器2003中的新增项。</p>
<p>在实时通信服务器2005中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>电话将使用此现有 Active Directory 属性指定手机的备用 TCP/IP 地址列表。</p></td>
<td><p>Windows Server 2008 操作系统中的新增操作。</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Lync Server 中的语音组件使用此现有 Active Directory 属性，仅适用于联系人对象，目的是将呼叫路由到统一消息自动助理和订阅者访问号码。 无条件呼叫转发地址存储在此多值属性中。 此帐户是为自动助理和订阅者访问的特定用途而创建的。 管理员不应修改此帐户的属性。</p></td>
<td><p>Windows 2000 操作系统中的新增操作。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>此现有 Active Directory 多值属性是 Windows 2000 中引入的基本 Active Directory 架构的一部分。 此属性包含用户电子邮件的各种 X400、X500 和 SMTP 地址。 在实时通信服务器2003和更高版本中，使用&quot;sip：&quot;标记将用户的 SIP URI 添加到此列表中。</p>
<p>以下应用程序从该属性中搜索用户的 SIP URI：</p>
<ul>
<li><p>Microsoft Office Outlook 2003 消息传递和协作客户端</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 操作系统中的新增操作。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>此现有 Active Directory 属性包含用户的电话号码。</p></td>
<td><p>Windows 2000 操作系统中的新增操作。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

