---
title: Skype 业务服务器中的类的架构属性
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
description: 本节列出了每个 Skype Business Server 类和可以包含在其他类的类中可包含的架构属性。 有关所有类及其说明的列表，请参阅架构类和 Skype 中的业务服务器的说明。 有关所有属性及其说明的列表，请参阅架构属性和 Skype 中的业务服务器的说明。
ms.openlocfilehash: a2dc6ee09730c1245a3242f88ad25ad07f9b582a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213366"
---
# <a name="schema-attributes-by-class-in-skype-for-business-server"></a>Skype 业务服务器中的类的架构属性
 
本节列出了每个 Skype Business Server 类和可以包含在其他类的类中可包含的架构属性。 有关所有类及其说明的列表，请参阅[架构类和 Skype 业务服务器中的说明](schema-classes-and-descriptions.md)。 所有属性及其说明的列表，请参阅[架构属性和 Skype 业务服务器中的说明](schema-attributes-and-descriptions.md)。
  
## <a name="attributes-by-class"></a>按类分组的属性

|**类**|**可包含以下属性**|
|:-----|:-----|
|联系人  <br/> |Msds-sourceobjectdn 所  <br/> msRTCSIP AcpInfo  <br/> msRTCSIP ApplicationDestination  <br/> msRTCSIP ApplicationOptions  <br/> msRTCSIP ApplicationPrimaryLanguage  <br/> msRTCSIP ApplicationSecondaryLanguages  <br/> msRTCSIP ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP FederationEnabled  <br/> msRTCSIP GroupingID  <br/> msRTCSIP InternetAccessEnabled  <br/> msRTCSIP 行  <br/> msRTCSIP LineServer  <br/> msRTCSIP OptionFlags  <br/> msRTCSIP OriginatorSid  <br/> msRTCSIP OwnerUrn  <br/> msRTCSIP PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP ProxyAddresses  <br/> msRTCSIP SourceObjectType  <br/> msRTCSIP TargetHomeServer  <br/> msRTCSIP TargetUserPolicies  <br/> msRTCSIP TenantId  <br/> msRTCSIP UserEnabled  <br/> msRTCSIP UserExtension  <br/> msRTCSIP UserLocationProfile  <br/> msRTCSIP UserPolicies  <br/> msRTCSIP UserPolicy  <br/> msRTCSIP UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
|邮件收件人  <br/> |msExchUCVoiceMailSettings  <br/> msExchUserHoldPolicies  <br/> |
|msRTCSIP ApplicationServerService  <br/> |msRTCSIP ApplicationServerBL  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |msRTCSIP ApplicationList  <br/> msRTCSIP ApplicationServerPoolLink  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |msRTCSIP ConferenceDirectoryHomePool  <br/> msRTCSIP ConferenceDirectoryId  <br/> msRTCSIP ConferenceDirectoryTargetPool  <br/> msRTCSIP ExtensionData  <br/> |
|msRTCSIP DefaultCWABank  <br/> |msRTCSIP DefaultCWAExternalURL  <br/> msRTCSIP DefaultCWAInternalURL  <br/> |
|msRTCSIP 域  <br/> |msRTCSIP 默认  <br/> msRTCSIP DomainData  <br/> msRTCSIP DomainName  <br/> |
|msRTCSIP EdgeProxy  <br/> |msRTCSIP EdgeProxyData  <br/> msRTCSIP EdgeProxyFQDN  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |msRTCSIP MCUData  <br/> msRTCSIP MCUFactoryAddress  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> msRTCSIP TrustedServiceLinks  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |msRTCSIP EnterpriseServices  <br/> msRTCSIP PoolAddress  <br/> msRTCSIP ServerData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |msRTCSIP BackEndServer  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP MirrorBackEndServer  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP LocalNormalization  <br/> |msRTCSIP LocalNormalizationOptions  <br/> |
|msRTCSIP LocationContactMapping  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP MappingContact  <br/> msRTCSIP MappingLocation  <br/> |
|msRTCSIP LocationProfile  <br/> |msRTCSIP ExternalAccessCode  <br/> msRTCSIP LocationProfileOptions  <br/> |
|msRTCSIP MCUFactory  <br/> |msRTCSIP MCUFactoryData  <br/> msRTCSIP MCUFactoryProviderID  <br/> msRTCSIP MCUServers  <br/> msRTCSIP MCUType  <br/> msRTCSIP MCUVendor  <br/> msRTCSIP PoolAddresses  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP MCUFactoryService  <br/> |msRTCSIP MCUFactoryPath  <br/> |
|msRTCSIP 移动  <br/> |msRTCSIP MobilityFlags  <br/> msRTCSIP MobilityPolicy  <br/> |
|msRTCSIP MonitoringServer  <br/> |dnsHostName  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP 池  <br/> |msRTCSIP ApplicationList  <br/> msRTCSIP BackEndServer  <br/> msRTCSIP dnsHostName  <br/> msRTCSIP PoolData  <br/> msRTCSIP PoolDisplayName  <br/> msRTCSIP PoolDomainFQDN  <br/> msRTCSIP PoolFunctionality  <br/> msRTCSIP PoolType  <br/> msRTCSIP PoolVersion  <br/> msRTCSIP TrustedServiceLinks  <br/> |
|msRTCSIP PoolService  <br/> |msRTCSIP FrontEndServers  <br/> |
|msRTCSIP 状态  <br/> |msRTCSIP PresenceFlags  <br/> msRTCSIP PresencePolicy  <br/> |
|msRTCSIP TrustedMCU  <br/> |msRTCSIP MCUType  <br/> msRTCSIP MCUVendor  <br/> msRTCSIP RoutingPoolDN  <br/> msRTCSIP TrustedMCUData  <br/> msRTCSIP TrustedMCUFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP TrustedProxy  <br/> |msRTCSIP TrustedProxyData  <br/> msRTCSIP TrustedProxyFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP TrustedServer  <br/> |msRTCSIP TrustedServerData  <br/> msRTCSIP TrustedServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP TrustedService  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP 路由  <br/> msRTCSIP RoutingPoolDN  <br/> msRTCSIP ServerBL  <br/> msRTCSIP TrustedServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> msRTCSIP TrustedServiceFlags  <br/> msRTCSIP TrustedServicePort  <br/> msRTCSIP TrustedServiceType  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |msRTCSIP TrustedWebComponentsServerData  <br/> msRTCSIP TrustedWebComponentsServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP WebComponentsService  <br/> |msRTCSIP WebComponentsServers  <br/> |
|msRTCSIP WebComponentSettings  <br/> |msRTCSIP WebComponentsData  <br/> msRTCSIP WebComponentsPoolAddress  <br/> msRTCSIP ServerVersion  <br/> |
|用户  <br/> |msRTCSIP AcpInfo  <br/> msRTCSIP ApplicationOptions  <br/> msRTCSIP ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP FederationEnabled  <br/> msRTCSIP GroupingID  <br/> msRTCSIP InternetAccessEnabled  <br/> msRTCSIP 行  <br/> msRTCSIP LineServer  <br/> msRTCSIP OptionFlags  <br/> msRTCSIP OriginatorSid  <br/> msRTCSIP OwnerUrn  <br/> msRTCSIP PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP TargetHomeServer  <br/> msRTCSIP TargetUserPolicies  <br/> msRTCSIP TenantId  <br/> msRTCSIP UserEnabled  <br/> msRTCSIP UserExtension  <br/> msRTCSIP UserLocationProfile  <br/> msRTCSIP UserPolicies  <br/> msRTCSIP UserPolicy  <br/> msRTCSIP UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
   
