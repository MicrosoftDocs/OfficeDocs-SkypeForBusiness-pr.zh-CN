---
title: 架构中的架构类和Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本节介绍由 Skype for Business Server 使用的所有架构类。
ms.openlocfilehash: ec9c4a7612455df6d004289f88ccdb7efb3d6334
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596436"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>架构中的架构类和Skype for Business Server
 
本节介绍由 Skype for Business Server 使用的所有架构类。 
  
## <a name="schema-classes-and-descriptions"></a>架构类和说明

|**类**|**说明**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange统一消息 (UM) 电子邮件收件人。  <br/> |此辅助类与 UM Exchange共享。  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |此类是多个应用程序联系人的容器，并且自身不包含任何属性。  <br/> |Microsoft Office Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |此类包含统一通信应用程序服务 (UCAS) 实例的服务控制点的相应项。  <br/> |Office Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |此类提供从特定池到其应用程序服务的关联。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |这是 msRTCSIP-ApplicationServer 的辅助类，包含表示应用程序服务实例设置的属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-Archive（作废）  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与存档相关的所有设置。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-ArchivingServer（作废）  <br/> |此类表示单个即时消息存档服务器。将计算机作为即时消息存档服务器（如安装了即时消息存档服务的计算机）激活时将创建此类的实例。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |此类是会议目录的多个实例的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |此类包含表示特定会议目录的设置的属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |通用服务控制点 (SCP) ，以将计算机指定为运行 Skype for Business Server。  <br/> |Lync 2010 中的新增功能。  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |此辅助类包含银行Skype for Business Web应用设置。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-Domain  <br/> |此类包含定义 SIP 注册器的已配置域的属性。  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |此类容器表示单个访问边缘服务。 由于访问边缘服务部署在外围网络中，并且客户通常不允许从外围网络访问 Active Directory 域服务，因此访问边缘服务的实例未加入到 Intranet 的 Active Directory 网络中。 这样，访问代理就不会在 AD DS 中自动注册。 管理员必须手动配置 AD DS 中每个访问边缘服务实例是否存在。  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |这是 msRTCSIP-MCU 的辅助类，其中包含表示会议服务器的设置的属性。  <br/> |Microsoft Office Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |这是 msRTCSIP-MediationServer 的辅助类，其中包含表示中介服务器的设置的属性。  <br/> |Office Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |这是 msRTCSIP-Server 的辅助类，其中包含表示 SIP 服务器的设置的属性。  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与联盟相关的所有设置。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |此类包含应用于整个部署Skype for Business Server设置。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy（作废）  <br/> |此类表示单个 Office Communications Server 会议策略。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |本地全局拓扑设置对象。  <br/> |Lync Server 2010 中的新增功能。  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |包含全局拓扑设置对象的容器。  <br/> |Lync Server 2010 中的新增功能。  <br/> |
|msRTCSIP-LocalNormalization  <br/> |此类是表示位置规范化规则的实例的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |此类由会议会议助理应用程序保留用于按区域分类会议电话号码的属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |此类是位置联系人映射的多个实例的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-LocationProfile  <br/> |此类是表示特定位置配置文件的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles（作废）  <br/> |此类是多个位置配置文件的容器，并且自身不包含任何属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-LocalNormalizations（作废）  <br/> |此类是多个本地规范化规则的容器，并且自身不包含任何属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-MCU  <br/> |此类表示单个会议服务器。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-MCUFactories  <br/> |此类包含多个 msRTCSIP-MCUFactory 类，并且自身没有任何属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-MCUFactory  <br/> |此类是表示单个媒体类型的会议服务器中心的容器。当激活对应于此特定类型和供应商的第一台会议服务器时，将创建此类的实例。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |此类提供从特定池到其会议服务器中心的关联。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-MediationServer  <br/> |此类包含中介服务器的服务控制点的相应项。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-Meeting（作废）  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示可配置会议设置的属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-Mobility  <br/> |存储全局移动性设置的容器。  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |此类包含表示单个监控服务器的设置的属性。  <br/> |Communications Server 2007 R2 中的新增功能。  <br/> |
|msRTCSIP-PhoneRoute（作废）  <br/> |此类是表示到一个网关或一组网关的最低成本路由的实例的容器。所有企业版池或运行 Standard Edition 的服务器使用此信息，以最经济有效的方式将传出呼叫路由至公用电话交换网 (PSTN)。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-PhoneRoutes（作废）  <br/> |此类是多个最低成本路由的容器，并且自身不包含任何属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-Policies（作废）  <br/> |此类包含多个 Lync Server 策略类，并且自身没有任何属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-Pool  <br/> |此类表示单个Skype for Business Server池。  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |此类包含多个Skype for Business Server池，并且自身没有任何属性。  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |此类表示池的服务控制点。如果用户承载于池中，其 msRTCSIP-PrimaryHomeServer 属性将指向此类的实例。  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |存储全局状态设置的容器。  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示由 SIP 注册器服务器维护的用户设置的属性。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage（作废）  <br/> |此类是表示电话路由用法的实例的容器。电话路由用法类由一个属性字段和一个说明字段组成。属性字段定义用法类型。通过说明字段，管理员可以描述此属性在电话路由中的用法。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-RouteUsages（作废）  <br/> |此类包含 msRTCSIP-RouteUsage 类的多个实例，并且自身没有任何属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-Search  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，它包含用于限定和控制搜索结果范围的属性。  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |此类表示运行数据库的单个Skype for Business Server。  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |此类包含全局设置容器和 msRTCSIP-Domain 对象。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |此类包含表示受信任会议服务器的设置的属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |此类包含 msRTCSIP-TrustedMCU 类的多个实例，并且自身没有任何属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedProxies  <br/> |此类包含多个 msRTCSIP-TrustedProxy 类，并且自身不包含任何属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |此类是表示运行代理服务器的服务器的容器。在加入 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedServer  <br/> |此类包含表示受信任服务器的设置的属性。  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |此类是表示可使用全局可路由用户代理 URI (GRUU) 地址进行路由的受信任服务的容器。 当激活受信任服务器的新服务器时，将Skype for Business Server此类的实例。 此受信任服务器必须加入 Active Directory 域。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedServices  <br/> |此类是多个 GRUU 服务器的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |此类包含表示受信任 Web 组件的设置的属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |此类包含 msRTCSIP-TrustedWebComponentServer 类的多个实例，并且自身没有任何属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-UnifiedCommunications（作废）  <br/> |这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与统一通信相关的属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-WebComponents  <br/> |此类包含 Internet Information Server (IIS) 的服务控制点。它将服务器标识为 Web 组件服务器。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-WebComponentsService  <br/> |此类提供从特定池到该池将使用的 Web 组件的关联。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |这是 msRTCSIP-WebComponents 的辅助类，其中包含表示 Web 组件的设置的属性。  <br/> |Communications Server 2007 中的新增功能。  <br/> |
   

