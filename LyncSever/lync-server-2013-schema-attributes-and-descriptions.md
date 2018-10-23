---
title: Lync Server 2013 中的架构属性和说明
TOCTitle: Lync Server 2013 中的架构属性和说明
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412841(v=OCS.15)
ms:contentKeyID: 49313962
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的架构属性和说明

 

_**上一次修改主题：** 2015-03-09_

本节介绍 Lync Server 2013 使用的所有架构属性。有关与属性关联的类，请参阅[Lync Server 2013 中的按类分组的架构属性](lync-server-2013-schema-attributes-by-class.md)。有关 Lync Server 2013 中新增的类和属性的列表，请参阅 [Lync Server 2013 中的架构更改](lync-server-2013-schema-changes-in-lync-server-2013.md)。

将链接为一对的属性指定为正向链接或反向链接。指向另一个对象的属性为正向链接；向回指向第一个对象的其他对象的属性为反向链接。正向链接可更新，而反向链接为只读。

有些属性具有位掩码值。对于这些属性，每项设置均由位表示，所显示的十进制值表示各个位的位置。位的位置从第 0 位开始。例如，1（二进制）设置了第 0 位，10000（二进制）设置了第 4 位。每位表示一个属性。下面给出了一些示例：

  - 10000（二进制）的十进制值为 16（即设置了第 4 位）。

  - 100000000（二进制）的十进制值为 256（即设置了第 8 位）。

  - 1100（二进制）的十进制值为 12（即设置了第 2 位和第 3 位；这两位表示的属性已启用）。

  - 1111000001（二进制）的十进制值为 961（即设置了第 0、6、7、8 和 9 位；这些位中每位表示的属性已启用）。