### <a name="classes-contained-in-other-classes"></a>其他类中包含的类

|**类**|**可能包含此类**|
|:-----|:-----|
|serviceConnectionPoint  <br/> |msRTCSIP 服务器  <br/> msRTCSIP PoolService  <br/> msRTCSIP MCU  <br/> msRTCSIP MCUFactoryService  <br/> msRTCSIP web 组件  <br/> msRTCSIP WebComponentsService  <br/> msRTCSIP ApplicationServerService  <br/> msRTCSIP 服务  <br/> msRTCSIP 连接点  <br/> msRTCSIP MediationServer  <br/> msRTCSIP ApplicationServer  <br/> |
|msRTCSIP 服务  <br/> |msRTCSIP GlobalContainer  <br/> 在 Msrtcsip-pools  <br/> msRTCSIP MCUFactories  <br/> msRTCSIP TrustedMCUs  <br/> msRTCSIP TrustedWebComponentsServers  <br/> msRTCSIP TrustedProxies  <br/> msRTCSIP TrustedServices  <br/> msRTCSIP ApplicationContacts  <br/> msRTCSIP LocationContactMappings  <br/> msRTCSIP ConferenceDirectories  <br/> msRTCSIP GlobalTopologySettings  <br/> |
|msRTCSIP GlobalContainer  <br/> |msRTCSIP 域  <br/> msRTCSIP TrustedServer  <br/> msRTCSIP EdgeProxy  <br/> msRTCSIP MonitoringServer  <br/> |
|在 Msrtcsip-pools  <br/> |msRTCSIP 池  <br/> |
|msRTCSIP MCUFactories  <br/> |msRTCSIP MCUFactory  <br/> |
|msRTCSIP TrustedMCUs  <br/> |msRTCSIP TrustedMCU  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |msRTCSIP TrustedWebComponentsServer  <br/> |
|msRTCSIP TrustedProxies  <br/> |msRTCSIP TrustedProxy  <br/> |
|msRTCSIP TrustedServices  <br/> |msRTCSIP TrustedService  <br/> |
|msRTCSIP LocationContactMappings  <br/> |msRTCSIP LocationContactMapping  <br/> |
|msRTCSIP ConferenceDirectories  <br/> |msRTCSIP ConferenceDirectory  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |msRTCSIP GlobalTopologySetting  <br/> |
   

