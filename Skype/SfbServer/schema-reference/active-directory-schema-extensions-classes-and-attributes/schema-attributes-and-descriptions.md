---
title: 架构属性，并在 Skype 业务服务器的描述
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b009df76-9c22-471d-b57a-bda009a98261
description: 本部分介绍用于通过 Skype 业务服务器的所有架构属性。 与属性相关联的类，请参见架构属性由类在 Skype 业务服务器
ms.openlocfilehash: bcb54a33a6a798c7d413decb2aceb3e8857926ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="schema-attributes-and-descriptions-in-skype-for-business-server"></a>架构属性，并在 Skype 业务服务器的描述
 
本部分介绍用于通过 Skype 业务服务器的所有架构属性。 与属性相关联的类，请参阅[通过 Skype 业务服务器中类的架构属性](schema-attributes-by-class.md)。
  
对链接的属性被指定为正向链接或反向链接。 引用另一个对象的属性是一个正向链接;又引用第一个对象的其他对象的属性是反向链接。 正向链接是可更新的、 反向链接是只读的。
  
某些属性具有一个位掩码值。 对于这些特性，由一个位，表示每个设置和显示的十进制值表示的位的位置。 位 0 位的位置开始。 例如，1 （二进制） 是位 0 套和 10000 （二进制） 是 4 位组。 每一位代表一个属性。 以下是一些示例： 
  
- 10000 （二进制） 其十进制值为 16 （也就是说，设置 4 位）。
    
- 100000000 （二进制） 的十进制值为 256 （也就是说，设置 8 位）。
    
- 1100 （二进制） 具有其十进制值为 12 （即设置 2 和第 3 位; 启用由两位数表示的属性）。
    
- 1111000001 （二进制） 的十进制值为 961 （即 0、 6、 7、 8 和 9 位设置，启用这些位的每个属性）。
    
**Skype 业务服务器的架构属性**

