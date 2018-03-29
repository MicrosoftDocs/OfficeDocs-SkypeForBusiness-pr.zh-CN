---
title: 架构类和在 Skype 业务服务器的描述
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本部分介绍用于通过 Skype 业务服务器的架构类。
ms.openlocfilehash: 20d85e879bb9bfb040150423d47836b6e6803c37
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>架构类和在 Skype 业务服务器的描述
 
本部分介绍用于通过 Skype 业务服务器的架构类。 
  
## <a name="schema-classes-and-descriptions"></a>架构类和说明

|**类**|**说明**|**注释**|
|:-----|:-----|:-----|
|邮件收件人  <br/> |Exchange 统一消息 (UM) 电子邮件收件人。  <br/> |此辅助类 UM 交换与共享。  <br/> |
|msRTCSIP ApplicationContacts  <br/> |此类是用于多个应用程序的联系人的容器，不包含任何属性本身。  <br/> |Microsoft Office 通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP-应用程序服务器  <br/> |此类的实例的统一通信应用程序服务 (UCAS) 包含服务控制点的条目。  <br/> |办公通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerService  <br/> |此类提供对其应用程序服务从一个特定的池关联。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |MsRTCSIP-应用程序服务器对此辅助类包含属性表示用于设置应用程序服务的实例。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP 存档 （已过时）  <br/> |MsRTCSIP GlobalContainer 对此辅助类包含与存档相关的所有设置。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ArchivingServer （已过时）  <br/> |此类表示单个即时消息存档服务器。 此类的实例创建时计算机激活为即时消息存档服务器，如即时消息存档服务计算机安装。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP ConferenceDirectories  <br/> |此类会议目录的多个实例的容器，不包含任何属性本身。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |此类包含表示特定会议目录的设置的属性。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP 连接点  <br/> |通用服务控制点 (SCP) 指定为业务服务器运行 Skype 的服务器的计算机。  <br/> |Lync 2010 中的新功能。  <br/> |
|msRTCSIP DefaultCWABank  <br/> |此辅助类包含企业 Web 应用程序的银行对 Skype 的设置。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP 域  <br/> |此类包含用于定义的已配置的域的 SIP 注册器属性。  <br/> |-  <br/> |
|msRTCSIP EdgeProxy  <br/> |此类容器表示一个访问边缘服务。 由于访问边缘服务部署在外围网络中，客户通常不允许 Active Directory 域服务从外围网络的访问，访问边缘服务实例未加入到 intranet 的 Active Directory 网络。 因此，访问代理服务器将不会自动注册在 AD DS 中。 在 AD DS 中，管理员必须手动配置访问边缘服务的每个实例的存在。  <br/> |-  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |对 msRTCSIP MCU 此辅助类包含属性表示会议服务器的设置。  <br/> |Microsoft Office 通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |MsRTCSIP MediationServer 对此辅助类包含属性表示中介服务器的设置。  <br/> |办公通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |MsRTCSIP 服务器到该辅助类包含属性表示 SIP 服务器的设置。  <br/> |-  <br/> |
|msRTCSIP-联合身份验证  <br/> |MsRTCSIP GlobalContainer 对此辅助类包含与联合身份验证相关的所有设置。  <br/> |-  <br/> |
|msRTCSIP GlobalContainer  <br/> |此类包含将应用于整个业务服务器部署 Skype 的所有设置。  <br/> |-  <br/> |
|msRTCSIP GlobalUserPolicy （已过时）  <br/> |此类表示单个 Office 通信服务器会议策略。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |本地的全局拓扑结构设置对象。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |要保存设置的对象的全局拓扑结构的容器。  <br/> |Lync Server 2010 中的新功能。  <br/> |
|msRTCSIP LocalNormalization  <br/> |此类是表示位置规范化规则的实例的容器。  <br/> |-  <br/> |
|msRTCSIP LocationContactMapping  <br/> |此类会议助理应用程序创建，并包含用于按地区分类会议电话号码属性。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP LocationContactMappings  <br/> |此类是联系人映射的位置的多个实例的容器，不包含任何属性本身。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP LocationProfile  <br/> |此类是表示特定位置配置文件的容器。  <br/> |-  <br/> |
|msRTCSIP LocationProfiles （已过时）  <br/> |此类是用于多个位置配置文件的容器，不包含任何属性本身。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP LocalNormalizations （已过时）  <br/> |此类是用于多个本地的规范化规则的容器，不包含任何属性本身。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP MCU  <br/> |此类表示单个的会议服务器。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactories  <br/> |此类包含多个 msRTCSIP MCUFactory 类并不具有属性本身。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactory  <br/> |此类是表示会议服务器工厂为一个中等类型的容器。 对于此特定类型和供应商的第一个会议服务器被激活时创建此类的实例。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MCUFactoryService  <br/> |此类提供对其会议服务器工厂从一个特定的池关联。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP MediationServer  <br/> |此类中介服务器充当服务控制点的条目。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP 会议 （已过时）  <br/> |MsRTCSIP GlobalContainer 为此辅助类包含表示可配置会议设置的属性。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP 移动  <br/> |存储全局移动设置的容器。  <br/> |-  <br/> |
|msRTCSIP MonitoringServer  <br/> |此类包含用于表示一台监视服务器的设置属性。  <br/> |通信服务器 2007 R2 中的新功能。  <br/> |
|msRTCSIP PhoneRoute （已过时）  <br/> |此类是一个表示实例的最低成本路由到网关或网关的一组的容器。 此信息由所有企业版池或服务器运行标准版用于以最具成本效益的方式传送到公共交换的电话网 (PSTN) 的传出呼叫。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP PhoneRoutes （已过时）  <br/> |此类是多、 最低开销路由的容器，不包含任何属性本身。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP 策略 （已过时）  <br/> |此类包含多个 Lync Server 策略类并不具有任何属性本身。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP 池  <br/> |此类表示单个 Skype 业务服务器池。  <br/> |-  <br/> |
|msRTCSIP 池  <br/> |此类包含多个业务服务器池的 Skype，并不具有任何属性本身。  <br/> |-  <br/> |
|msRTCSIP PoolService  <br/> |此类表示池的服务控制 pointservice 控制点。 池上承载的用户都有其 msRTCSIP PrimaryHomeServer 特性点，对此类的实例。  <br/> |-  <br/> |
|msRTCSIP-状态  <br/> |容器，存储全球化设置。  <br/> |-  <br/> |
|msRTCSIP 的注册  <br/> |MsRTCSIP GlobalContainer 对此辅助类包含表示 SIP 注册服务器维护的用户设置的属性。  <br/> |-  <br/> |
|msRTCSIP RouteUsage （已过时）  <br/> |此类是表示电话路由使用的实例的容器。 电话路由使用类包含属性域和说明字段。 属性字段定义一个使用类型。 说明字段允许管理员描述电话路由中此属性的用法。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP RouteUsages （已过时）  <br/> |此类包含 msRTCSIP RouteUsage 类的多个实例，并不具有任何属性本身。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP 搜索  <br/> |MsRTCSIP GlobalContainer 对此辅助类包含用于限定和控制搜索结果范围的属性。  <br/> |-  <br/> |
|msRTCSIP 服务器  <br/> |此类表示单个服务器业务服务器运行 Skype。  <br/> |-  <br/> |
|msRTCSIP 服务  <br/> |此类包含全局设置容器和 msRTCSIP 域对象。  <br/> |-  <br/> |
|msRTCSIP TrustedMCU  <br/> |此类包含表示信任会议服务器设置的属性。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedMCUs  <br/> |此类包含 msRTCSIP TrustedMCU 类的多个实例，并不具有任何属性本身。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedProxies  <br/> |此类包含多个 msRTCSIP TrustedProxy 类并不包含任何属性本身。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedProxy  <br/> |此类是表示运行代理服务器的服务器的容器。 激活新的代理服务器的计算机上连接到 AD DS 时创建此类的实例。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedServer  <br/> |此类包含表示受信任的服务器设置的属性。  <br/> |-  <br/> |
|msRTCSIP TrustedService  <br/> |此类是表示可使用全局路由用户代理的 URI (GRUU) 地址路由的受信任的服务的容器。 受信任的 Skype 业务服务器的新服务器已激活时创建此类的实例。 这种受信任服务器必须加入 Active Directory 域。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedServices  <br/> |此类是 GRUU 的多个服务器的容器，不包含任何属性本身。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |此类包含用于表示受信任的 web 组件的设置属性。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |此类包含 msRTCSIP TrustedWebComponentServer 类的多个实例，并不具有任何属性本身。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP UnifiedCommunications （已过时）  <br/> |MsRTCSIP GlobalContainer 对此辅助类包含与统一通信相关的属性。  <br/> |Lync Server 2010 中的过时。  <br/> |
|msRTCSIP WebComponents  <br/> |此类包含服务控制 pointservice 控制点的互联网信息服务器 (IIS)。 它为 web 组件服务器标识服务器。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP WebComponentsService  <br/> |此类提供对该池将使用 web 组件从一个特定的池关联。  <br/> |通信服务器 2007年中的新功能。  <br/> |
|msRTCSIP WebComponentSettings  <br/> |MsRTCSIP WebComponents 对此辅助类包含属性表示 web 组件的设置。  <br/> |通信服务器 2007年中的新功能。  <br/> |
   