### Lync Server 2013 的架构属性

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Active Directory 域服务 中现与 <strong>msRTCSIP-Pool</strong> 和 <strong>msRTCSIP-MonitoringServer</strong> 类相关联的现有属性。此属性指定池或监控服务器的完全限定域名 (FQDN)。</p>
<p>每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>此属性包含一个字符串，表示另一个林中与此对象相对应的对象的可分辨名称 (DN)。此属性用于通讯组扩展和自动助理。此属性是在 Windows Server 2003 R2 的默认 Active Directory 架构中定义的。</p>
<p>为了省去将 AD DS 升级到 Windows Server 2003 R2 的麻烦，Active Directory 架构准备使用此属性定义扩展 Windows Server 2003 架构。</p></td>
<td><p>Microsoft Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>此多值属性保存语音邮件设置。与 Exchange 统一消息 (UM) 共享此属性。</p></td>
<td><p>Microsoft Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多值属性可保存应用于用户的保留策略的标识符。保留策略会在保留持续时间内保留用户的邮箱项目。与 Exchange 2013 共享此属性。</p></td>
<td><p>Lync Server 2013 的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>此属性存储用户的音频会议提供商信息。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>此属性指向应用程序联系人的受信任的服务项。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>此属性包含应用程序服务器上所承载的应用程序的列表。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>此属性指定应用程序联系人的选项。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>此属性包含应用程序联系人的主要语言。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>此多值属性包含应用程序联系人的辅助语言。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>此属性包含属于此池的应用程序服务器的列表。此反向链接属性相应的正向链接为 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>此属性指向此应用程序服务器所属的池。它属于正向链接。相应的反向链接为 <strong>msRTCSIP-ApplicationServerBL</strong>。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Office Communications Server 2007 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags（作废）</p></td>
<td><p>此属性指定林边界内用于对所有用户通信进行存档的全局默认设置。这由存档代理层强制执行。此属性的值范围如下：</p>
<ul>
<li><p><strong>TRUE</strong>：存档所有用户</p></li>
<li><p><strong>FALSE</strong>：不存档所有用户</p></li>
</ul>
<p>此属性在林边界内对内部网络中的用户通信存档方式进行全局控制。</p>
<p><strong>Live Communications Server 2005 行为（现已撤销）</strong></p>
<p>此属性的值范围如下：</p>
<ul>
<li><p>0: 对消息正文进行存档 [0 位]</p></li>
<li><p>1: 不对消息正文进行存档 [0 位]</p></li>
</ul>
<p><strong>Office Communications Server 2007 行为</strong></p>
<p>此属性的值范围如下：</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody（已撤销）</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Office Communications Server 2007 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Office Communications Server 2007 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>此属性是一个用作位字段的整数，用于控制是否要对单个用户的通信进行存档。这种控制由存档代理层强制执行。此属性标记为进行全局编录复制。</p>
<p>此属性的作用域特定于单个用户或联系人。此属性在 Lync Server 中的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>0: 不存档（未设置位）</p></li>
<li><p>1: 已撤销（第 0 位）</p></li>
<li><p>2: 已撤销（第 1 位）</p></li>
<li><p>4: 对内部通信进行存档（第 2 位）</p></li>
<li><p>8: 对联盟通信进行存档（第 3 位）</p></li>
</ul>
<p>以前在 Live Communications Server 2005 中的有效值如下：</p>
<ul>
<li><p>0：按以下优先顺序使用由 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 定义的默认值：</p>
<ul>
<li><p>1: 存档</p></li>
<li><p>2: 不存档</p></li>
<li><p>3: 存档，但不包括消息正文</p></li>
</ul></li>
</ul></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion（作废）</p></td>
<td><p>此属性定义存档服务的版本。此属性属于单调递增的整数类型，它随每次正式产品发布而递增。可能的有效值为：</p>
<ul>
<li><p>未定义：Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>此属性指定池的后端服务器的 FQDN。因为每个池只能有一个后端服务器，所以这是一个单值属性。</p>
<p>每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>此属性包含承载会议目录的池的标识符。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>此属性包含会议目录的标识符。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>此属性包含要向其移动会议目录的池的标识符。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Default</p></td>
<td><p>此布尔属性定义电话用法是否为默认用法。如果此属性设置为 <strong>TRUE</strong>，则电话用法为默认用法，且管理员无法删除该用法。如果此属性设置为 <strong>FALSE</strong>，则可以删除该用法。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>此属性标识组织外部用户的 Communicator Web Access URL。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>此属性标识组织内部用户的 Communicator Web Access URL。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink（作废）</p></td>
<td><p>此单值属性包含分配给它的位置配置文件类对象的可分辨名称 (DN)。</p>
<p>正向链接：<strong>链接 ID 11036</strong></p>
<p>相应的反向链接为 <strong>msRTCSIP-ServerReferenceBL</strong>。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy（作废）</p></td>
<td><p>此布尔属性指定策略是否为默认策略。当此属性设置为 <strong>TRUE</strong> 时，策略为默认策略。</p></td>
<td><p>Office Communications Server 2007 中的新增属性</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy（作废）</p></td>
<td><p>此属性指定运行访问边缘服务的边缘服务器（如果能直接访问）的 FQDN，或指定运行访问边缘服务的服务器的池的硬件负载平衡器的 FQDN。如果只能通过一个或多个控制器访问运行访问边缘服务的服务器，则此属性指定控制器或为控制器池提供服务的硬件负载平衡器的 FQDN 及端口号（端口号为可选指定内容）。</p>
<p>每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort（作废）</p></td>
<td><p>此属性代表应用于连接到运行访问边缘服务的服务器的端口号。</p>
<p>有效值为指定要使用的端口的整数值。默认值为 5061。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示默认的状态订阅超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout（作废）</p></td>
<td><p>此属性表示默认的注册超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示默认的漫游数据订阅超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>此属性在拆分域拓扑中使用，并且包含完全限定域名 (FQDN)。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description（作废）</p></td>
<td><p>此单值 UNICODE 字符串属性包含对此电话路由或规范化规则的友好描述。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>此属性表示为注册器配置的域。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>此属性指定运行访问边缘服务的服务器的 FQDN。</p>
<p>每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify（作废）</p></td>
<td><p>此属性控制服务器是否生成 Best Effort NOTIFY (BENOTIFY) 请求（而不是 NOTIFY 请求）以响应来自客户端的 SUBSCRIBE 请求。BENOTIFY 是对订阅通知握手的性能增强扩展，在此过程中，服务器将生成 BENOTIFY 请求，而不是通常的 NOTIFY 请求。其性能优点在于，BENOTIFY 请求不需要来自客户端的 200 OK 响应，而 NOTIFY 请求则需要。</p>
<p>有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 不支持 BENOTIFY 请求。在 Live Communications Server 2005 和第三方服务器上运行的某些服务器应用程序是用 Live Communications Server 2003 服务器 API 编写的，若要与这些应用程序进行互操作，可通过将此属性的值设置为 <strong>FALSE</strong> 来禁用 BENOTIFY 请求。BENOTIFY 目前不是 IETF（Internet 工程任务组）SIP 标准化过程的一部分。