|**属性**|**说明**|**注释**|
|:-----|:-----|:-----|
|仅  <br/> |现在的 Active Directory 域服务中的现有属性的**msRTCSIP 池**和**msRTCSIP MonitoringServer**类与关联。 此属性指定池或监视服务器的完全合格的域名称 (FQDN)。 <br/> 每个段的有效值是 63 个字符;整个的 FQDN 的有效值是 255 个字符。  <br/> |Microsoft® Office Live 的测试报告中的新功能。  <br/> |
|msDS SourceObjectDN  <br/> |此属性包含的字符串表示形式中对应于此对象的另一个目录林中的对象的可分辨名称 (DN)。 此特性用于通讯组展开以及自动出勤。 对于 Windows Server 2003 R2 默认 Active Directory 架构中定义了此属性。  <br/> 为了避免要求升级到 Windows Server 2003 R2 的 AD ds，Active Directory 架构准备扩展使用此属性定义的 Windows Server 2003 架构。  <br/> |Microsoft Office 通信服务器 2007年中的新功能。  <br/> |
|msExchUCVoiceMailSettings  <br/> |此多值的属性包含语音邮件设置。 此特性被共享与 Exchange 统一消息 (UM)。  <br/> |Microsoft Lync Server 2010 中的新功能。  <br/> |
|msExchUserHoldPolicies  <br/> |此多值属性包含标识符的保留适用于用户的策略。 保留策略的暂停的持续时间内保留该用户的邮箱项目。 此属性是与 Exchange 2013 共享。  <br/> |Lync Server 2013 中的新功能。  <br/> |
|msRTCSIP AcpInfo  <br/> |此属性存储用户的音频会议提供商信息。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP ApplicationDestination  <br/> |此属性指向受信任的服务应用程序联系人条目。  <br/> |Microsoft Office 通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationList  <br/> |此属性包含在应用程序服务器上承载应用程序的列表。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationOptions  <br/> |此属性指定应用程序联系人的选项。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationPrimaryLanguage  <br/> |此属性包含应用程序联系人的主要语言。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationSecondaryLanguages  <br/> |此多值属性包含应用程序联系人的第二语言。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerBL  <br/> |此属性包含属于此池的应用程序服务器的列表。 相应的正向链接到此链接属性为**msRTCSIP ApplicationServerPoolLink**。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerPoolLink  <br/> |此特性将指向此应用程序服务器所属的池。 这是正向链接。 相应的向后链接是**msRTCSIP ApplicationServerBL**。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ArchiveDefault （已过时）  <br/> |-  <br/> |测试报告中的新功能。  <br/> 在办公室通信服务器 2007年中已过时。  <br/> |
|msRTCSIP ArchiveDefaultFlags （已过时）  <br/> | 此属性指定的全局默认设置，存档所有用户通信对林边界内。 这是由存档代理层实施的。 此属性的值的范围是，如下所示： <br/> **TRUE**： 存档所有用户  <br/> **FALSE**： 不存档所有用户  <br/>  此特性全局控制，在林边界内对内部网络中的用户通信存档方式。 <br/> **实时通信服务器 2005年行为 （现在已停用）** <br/>  此属性的值的范围是，如下所示： <br/>  0： 存档消息正文 [0 位] <br/>  1： 不存档消息正文 [0 位] <br/> **通信服务器 2007 office 的行为** <br/>  此属性的值的范围是，如下所示： <br/>  0: ArchiveFederationDefaultWithoutBody （退休） <br/>  1-2: ArchiveInternalCommunications <br/>  3-4: ArchiveFederatedCommunications <br/>  5: RecordPresenceRegistrations <br/>  6: RecordIMCallDetails <br/>  7: RecordGroupIMCallDetails <br/>  8: RecordFileTransferInstances <br/>  9: RecordAudioCallDetails <br/>  10: RecordVideoCallDetails <br/>  11: RecordRemoteAssistanceCallDetails <br/>  12: RecordApplicationSharingDetails <br/>  13: RecordMeetingInstantiations <br/>  14: RecordMeetingJoins <br/>  15: RecordDataJoins <br/>  16: RecordAVJoins <br/> |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ArchiveFederationDefault （已过时）  <br/> |-  <br/> |测试报告中的新功能。  <br/> 在办公室通信服务器 2007年中已过时。  <br/> |
|msRTCSIP ArchiveFederationDefaultFlags （已过时）  <br/> |-  <br/> |测试报告中的新功能。  <br/> 在办公室通信服务器 2007年中已过时。  <br/> |
|msRTCSIP ArchivingEnabled  <br/> | 此特性是用作一个位字段和控件，是否单个用户的通信进行存档，这是一个整数。 此控件是由存档代理层强制执行。 它被标记为全局编录复制。 <br/>  此属性的范围是特定于单个用户或联系人。 在 Skype 业务服务器的有效值 （和相关联的位的位置） 如下所示： <br/>  0： 不存档 （设置任何位） <br/>  1： 退休 （位位置 0） <br/>  2： 退休 （位位置 1） <br/>  4： 存档内部通信 （位位置 2） <br/>  8： 存档联盟的通信 （位位置 3） <br/>  以前 Live Communications 服务器 2005年中的有效值如下所示： <br/>  0:Use 的默认值由**msRTCSIP ArchiveDefault**和**msRTCSIP ArchiveFederation**的优先顺序如下： <br/>  1： 存档 <br/>  2： 不自动存档 <br/>  3： 存档但不包括消息正文 <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP ArchivingServerData （已过时）  <br/> |此属性保留供将来使用。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ArchivingServerVersion （已过时）  <br/> | 此属性定义的存档服务的版本。 此属性是每个官方产品版本递增 monotonously 递增整数类型。 可能的有效值包括： <br/>  未定义： 实时通信服务器 2003 <br/>  Live Communications Server 2005 <br/>  Live Communications Server 2005 SP1 <br/>  3： 办公室通信服务器 2007年 <br/>  4： 办公室通信服务器 2007 R2 <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP BackEndServer  <br/> |此属性指定池的后端服务器的 FQDN。 由于只能有一个后端服务器，每个池，这是一个单值属性。  <br/> 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP ConferenceDirectoryHomePool  <br/> |此属性包含的池的主持会议目录标识符。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ConferenceDirectoryId  <br/> |此属性包含会议目录的标识符。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ConferenceDirectoryTargetPool  <br/> |此属性包含会议目录移动到该池的标识符。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP 默认  <br/> |此布尔值特性定义的电话惯例是否为默认用法。 如果此属性设置为**TRUE**，电话惯例是默认用法，不能由管理员删除。 如果此属性设置为**FALSE**，则可以删除使用率。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP DefaultCWAExternalURL  <br/> |此属性标识组织外部用户的 URL。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP DefaultCWAInternalURL  <br/> |此属性标识在组织内的用户的 URL。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP DefaultLocationProfileLink （已过时）  <br/> |此单值属性包含分配给它的位置配置文件类对象的可分辨的名称 (DN)。  <br/> 前向链接：**链接 ID 11036** <br/> 相应的向后链接是**msRTCSIP ServerReferenceBL**。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefaultPolicy （已过时）  <br/> |此布尔值特性指定策略是默认策略。 该策略被设置为**TRUE**时的默认策略。  <br/> |办公通信服务器 2007年中的新增功能  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefaultRouteToEdgeProxy （已过时）  <br/> |此属性指定任一边缘服务器运行访问边缘服务，如果它可以直接访问或硬件负载平衡器的运行服务访问边缘服务器池的 FQDN。 如果运行服务可以访问只能通过一个或多个控制器的访问边缘服务器，此特性指定 FQDN 和控制器或硬件负载平衡器控制器池提供服务的端口号 （可选）。  <br/> 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefaultRouteToEdgeProxyPort （已过时）  <br/> |此属性表示用于连接到运行访问边缘服务的服务器的端口号。  <br/> 有效的值是一个整数值，指定要使用的端口。 默认值为 5061。  <br/> |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefPresenceSubscriptionTimeout （已过时）  <br/> |此属性表示默认状态订阅超时期限。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefRegistrationTimeout （已过时）  <br/> |此属性表示默认注册超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DefRoamingDataSubscriptionTimeout （已过时）  <br/> |此属性表示默认漫游数据订阅超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DeploymentLocator  <br/> |此特性用于拆分域拓扑中，包含完全限定的域名称 (FQDN)。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP 说明 （已过时）  <br/> |此单值 UNICODE 字符串属性包含此电话路由或规范化规则的友好说明。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP DomainData  <br/> |此属性保留供将来使用。  <br/> |-  <br/> |
|msRTCSIP 域名  <br/> |此属性表示为注册配置域。  <br/> |-  <br/> |
|msRTCSIP EdgeProxyData  <br/> |此属性保留供将来使用。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP EdgeProxyFQDN  <br/> |此属性指定运行访问边缘服务的服务器的 FQDN。  <br/> 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP EnableBestEffortNotify （已过时）  <br/> |此属性可控制是否服务器会生成最佳工作通知 (BENOTIFY) 请求，而不是通知的请求，以响应来自客户端订阅请求。 BENOTIFY 是订阅通知握手的性能增强扩展服务器会生成 BENOTIFY 请求，而不是常规的通知请求。 性能优势是 BENOTIFY 请求不通知请求也一样需要一个 200 OK 响应来自客户端。  <br/> 有效的值为**真**或**假**。  <br/> > [!NOTE]> 实时通信服务器 2003年不支持 BENOTIFY 请求。 与编写的实时通信服务器 2003年服务器 API Live Communications 服务器 2005年和第三方服务器上运行的服务器应用程序交互操作，可以通过将其值设置为**FALSE**禁用 BENOTIFY 请求。 BENOTIFY 不是当前 IETF （互联网工程任务组） SIP 标准化过程的一部分。           |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP EnableFederation （已过时）  <br/> | 此属性是一种 IT 管理员使用配置是否允许用户与其他组织中的用户进行通信的全局参数。 这样，管理员可以覆盖个别用户的**FederationEnabled**属性。 此特性可用于帮助保护内部网络不受互联网的攻击，可能由病毒、 蠕虫或有目标的攻击，在该公司。 <br/>  有效的值 （和相关联的位的位置） 如下所示： <br/>  1： 启用公用 IM 连接 （位位置 0） <br/>  2： 保留 （位位置 1） <br/>  4： 保留 （位位置 2） <br/>  8： 保留 （位位置 3） <br/>  16： 远程呼叫控制已启用-电话 （位位置 4） <br/>  64: AllowOrganizeMeetingWithAnonymousParticipants (允许用户匿名用户邀请到会议 （位位置 6） <br/>  128: UCEnabled （允许用户为统一通信） （位位置 7） <br/>  256: EnabledForEnhancedPresence （启用公用 IM 连接的用户） （位位置 8） <br/>  512: RemoteCallControlDualMode （位位置 9） <br/> |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP EnterpriseServices  <br/> |此属性指示是否在给定的服务器上加载企业服务。  <br/> |-  <br/> |
|msRTCSIP ExtensionData  <br/> |此属性保留供将来使用。  <br/> |-  <br/> |
|msRTCSIP ExternalAccessCode  <br/> |此属性包含外部访问的拨号代码。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP FederationEnabled  <br/> |此属性可控制是否将单个用户启用联盟。 它是由企业服务层强制执行。 它被标记为全局编录复制。  <br/> 有效的值为**真**或**假**。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP FrontEndServers  <br/> |此属性是多值的列表的所有企业版服务器与池相关联的域名。  <br/> 背景链接：**链接 ID 11023** <br/> 此后退链接到相应的正向链接是**msRTCSIP PoolAddress**。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP-网关 （已过时）  <br/> |此多值的字符串属性包含网关和端口 （每个网关） 的列表。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP GlobalSettingsData （已过时）  <br/> |此属性存储名称： 值对。 已定义名称： 值对的是**允许轮询状态**设置。 <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP GroupingID  <br/> |此属性是一组用于对组地址簿中的条目的唯一标识符。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP HomeServer （已过时）  <br/> |-  <br/> |2003 中的新增实时通信服务器 （未使用）。  <br/> 在测试报告中已过时。  <br/> |
|msRTCSIP HomeServerString （已过时）  <br/> |-  <br/> |实时通信 Server 2003 中的新增功能。  <br/> 在测试报告中已过时。  <br/> |
|msRTCSIP HomeUsers （已过时）  <br/> |-  <br/> |2003 中的新增实时通信服务器 （未使用）。  <br/> 在测试报告中已过时。  <br/> |
|msRTCSIP InternetAccessEnabled  <br/> |此属性可控制是否为单个用户启用外部用户访问。 它是由企业服务层强制执行。 它被标记为全局编录复制。  <br/> 有效的值为**真**或**假**。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP IsMaster （已过时）  <br/> |-  <br/> |实时通信 Server 2003 中的新增功能  <br/> 在测试报告中已过时。  <br/> |
|msRTCSIP 行  <br/> |此单值属性中包含的设备 ID （SIP URI 或 TEL URI 的电话用户控件） 使用的业务客户端电话服务 Skype。 此属性标记为全局编录复制并编制索引。 如果用户启用企业语音，此属性就会存储用户的电话号码的 E.164 标准化的版本。  <br/> |Microsoft® Office Live 通信服务器 2005 sp1 中的新增功能  <br/> |
|msRTCSIP LineServer  <br/> |此单值属性包含 CSTA SIP 网关服务器的 SIP URI。 此属性标记为全局编录复制，但未被编入索引。  <br/> |Microsoft® Office Live 通信服务器 2005 sp1 中的新增功能  <br/> |
|msRTCSIP LocalNormalizationData （已过时）  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP LocalNormalizationLinks （已过时）  <br/> |此多值的属性包含与此位置配置文件相关联的本地规范化可分辨名称 (DN) 的列表。 此属性的类型是一个二进制的 DN。 没有位置配置文件与本地的规范化规则之间的一对多关系。 必须由管理员指定的顺序维护本地规范化 DNs 的列表中的顺序。 由二进制，DN 指定顺序索引的二进制部分维护保留的订单。  <br/> 前向链接：**链接 ID 11034** <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP LocationProfileBL**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP LocalNormalizationOptions  <br/> |此属性包含的规范化规则的选项的列表。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP LocationName （已过时）  <br/> |此单值属性包含指示表示此配置文件的位置的位置配置文件的友好名称。 因为可能有多个位置配置文件，管理员需要一种方法来区分不同的配置文件。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP locationProfileBL （已过时）  <br/> |此多值的属性包含位置配置文件可分辨名称的列表。 此特性指定上一页链接到一个或多个位置配置文件。  <br/> 背景链接：**链接 ID 11035** <br/> 此属性对应于正向链接**msRTCSIP LocalNormalizationLinks**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP LocationProfileData （已过时）  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP LocationProfileOptions  <br/> |此属性包含位置配置文件的选项。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP MappingContact  <br/> |此多值属性包含应用程序的联系人的列表。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP MappingLocation  <br/> |此多值属性保存位置配置文件的列表。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP MaxNumOutstandingSearchPerServer （已过时）  <br/> |此属性表示的最大未处理搜索每个服务器的请求数。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MaxNumSubscriptionsPerUser （已过时）  <br/> |该属性表示每个用户的订阅数。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MaxPresenceSubscriptionTimeout （已过时）  <br/> |此属性表示的最大订阅超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MaxRegistrationsTimeout （已过时）  <br/> |此属性表示的最大注册超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MaxRoamingDataSubscriptionTimeout （已过时）  <br/> |此属性表示最大的漫游数据订阅超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MCUData  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactoryAddress  <br/> |此属性是服务控制点属性下指定的链接返回到其所属的多点控制单元 (MCU) 工厂的计算机类。 为每个 Microsoft MCU 创建此服务控制点和特性。 每个 Microsoft MCU 必须找到其所属，以便从其检索池级设置的池后端服务器。  <br/> 此属性的值是 MCU 工厂的可分辨的名称 (DN)。 这是一个单值属性且标记为全局编录复制。  <br/> 前向链接：**链接 ID 11026** <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP MCUServers**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactoryData  <br/> | 这是一个多字符串保留的属性。 设置存储在此特性中表示为名称 = 值对。 当前定义的名称 = 的值对： <br/>  FactoryURL = \<URL\> <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactoryPath  <br/> |这是一个单值属性包含单个 MCU 工厂与池相关联的可分辨的名称 (DN)。  <br/> 前向链接：**链接 ID 11024** <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP PoolAddresses**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactoryProviderID  <br/> |此属性是单值指定的 MCU 工厂提供的 GUID 字符串。 MCU 的工厂过程根据 GUID 值，确定是否服务这种 MCU 类型。 如果 GUID 值**{F0810510-424F-46ef-84FE-6CC720DF1791}**，然后 MCU 的工厂过程 （可通过 Lync Server 中的默认值） 将处理它。 对于任何其他 GUID 值，MCU 工厂处理流程将不服务 MCU 类型。 <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUServers  <br/> |此属性是多值的列表的可分辨名称 (DN)。 此属性包含相同的类型和供应商与此 MCU 工厂相关联的所有 MCU 服务器的列表。 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> 背景链接： 链接 ID 11027  <br/> 此后退链接到相应的正向链接是**msRTCSIP MCUFactoryAddress**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUType  <br/> | 此属性是指定 MCU 可以处理中的单值的字符串。 <br/>  支持有效类型包括： <br/>  会议 <br/>  音频-视频 <br/>  聊天 <br/>  电话 conf <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUVendor  <br/> |此属性是单值，它指定 MCU 供应商的名称的字符串。 所有 Microsoft Mcu 将都指定此特性，将**微软公司**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MeetingFlags （已过时）  <br/> | 此属性可以定义不同的会议选项的所有用户的全局启用或联系人对象。 此属性是整数类型的位掩码值。 <br/>  有效的值 （和相关联的位的位置） 如下所示： <br/>  0: AllowOrganizeMeetingWithAnonymousParticipants 为无 （不允许用户匿名用户邀请到会议） （没有设置位） <br/>  4: AllowOrganizeMeetingWithAnonymousParticipants 是每个人都 （允许所有用户匿名用户邀请到会议） （位位置 2） <br/>  8: AllowOrganizeMeetingWithAnonymousParticipants 是 UsePerUserSetting （允许用户邀请到会议基于每个用户设置匿名用户） （位位置 3） <br/>  16: （会议策略定义每个用户） 的 UserPerUserMeetingPolicy （位位置 4） <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MeetingPolicy （已过时）  <br/> |此属性指定的可分辨的名称 (DN) 的策略管理员已分配给此用户作为单值属性。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MinPresenceSubscriptionTimeout （已过时）  <br/> |此属性表示最小状态订阅超时窗口。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MinRegistrationTimeout （已过时）  <br/> |此属性表示的最小注册超时窗口。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MinRoamingDataSubscriptionTimeout （已过时）  <br/> |此属性表示小的漫游数据订阅超时时间。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MirrorBackEndServer  <br/> |此属性用于存储镜像的 SQL Server 后端前端池使用。  <br/> |Lync Server 2013 中的新功能。  <br/> |
|msRTCSIP MobilityFlags  <br/> |此属性包含选项和定义移动设置的标志。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP MobilityPolicy  <br/> |此属性包含一个移动策略对象的 DN。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP NumDevicesPerUser （已过时）  <br/> |此属性表示允许的用户可以注册的 SIP 通信和订阅状态的设备的数量。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP OptionFlags  <br/> | 此属性指定的选项已启用的用户或联系人对象。 此属性是一个整数类型的位掩码值。 一位代表每个选项。 此属性标记为全局编录复制。 <br/>  有效的值 （和相关联的位的位置） 如下所示： <br/>  1： 启用公共即时消息 (IM) 连接 （位位置 0） <br/>  2： 保留 （位位置 1） <br/>  4： 保留 （位位置 2） <br/>  8： 保留 （位位置 3） <br/>  16： 远程呼叫控制已启用-电话 （位位置 4） <br/>  64: AllowOrganizeMeetingWithAnonymousParticipants (允许用户匿名用户邀请到会议 （位位置 6） <br/>  128: UCEnabled （允许用户为 UC） （位位置 7） <br/>  256: EnabledForEnhancedPresence （启用公用 IM 连接的用户） （位位置 8） <br/>  512: RemoteCallControlDualMode （位位置 9） <br/> |实时通信服务器 2005 sp1 中的新增功能。  <br/> |
|msRTCSIP OriginatorSID  <br/> |资源和中央林拓扑中使用此属性来启用单一登录时用户的 ObjectSID 从 Windows NT 服务器主体帐户复制到此属性的相应用户或联系在中央目录林中的资源的对象。 在使用此属性或用户的 ObjectSID AD DS 用户 Skype 业务服务器的搜索。 此属性标记为全局编录复制。  <br/> |-  <br/> |
|msRTCSIP OwnerUrn  <br/> |此属性是所有者的应用程序联系人的统一资源名称 (URN)。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP 模式 （已过时）  <br/> |此单值字符串属性包含用于匹配的拨号数字为 E.164 格式模式。 如果拨号号码与此模式匹配，则将转换应用到拨叫的号码。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PhoneRouteBL （已过时）  <br/> |此多值的属性包含电话路由可分辨名称 (DN) 的列表。 此属性指定一个或多个电话路由到上一页链接。  <br/> 背景链接：**链接 ID 11033** <br/> 此属性对应于正向链接**msRTCSIP RouteUsageLinks**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PhoneRouteData （已过时）  <br/> |此属性保留供将来使用。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PhoneRouteName （已过时）  <br/> |此单一的值的 UNICODE 字符串属性指定电话路由的友好名称，所以管理员可以很容易地引用它。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PhoneUsageData （已过时）  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PolicyContent （已过时）  <br/> |此属性是单值的 Unicode 字符串。 该字符串属性包含在 XML 格式中的策略定义。 XML 架构定义是跨不同的策略类型，常见，只设置会因每个策略类型而异。  <br/> XML 架构定义 (XSD) 定义如下：  <br/> ```<?xml version="1.0" encoding="utf-8"?><xs:schema id="instance" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  <xs:element name="instance" msdata:IsDataSet="true">    <xs:complexType>      <xs:choice maxOccurs="unbounded">        <xs:element name="property" nillable="true">          <xs:complexType>            <xs:simpleContent msdata:ColumnName="property_Text" msdata:Ordinal="1">              <xs:extension base="xs:string">                <xs:attribute name="name" type="xs:string" />              </xs:extension>            </xs:simpleContent>          </xs:complexType>        </xs:element>      </xs:choice>    </xs:complexType>  </xs:element></xs:schema>```|办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PolicyData （已过时）  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PolicyType （已过时）  <br/> | 此单值 Unicode 字符串属性包含的策略类型。 有效的策略类型如下所示： <br/>  会议 <br/>  电话服务 <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PoolAddress  <br/> |此特性指定的链接返回到计算机所属的池。 无论计算机是否正在运行标准版或企业版设置了该属性。 此属性标记为全局编录复制。  <br/> 有效的值为该池的域名。  <br/> 前向链接：**链接 ID 11022** <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP FrontEndServers**。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP PoolAddresses  <br/> |这是一个多值的属性包含的 MCU 工厂与之关联的池的可分辨名称 (DN) 的列表。  <br/> 背景链接：**链接 ID 11025** <br/> 此后退链接到相应的正向链接是**msRTCSIP MCUFactoryPath**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP PoolData  <br/> |此属性保留供将来使用。  <br/> |实时通信服务器 2005 sp1 中的新增功能。  <br/> |
|msRTCSIP PoolDisplayName  <br/> |此属性指定的池，通过管理控制台显示的任意名称。 管理员可以更改此名称。  <br/> 有效的值是一个字符串，表示池的名称。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP PoolDomainFQDN  <br/> |此属性是单值的字符串值。 此特性的值时存在，表示该池的 FQDN 域如果管理员想要使用不符合 Active Directory 域结构 （例如，对 SIP 在其中创建前端池的 FQDN 创建前端池命名空间中退出来自域名系统 (DNS) 命名空间）。  <br/> 我们建议为该池所在的 Active Directory 域将前端池域 FQDN 映射到域中的名称部分。 因此，没有值时在此属性中，**仅**特性的指示，FQDN 将默认为 Active Directory 域名结构，前端池存在。 <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP PoolFunctionality  <br/> | 多值的列表域的名称的所有 Skype 业务服务器的企业版服务器与池相关联。 整数类型的此属性可以定义该池是否能即时消息 (IM) 和在线状态以及会议。 <br/>  可能有效的值类型如下所示： <br/>  未定义： IM 和状态显示服务 （实时通信服务器 2005年和 2003年） <br/>  1: IM 和状态显示服务 (Skype 业务服务器) <br/>  2: IM 和状态显示以及会议服务 (Skype 业务服务器) <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP PoolType  <br/> | 此属性指定是否在服务器标准版或企业版服务器运行服务器池。 此属性是一个整数类型的位掩码值。 一位代表每个选项。 <br/>  有效的值 （和相关联的位的位置） 如下所示： <br/>  1： 标准版服务器、 主机用户 （位位置 0） <br/>  2： 企业版服务器、 主机用户 （位位置 1） <br/>  4： 标准版服务器、 主机应用程序 （位位置 2） <br/>  8： 企业版服务器、 主机应用程序 （位位置 3） <br/>  由于 Lync 服务器不支持主机仅应用程序池，唯一有效的值如下所示： <br/>  5： 标准版服务器、 主机用户和应用程序 （位位置 0 和 2） <br/>  10： 企业版服务器、 主机用户和应用程序 （位位置 1 和 3） <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP PoolVersion  <br/> | 此属性定义的池版本。 它是每个主要产品版本递增整数类型。 <br/>  可能有效的值类型如下所示： <br/>  0： 实时通信服务器 2003年 <br/>  1： 实时测试报告 <br/>  2： 实时通信服务器 2005 sp1 <br/>  3： 办公室通信服务器 2007年 <br/>  4： 办公室通信服务器 2007 R2 <br/>  5: Lync Server 2010 <br/> |实时通信服务器 2005 sp1。  <br/> |
|msRTCSIP PresenceFlags  <br/> |此属性包含选项和定义展示形式设置的标志。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP PresencePolicy  <br/> |此属性包含一个状态策略对象的 DN。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP PrimaryHomeServer  <br/> |此特性允许用户或联系人的 SIP 消息。 它被添加到联系人类，因为在中央林拓扑中，联系人对象，而非用户对象，都启用了 SIP。  <br/> 有效的值为标准版或企业版前端用户所在的池 DN。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP PrimaryUserAddress  <br/> |此属性包含给定用户的 SIP 地址。  <br/> |-  <br/> |
|msRTCSIP PrivateLine  <br/> |此属性包含的专用电话线路设备的设备 ID。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP 可穿绕  <br/> |此属性是布尔属性用于确定是否授权 Skype 业务服务器路由到此服务使用 GRUU 地址。 如果此值设置为**TRUE**，Skype 业务服务器被授权可将路由到该服务。 如果此值设置为**FALSE**，Skype 业务服务器未授权可将路由到该服务。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP RouteUsageAttribute （已过时）  <br/> |此单值 UNICODE 字符串属性定义限定的电话路由使用的属性。 选定的电话路由决定基于两个元素： 使用特性为电话路由和调用方分配的允许策略使用属性。 第一个电话路由匹配调用方的允许的用法使用属性处于选中状态。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP RouteUsageLinks （已过时）  <br/> |此多值可分辨的名称 (DN) 属性包含路由使用可分辨名称的列表。  <br/> 前向链接：**链接 ID 11032** <br/> 此属性是与相应的后台链接**msRTCSIP PhoneRouteBL**的前向链接。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP RoutingPoolDN  <br/> |此属性包含指向池 MCU 或受信任服务的所有 SIP 通信，都解决对此必须经过的 DN。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP RuleName （已过时）  <br/> |此单值 UNICODE 字符串属性指定友好名称的规范化规则，因此管理员可以轻松地引用它。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP SchemaVersion  <br/> |此属性表示当前已在组织中部署的架构版本。  <br/> |-  <br/> |
|msRTCSIP SearchMaxRequests （已过时）  <br/> |此特性将限制用户搜索联系人使用 Communicator 时从目录搜索中返回的搜索结果数。 此属性将覆盖客户端提供的值。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP SearchMaxResults （已过时）  <br/> |此属性限制返回的搜索请求数。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ServerBL  <br/> |此多值的属性是反向链接包含可分辨名称 (DN) 的列表。 这些 DNs 指向池或**TrustedService**对象。 <br/> 此属性对应于正向链接**msRTCSIP TrustedServiceLinks**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP ServerData  <br/> |此属性保留供将来使用。  <br/> |-  <br/> |
|msRTCSIP ServerReferenceBL （已过时）  <br/> |此多值的属性包含可分辨名称的列表。 这些可分辨的名称是引用其他可以分配一个默认位置配置文件的服务器对象的反向链接。  <br/> 背景链接：**链接 ID 11037** <br/> 此后退链接到相应的正向链接是**msRTCSIP DefaultLocationProfileLink**。  <br/> 此链接属性仅引用池和中介服务器。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ServerVersion  <br/> | 此属性可以定义的服务器的版本信息。 此版本号将应用于所有服务器角色。 它是每个官方产品版本递增 monotonously 递增整数。 <br/>  有效的可能值如下所示： <br/>  未定义： 实时通信服务器 2003 <br/>  Live Communications Server 2005 <br/>  Live Communications Server 2005 SP1 <br/>  3： 办公室通信服务器 2007年 <br/>  4： 办公室通信服务器 2007 R2 <br/>  5: Lync Server 2010 <br/>  6: Lync Server 2013 <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP SourceObjectType  <br/> | 整数类型的此单值属性指定的对象的类型， **msDS SourceObjectDN**点，如下所示： <br/>  为空 | 0x00000001： 来自不同的林代表 Windows NT 服务器用户主体对象 <br/>  下列属性表示从不同林中的通讯组展开组类型： <br/>  0X00000002: ADS_GROUP_TYPE_GLOBAL_GROUP <br/>  0X00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP <br/>  0X00000004: ADS_GROUP_TYPE_LOCAL_GROUP <br/>  0X00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP <br/>  0X80000000: ADS_GROUP_TYPE_SECURITY_ENABLED <br/>  0x90000000： 从同一目录林中或者不同的林代表自动助理或订阅服务器上访问对象 <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP SubscriptionAuthRequired （已过时）  <br/> |-  <br/> |实时通信 Server 2003 中的新增功能。  <br/> 在测试报告中已过时。  <br/> |
|msRTCSIP TargetHomeServer  <br/> |此特性允许您的用户或联系人对象移动到另中一个 Skype 业务服务器池。 将此特性添加到联系人类，因为在中央林拓扑中，联系人对象，而非用户对象，都启用了 SIP。  <br/> 有效的值是用户将被移到前端池的目标标准版服务器的 DN。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP TargetPhoneNumber （已过时）  <br/> |此单值字符串属性包含电话号码模式或路由到指定的网关在**msRTCSIP 网关**定义的范围。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP TargetUserPolicies  <br/> |此属性存储业务服务器用户的 Skype 目标策略的名称-值对。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP TenantId  <br/> |此属性存储组织的唯一标识符。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP 翻译 （已过时）  <br/> |此属性由 Lync 服务器的语音功能，包含要拨叫的号码，接通翻译字符串，如果找到匹配的。  <br/> |办公通信服务器 2007年中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP TrustedMCUData  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedMCUFQDN  <br/> |此属性是一个字符串值，包含 MCU 的 FQDN。 这是一个单值属性。 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedProxyData  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedProxyFQDN  <br/> |此属性是服务器的一个字符串值，包含运行代理服务器的 FQDN。 此属性是单值。 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedServerData  <br/> |此属性保留供将来使用。  <br/> |-  <br/> |
|msRTCSIP TrustedServerFQDN  <br/> |此属性是服务器的单值属性表示受信任的 FQDN。  <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP TrustedServerVersion  <br/> | 此属性指定受信任的服务器列表中服务器的版本号。 <br/>  有效的可能值如下所示： <br/>  空： 实时通信服务器 2003 <br/>  2： 实时测试报告 <br/>  3： 办公室通信服务器 2007年 <br/>  4： 办公室通信服务器 2007 R2 <br/>  5: Lync Server 2010 <br/>  6: Lync Server 2013 <br/> |测试报告中的新功能。  <br/> |
|msRTCSIP TrustedServiceFlags  <br/> |该属性定义为受信任服务启用的选项。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP TrustedServiceLinks  <br/> |此多值的属性包含引用受信任的服务对象，例如媒体中继身份验证服务的可分辨名称 (DN) 的列表。 媒体中继身份验证服务 (运行 A 的边缘服务器上物理地并入 / V 会议服务) 必须与一个池来支持远程用户的音频方案相关联。  <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP ServerBL**。  <br/> |统一通信  <br/> |
|msRTCSIP TrustedServicePort  <br/> |此属性是一个整数，它定义用来连接到此 GRUU 服务的端口号。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedServiceType  <br/> | 此属性是一个字符串值，定义了它所代表的 GRUU 服务的类型。 <br/>  有效的 GRUU 服务类型如下所示： <br/>  MediationServer <br/>  网关 <br/>  媒体中继 (MRAS) 的身份验证服务 <br/>  QoSM <br/>  msRTCSIP UserExtension CWA <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedWebComponentsServerData  <br/> |此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedWebComponentsServerFQDN  <br/> |此属性是一个字符串值，包含业务服务器 Web 服务运行 Skype 的 IIS 服务器的 FQDN。 这是一个单值属性。 每个段的有效值是 63 个字符;整个 fqdn 有效的值为 255 个字符。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP UCFlags （已过时）  <br/> | 此属性可以定义不同的 UC 选项来全局启用对所有用户或联系人对象。 此属性是整数类型的位掩码值。 每个选项都表示有点的存在。 <br/>  可能有效的值 （和关联的位的位置） 如下所示： <br/>  4: UsePerUserUCPolicy （位位置 2） <br/>  当这位被设置时，UC 策略定义每个用户。 <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP UCPolicy （已过时）  <br/> |此单值属性包含的 UC 策略的管理员已分配给此用户的可分辨的名称 (DN)。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP UserDomainList （已过时）  <br/> |此属性在承载启用 SIP 的用户提供一个目录林中的所有域的列表。 默认值是一个空列表，表示目录林中的所有域启用 SIP 的。  <br/> 有效值为多个字符串表示单个域的域名。  <br/> |测试报告中的新功能。  <br/> Lync Server 2010 中的过时。  <br/> |
|msRTCSIP UserEnabled  <br/> |此属性确定用户当前是否启用为 Skype 业务服务器。  <br/> |-  <br/> |
|msRTCSIP UserExtension  <br/> |此多值的属性包含列表的名称 / 值对的格式为"名称 = 值。" 此属性标记为全局编录复制。  <br/> |实时通信服务器 2005 sp1 中的新增功能。  <br/> |
|msRTCSIP UserLocationProfile  <br/> |此属性包含指向一个位置配置文件对象的可分辨的名称 (DN)。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP UserPolicies  <br/> |此属性存储用户策略的名称-值对。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP UserPolicy  <br/> | 这是多值的属性包含指向的不同类型的全局用户策略使用的二进制文件 (DN_WITH_BINARY) 的可分辨名称的列表。 二进制的部分指示的策略的 DN 部分所指向的类型。 <br/>  有效的二进制值如下所示： <br/>  0x00000001： 会议策略 <br/>  0x00000002： 统一通信策略 <br/>  0x00000005： 状态策略 <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP UserRoutingGroupId  <br/> |这是 SIP 路由组 id。 同一组中的用户将注册到同一前端服务器。  <br/> |Lync Server 2013 中的新功能。  <br/> |
|msRTCSIP WebComponentsData  <br/> |这是一个多值的属性。 此属性保留供将来使用。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP WebComponentsPoolAddress  <br/> |此单值属性指向的池或 web 组件属于标准版服务器。  <br/> 前向链接：**链接 ID 11028** <br/> 对此的正向链接属性的相应后台链接是**msRTCSIP WebComponentsServers**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP WebComponentsServers  <br/> |此属性是多值的列表的可分辨名称。 此属性包含与该池相关联的所有 Web 服务器的列表。  <br/> 背景链接：**链接 ID 11029** <br/> 此后退链接到相应的正向链接是**msRTCSIP WebComponentsPoolAddress**。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP WMIInstanceId （已过时）  <br/> |-  <br/> |实时通信 Server 2003 中的新增功能。  <br/> 在测试报告中已过时。  <br/> |
|OtherIPPhone  <br/> |电话服务使用此现有活动目录属性以指定列表中的可选 TCP/IP 地址电话。  <br/> |Windows Server 2008 操作系统中的新功能。  <br/> |
|PhoneOfficeOther  <br/> |此现有活动目录属性用于通过 Skype 语音组件业务服务器的联系人对象，路由调用统一邮件自动助理和订阅者访问号码。 无条件的呼叫转发地址存储在此多值属性。 自动助理的特定目的和订阅者访问创建此帐户。 不应由管理员修改此帐户的属性。  <br/> |Windows 2000 操作系统中的新功能。  <br/> |
|代理地址  <br/> | 此现有的 Active Directory 多值的属性是基在 Windows 2000 中引入的 Active Directory 架构的一部分。 此属性包含用户的电子邮件的各种 X400、 X500 和 SMTP 地址。 在实时通信服务器 2003年及更高版本，用户的 SIP URI 添加到此列表中，使用"sip:"标记。 <br/>  以下应用程序中搜索该属性从用户的 SIP URI: <br/>  Microsoft Office Outlook 2003年消息传递和协作客户端 <br/>  Microsoft Office SharePoint Server 2007 <br/> |Windows 2000 操作系统中的新功能。  <br/> |
|TelephoneNumber  <br/> |此现有活动目录属性包含用户的电话号码。  <br/> |Windows 2000 操作系统中的新功能。  <br/> |
   