</div></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation（作废）</p></td>
<td><p>此属性是供 IT 管理员使用的全局开关，用于配置是否允许用户与其他组织的用户进行通信。管理员可使用此属性覆盖单个用户的 <strong>FederationEnabled</strong> 属性。此属性有助于保护内部网络免受蠕虫和病毒导致的 Internet 攻击，或针对公司的各种攻击。</p>
<p>此属性的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>1: 启用公共 IM 连接（第 0 位）</p></li>
<li><p>2: 保留（第 1 位）</p></li>
<li><p>4: 保留（第 2 位）</p></li>
<li><p>8: 保留（第 3 位）</p></li>
<li><p>16: 启用了远程呼叫控制 [电话]（第 4 位）</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</p></li>
<li><p>128: UCEnabled（为用户启用统一通信）（第 7 位）</p></li>
<li><p>256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</p></li>
<li><p>512: RemoteCallControlDualMode（第 9 位）</p></li>
</ul></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>此属性指示给定服务器上是否已加载企业服务。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>此属性包含用于外部访问的拨号代码。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>此属性控制是否为单个用户启用联盟。它由企业服务层强制执行。此属性标记为进行全局编录复制。</p>
<p>有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>此属性是一个多值列表，其中包含与池关联的所有 Enterprise Edition Server 的域名。</p>
<p>反向链接：<strong>链接 ID 11023</strong></p>
<p>此反向链接相应的正向链接为 <strong>msRTCSIP-PoolAddress</strong>。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways（作废）</p></td>
<td><p>此多值字符串属性包含网关和端口的列表（每个网关）。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData（作废）</p></td>
<td><p>此属性存储“名称:值”对。已定义的“名称:值”对用于“允许轮询状态”设置。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>此属性是用于归类组通讯簿条目的组的唯一标识符。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增属性（未使用）。</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增类。</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增属性（未使用）。</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>此属性控制是否为单个用户启用外部用户访问。它由企业服务层强制执行。此属性标记为进行全局编录复制。</p>
<p>有效值为 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增属性</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Line</p></td>
<td><p>此单值属性包含 Lync 用于电话的设备 ID（用户所控制的电话的 SIP URI 或 TEL URI）。此属性标记为进行全局编录复制，并且已编入索引。如果为用户启用了企业语音，则此属性存储该用户的电话号码的 E.164 规范化版本。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 中的新增属性</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>此单值属性包含 CSTA-SIP 网关服务器的 SIP URI。此属性标记为进行全局编录复制，但未编入索引。</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1 中的新增属性</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks（作废）</p></td>
<td><p>此多值属性包含与此位置配置文件关联的本地规范化可分辨名称 (DN) 列表。此属性的类型是 DN 二进制值。位置配置文件和本地规范化规则之间存在一对多关系。必须按照管理员指定的顺序维护本地规范化 DN 列表的顺序。顺序的保持是由 DN 二进制值的二进制值部分维护的，该部分指定了顺序索引。</p>
<p>正向链接：<strong>链接 ID 11034</strong></p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-LocationProfileBL</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>此属性包含规范化规则的选项列表。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName（作废）</p></td>
<td><p>此单值属性包含位置配置文件的友好名称，用于指示此配置文件所表示的位置。因为可能有多个位置配置文件，所以管理员需要一种方法来区分不同的配置文件。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL（作废）</p></td>
<td><p>此多值属性包含位置配置文件可分辨名称的列表。此属性指定一个或多个位置配置文件的反向链接。</p>
<p>反向链接：<strong>链接 ID 11035</strong></p>
<p>此属性对应于正向链接 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>此属性包含位置配置文件的选项。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>此多值属性包含应用程序联系人的列表。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>此多值属性包含位置配置文件的列表。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer（作废）</p></td>
<td><p>此属性表示每台服务器未处理搜索请求的最大数量。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser（作废）</p></td>
<td><p>该属性表示每个用户的最大订阅数。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示最大订阅超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout（作废）</p></td>
<td><p>此属性表示最大注册超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示最大漫游数据订阅超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>此属性是计算机类下属的一个服务控制点属性，该计算机类指定指向其所属多点控制单元 (MCU) 中心的反向链接。此服务控制点和属性是为每一个 Microsoft MCU 创建的。每个 Microsoft MCU 都必须找到其所属池的后端服务器，才能从中检索池级设置。</p>
<p>此属性的值是 MCU 中心的可分辨名称 (DN)。此属性是单值属性，并且标记为进行全局编录复制。</p>
<p>正向链接：<strong>链接 ID 11026</strong></p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-MCUServers</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>此属性是多字符串保留属性。存储在此属性中的设置表示为“名称=值”对。当前定义的“名称=值”对如下：</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>这是一个单值属性，包含与池关联的单个 MCU 中心的可分辨名称 (DN)。</p>
<p>正向链接：<strong>链接 ID 11024</strong></p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-PoolAddresses</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>此属性为单值字符串，用于指定 MCU 中心提供程序的 GUID。根据该 GUID 值，MCU 中心进程可确定是否向此 MCU 类型提供服务。如果 GUID 值为 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，则 MCU 中心进程（默认情况下在 Lync Server 中可用）将处理它。对于任何其他 GUID 值，MCU 中心进程不会向该 MCU 类型提供服务。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>此属性为可分辨名称 (DN) 的多值列表。此属性包含一个列表，其中列出了与此 MCU 中心关联的供应商的所有 MCU 服务器，且这些服务器属于同一类型。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p>
<p>反向链接：链接 ID 11027</p>
<p>此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryAddress</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>此属性为单值字符串，用于指定 MCU 可处理的媒体。</p>
<p>受支持的有效类型如下：</p>
<ul>
<li><p>meeting</p></li>
<li><p>audio-video</p></li>
<li><p>chat</p></li>
<li><p>phone-conf</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>此属性为指定 MCU 供应商名称的单值字符串。所有 Microsoft MCU 都将此属性指定为 <strong>Microsoft Corporation</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags（作废）</p></td>
<td><p>此属性定义为所有用户或联系对象在全局范围启用的各种会议选项。此属性为整数类型的位掩码值。</p>
<p>此属性的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants 为 None（不允许用户邀请匿名用户加入会议）（未设置位）</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants 为 Everyone（允许所有用户邀请匿名用户加入会议）（第 2 位）</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants 为 UsePerUserSetting（根据每用户设置允许用户邀请匿名用户加入会议）（第 3 位）</p></li>
<li><p>16: UserPerUserMeetingPolicy（按用户定义会议策略）（第 4 位）</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy（作废）</p></td>
<td><p>此属性以单值属性的形式指定管理员已为此用户分配的策略的可分辨名称 (DN)。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示最小状态订阅超时时段。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout（作废）</p></td>
<td><p>此属性表示最小注册超时时段。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout（作废）</p></td>
<td><p>此属性表示最小漫游数据订阅超时时段。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>此属性可用来存储前端池所使用的镜像 SQL Server 后端。</p></td>
<td><p>Lync Server 2013 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>此属性包含用于定义移动性设置的选项和标志。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>此属性包含移动性策略对象的 DN。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser（作废）</p></td>
<td><p>此属性表示用户可在其中注册 SIP 通信和订阅状态的设备数。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>此属性指定为用户或联系对象启用的选项。此属性为整数类型的位掩码值。每个选项都由位表示。此属性标记为进行全局编录复制。</p>
<p>此属性的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>1: 启用公共即时消息 (IM) 连接（第 0 位）</p></li>
<li><p>2: 保留（第 1 位）</p></li>
<li><p>4: 保留（第 2 位）</p></li>
<li><p>8: 保留（第 3 位）</p></li>
<li><p>16: 启用了远程呼叫控制 [电话]（第 4 位）</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants（允许用户邀请匿名用户加入会议）（第 6 位）</p></li>
<li><p>128: UCEnabled（为用户启用 UC）（第 7 位）</p></li>
<li><p>256: EnabledForEnhancedPresence（为用户启用公共 IM 连接）（第 8 位）</p></li>
<li><p>512: RemoteCallControlDualMode（第 9 位）</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>当用户的 ObjectSID 从 Windows NT Server 主体帐户复制到资源林或中央林中相应用户或联系人对象的此属性中时，此属性在资源林拓扑和中央林拓扑中用于实现单一登录。Communicator Web Access 使用此属性或用户的 ObjectSID 搜索 AD DS 中的用户。此属性标记为进行全局编录复制。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>此属性为应用程序联系人所有者的统一资源名称 (URN)。</p></td>
<td><p>Lync Server 2010 中的新增类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern（作废）</p></td>
<td><p>此单值字符串属性包含用于将拨号号码匹配为 E.164 格式的模式。如果拨号号码与此模式匹配，则对所拨号码应用转换。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL（作废）</p></td>
<td><p>此多值属性包含电话路由可分辨名称 (DN) 的列表。此属性指定一个或多个电话路由的反向链接。</p>
<p>反向链接：<strong>链接 ID 11033</strong></p>
<p>此属性对应于正向链接 <strong>msRTCSIP-RouteUsageLinks</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName（作废）</p></td>
<td><p>此单值 UNICODE 字符串属性指定电话路由的友好名称，以便于管理员引用。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent（作废）</p></td>
<td><p>此属性为单值 Unicode 字符串。此字符串属性包含 XML 格式的策略定义。对于不同的策略类型，该 XML 架构定义是共用的，只有设置因每种策略类型而异。</p>
<p>下面定义了 XML 架构定义 (XSD)：</p>
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
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData（作废）</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType（作废）</p></td>
<td><p>此单值 Unicode 字符串属性包含策略类型。有效策略类型如下：</p>
<ul>
<li><p>会议</p></li>
<li><p>电话</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>此属性指定指向计算机所属池的反向链接。无论计算机运行的是 Lync Server Standard Edtion 还是 Enterprise Edition，都将设置此属性。此属性标记为进行全局编录复制。</p>
<p>有效值为池的域名。</p>
<p>正向链接：<strong>链接 ID 11022</strong></p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-FrontEndServers</strong>。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>这是一个多值属性，包含与 MCU 中心关联的池的可分辨名称 (DN) 的列表。</p>
<p>反向链接：<strong>链接 ID 11025</strong></p>
<p>此反向链接相应的正向链接为 <strong>msRTCSIP-MCUFactoryPath</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Live Communications Server 2005 SP1 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>此属性指定管理控制台显示的池的任意名称。管理员可以更改此名称。</p>
<p>有效值为表示池名称的字符串。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>此属性为单值字符串值。如果管理员要创建的前端池的 FQDN 不符合从中创建该前端池的 Active Directory 域结构（例如 SIP 命名空间与域名系统 (DNS) 命名空间分离），则此属性的值（如果存在）表示该池的域 FQDN。</p>
<p>我们建议将前端池域 FQDN 映射到该池所在的 Active Directory 域的域名部分。因此，当此属性中不存在值时，前端池 FQDN 将默认为 <strong>dnsHostName</strong> 属性所表示的 Active Directory 域名结构。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>一个多值列表，包含与池关联的所有 Lync Server Enterprise Edition Server 的域名。此属性为整数类型，它定义池是否支持即时消息 (IM)、状态和会议。</p>
<p>可能的有效值类型如下：</p>
<ul>
<li><p>未定义：IM 和状态服务（Live Communications Server 2005 和 2003）</p></li>
<li><p>1: IM 和状态服务 (Lync Server)</p></li>
<li><p>2: IM 和状态以及会议服务 (Lync Server)</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>此属性指定服务器池运行的是 Standard Edition Server 还是 Enterprise Edition Server。此属性为整数类型的位掩码值。每个选项都由位表示。</p>
<p>此属性的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>1: Standard Edition Server，承载用户（第 0 位）</p></li>
<li><p>2: Enterprise Edition Server，承载用户（第 1 位）</p></li>
<li><p>4: Standard Edition Server，承载应用程序（第 2 位）</p></li>
<li><p>8: Enterprise Edition Server，承载应用程序（第 3 位）</p></li>
</ul>
<p>由于 Lync Server 不支持仅承载应用程序的池，因此，只有以下值有效：</p>
<ul>
<li><p>5: Standard Edition Server，承载用户和应用程序（第 0 和 2 位）</p></li>
<li><p>10: Enterprise Edition Server，承载用户和应用程序（第 1 和 3 位）</p></li>
</ul></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>此属性定义池版本。它为整数类型，在每次主要产品发布时递增。</p>
<p>可能的有效值类型如下：</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>此属性包含用于定义状态设置的选项和标志。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>此属性包含状态策略对象的 DN。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>此属性为用户或联系人启用 SIP 消息。它添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</p>
<p>有效值为用户所在 Standard Edition Server 或 Enterprise Edition 前端池的 DN。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>此属性包含给定用户的 SIP 地址。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>此属性包含专线设备的设备 ID。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Routable</p></td>
<td><p>此属性为布尔属性，用于确定 Lync Server 是否有权使用其 GRUU 地址路由到此服务。如果此值设置为 <strong>TRUE</strong>，则 Lync Server 有权路由到此服务。如果此值设置为 <strong>FALSE</strong>，则 Lync Server 无权路由到此服务。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute（作废）</p></td>
<td><p>此单值 UNICODE 字符串属性定义限定电话路由用法的属性。电话路由的选择基于两个元素确定：一是分配给电话路由的用法属性，二是经允许的主叫方的策略用法属性。将选择用法属性与主叫方允许的用法相匹配的第一个电话路由。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks（作废）</p></td>
<td><p>此多值可分辨名称 (DN) 属性包含路由用法可分辨名称的列表。</p>
<p>正向链接：<strong>链接 ID 11032</strong></p>
<p>此属性是反向链接 <strong>msRTCSIP-PhoneRouteBL</strong> 对应的正向链接。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>此属性包含指向发往此 MCU 或受信任服务的所有 SIP 流量都必须通过的池的 DN。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName（作废）</p></td>
<td><p>此单值 UNICODE 字符串属性指定规范化规则的友好名称，以方便管理员进行引用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>此属性表示组织中当前部署的架构版本。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests（作废）</p></td>
<td><p>此属性限制用户使用 Communicator 搜索联系人时，从目录搜索中返回的搜索结果的数量。此属性将覆盖客户端提供的值。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults（作废）</p></td>
<td><p>此属性限制所返回的搜索请求数。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>此多值属性为包含可分辨名称 (DN) 列表的反向链接。这些 DN 指向池或 <strong>TrustedService</strong> 对象。</p>
<p>此属性对应于正向链接 <strong>msRTCSIP-TrustedServiceLinks</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL（作废）</p></td>
<td><p>此多值属性包含可分辨名称的列表。这些可分辨名称是引用可分配默认位置配置文件的其他服务器对象的反向链接。</p>
<p>反向链接：<strong>链接 ID 11037</strong></p>
<p>此反向链接对应的正向链接为 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</p>
<p>此反向链接属性仅引用池和中介服务器。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>此属性定义服务器的版本信息。此版本号应用于所有服务器角色。它是一个单调递增的整数，并且随每一次正式产品发布而递增。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>未定义：Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>此整数类型的单值属性指定 <strong>msDS-SourceObjectDN</strong> 所指对象的类型，如下所示：</p>
<ul>
<li><p>null | 0x00000001:表示来自另一个林的 Windows NT Server 主体用户对象</p></li>
<li><p>下面的属性表示来自另一个林的用于通讯组扩展的组类型：</p>
<ul>
<li><p>0x00000002：ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004：ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004：ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008：ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000：ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000：表示同一个林或另一个林中的自动助理或订阅者访问对象</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增类。</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>通过此属性，可以将用户或联系人对象从一个 Lync Server 池移至另一个。此属性添加到联系类，因为在中央林拓扑中为联系对象（而非用户对象）启用了 SIP。</p>
<p>有效值为用户要移至的目标 Standard Edition Server 或前端池的 DN。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber（作废）</p></td>
<td><p>此单值字符串属性包含要路由到 <strong>msRTCSIP-Gateways</strong> 中定义的指定网关的电话号码模式或范围。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>此属性存储 Lync Server 用户的目标策略的名称值对。</p></td>
<td><p>Lync Server 2010 中的新增类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>此属性存储租户的唯一标识符。</p></td>
<td><p>Lync Server 2010 中的新增类。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation（作废）</p></td>
<td><p>此属性由 Lync Server 的语音功能使用，并且包含要应用于所拨号码的转换字符串（如果找到匹配项）。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>此属性是包含 MCU 的 FQDN 的字符串值。这是一个单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>此属性是一个字符串值，其中包含运行代理服务器的服务器的 FQDN。此属性为单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>此属性是表示受信任服务器的 FQDN 的单值属性。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>此属性指定受信任服务器列表中的服务器的版本号。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>NULL：Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Live Communications Server 2005 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>此属性定义为受信任的服务启用的选项。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>此多值属性包含可分辨名称 (DN) 的列表，这些名称引用受信任的服务对象，如媒体中继身份验证服务。媒体中继身份验证服务（物理上并置于运行 A/V 会议服务的边缘服务器上）必须与池关联才能支持远程用户音频方案。</p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-ServerBL</strong>。</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>此属性是一个整数，它定义用于连接到此 GRUU 服务的端口号。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>此属性是一个字符串值，用于定义它所表示的 GRUU 服务的类型。</p>
<p>有效的 GRUU 服务类型如下：</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>网关</p></li>
<li><p>媒体中继身份验证服务 (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>此属性是一个字符串值，其中包含运行 Lync Server Web 服务的 IIS 的 FQDN。这是一个单值属性。每段的有效值为 63 个字符；整个 FQDN 的有效值为 255 个字符。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags（作废）</p></td>
<td><p>此属性定义对所有用户或联系对象在全局范围启用的各种 UC 选项。此属性为整数类型的位掩码值。每个选项均由位表示。</p>
<p>此属性可能的有效值（和相关位的位置）如下：</p>
<ul>
<li><p>4: UsePerUserUCPolicy（第 2 位）</p></li>
</ul>
<p>设置此位后，将按用户分别定义 UC 策略。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy（作废）</p></td>
<td><p>此单值属性包含管理员已为此用户分配的 UC 策略的可分辨名称 (DN)。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList（作废）</p></td>
<td><p>此属性提供林中承载启用 SIP 的用户的所有域的列表。默认为空列表，表示林中的所有域都已启用 SIP。</p>
<p>有效值为表示各个域的域名的多个字符串。</p></td>
<td><p>Live Communications Server 2005 中的新增类。</p>
<p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>此属性确定当前是否为 Lync Server 启用了用户。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>此多值属性包含格式为“名称=值”的名称/值对的列表。此属性标记为进行全局编录复制。</p></td>
<td><p>Live Communications Server 2005 SP1 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>此属性包含指向位置配置文件对象的可分辨名称 (DN)。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>此属性存储用户策略的名称值对。</p></td>
<td><p>Lync Server 2010 中的新增类。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>这是一个多值属性，包含带二进制值的可分辨名称 (DN_WITH_BINARY) 的列表，这些名称指向不同类型的全局用户策略。二进制值部分则指示 DN 部分所指向的策略的类型。</p>
<p>有效的二进制值如下：</p>
<ul>
<li><p>0x00000001：会议策略</p></li>
<li><p>0x00000002：UC 策略</p></li>
<li><p>0x00000005：状态策略</p></li>
</ul></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>这是 SIP 路由组 ID。相同组中的用户将注册到相同的前端服务器。</p></td>
<td><p>Lync Server 2013 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>这是一个多值属性。此属性留作将来使用。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>此单值属性指向 Web 组件所属的池或 Standard Edition Server。</p>
<p>正向链接：<strong>链接 ID 11028</strong></p>
<p>此正向链接属性相应的反向链接为 <strong>msRTCSIP-WebComponentsServers</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>此属性为可分辨名称的多值列表。此属性包含与此池关联的所有 Web 服务器的列表。</p>
<p>反向链接：<strong>链接 ID 11029</strong></p>
<p>此反向链接相应的正向链接为 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId（作废）</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 中的新增类。</p>
<p>Live Communications Server 2005 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>电话使用此现有 Active Directory 属性指定电话的备用 TCP/IP 地址列表。</p></td>
<td><p>Windows Server 2008 操作系统中的新增属性。</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>此现有 Active Directory 属性由 Lync Server 中的语音组件使用，目的是将呼叫路由至统一消息自动助理和订阅者访问号码，它仅用于联系对象。无条件呼叫转移地址存储在此多值属性中。此帐户专为自动助理和订阅者访问的特定用途而创建。管理员不应修改此帐户的属性。</p></td>
<td><p>Windows 2000 操作系统中的新增属性。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>此现有 Active Directory 多值属性是 Windows 2000 中引入的基本 Active Directory 架构的一部分。此属性包含用户电子邮件的各种 X400、X500 和 SMTP 地址。在 Live Communications Server 2003 及更高版本中，系统会使用“sip:”标记将用户的 SIP URI 添加到此列表中。</p>
<p>下列应用程序从此属性搜索用户的 SIP URI：</p>
<ul>
<li><p>Microsoft Office Outlook 2003 消息和协作客户端</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 操作系统中的新增属性。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>此现有 Active Directory 属性包含用户的电话号码。</p></td>
<td><p>Windows 2000 操作系统中的新增属性。</p></td>
</tr>
</tbody>
</table>

