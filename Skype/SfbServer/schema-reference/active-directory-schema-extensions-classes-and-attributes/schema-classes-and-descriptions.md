---
title: 架构类和 Skype 中的业务服务器的说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本节介绍用于通过 Skype 业务服务器的所有架构类。
ms.openlocfilehash: 3074c11337427523608d894d0ba19544a7f0e8f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924974"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>架构类和 Skype 中的业务服务器的说明
 
本节介绍用于通过 Skype 业务服务器的所有架构类。 
  
## <a name="schema-classes-and-descriptions"></a>架构类和说明

|**类**|**说明**|**注释**|
|:-----|:-----|:-----|
|邮件收件人  <br/> |Exchange 统一消息 (UM) 电子邮件收件人。  <br/> |与 Exchange UM 共享此辅助类。  <br/> |
|msRTCSIP ApplicationContacts  <br/> |此类是多个应用程序联系人的容器，并且自身不包含任何属性。  <br/> |Microsoft Office Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP ApplicationServer  <br/> |此类包含的统一通信应用程序服务 (UCAS) 实例的服务控制点的条目。  <br/> |Office Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP ApplicationServerService  <br/> |此类提供从特定池到其应用程序服务的关联。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |Msrtcsip-applicationserver 此辅助类包含表示设置的属性的应用程序服务的实例。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP 存档 （作废）  <br/> |这 msrtcsip-globalcontainer 的辅助类包含与存档相关的所有设置。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP ArchivingServer （作废）  <br/> |此类表示单个即时消息存档服务器。 此类的实例被创建即时消息存档服务器，而被激活计算机时，如即时消息存档服务的计算机安装。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP ConferenceDirectories  <br/> |此类是会议目录的多个实例的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |此类包含表示特定会议目录的设置的属性。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP 连接点  <br/> |通用服务控制点 (SCP) 将计算机指定为运行 Skype 业务服务器的服务器。  <br/> |Lync 2010 中的新增类。  <br/> |
|msRTCSIP DefaultCWABank  <br/> |此辅助类包含 Skype 业务 Web 应用程序组的设置。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP 域  <br/> |此类包含定义 SIP 注册器的已配置的域的属性。  <br/> |-  <br/> |
|msRTCSIP EdgeProxy  <br/> |此类容器表示单个访问边缘服务。 因为外围网络中部署的访问边缘服务和客户通常不允许从外围网络的 Active Directory 域服务访问，访问边缘服务的实例未加入到 intranet 的 Active Directory 网络中。 因此，访问代理服务器没有自动注册在 AD DS 中。 管理员必须在 AD DS 中手动配置访问边缘服务的每个实例存在。  <br/> |-  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |此 MSRTCSIP-MCU 的辅助类包含表示会议服务器的设置的属性。  <br/> |Microsoft Office Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |此 Msrtcsip-mediationserver 的辅助类包含表示中介服务器的设置的属性。  <br/> |Office Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |此 Msrtcsip-server 的辅助类包含表示 SIP 服务器的设置的属性。  <br/> |-  <br/> |
|msRTCSIP 联合身份验证  <br/> |这 msrtcsip-globalcontainer 的辅助类包含与联合相关的所有设置。  <br/> |-  <br/> |
|msRTCSIP GlobalContainer  <br/> |此类包含应用于整个业务服务器部署 Skype 所有设置。  <br/> |-  <br/> |
|msRTCSIP GlobalUserPolicy （已过时）  <br/> |此类表示单个 Office Communications Server 会议策略。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |本地全局拓扑设置对象。  <br/> |Lync Server 2010 中的新增类。  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |包含全局拓扑设置对象的容器。  <br/> |Lync Server 2010 中的新增类。  <br/> |
|msRTCSIP LocalNormalization  <br/> |此类是表示位置的规范化规则的实例的容器。  <br/> |-  <br/> |
|msRTCSIP LocationContactMapping  <br/> |此类由会议助理应用程序，并包含用于按地区会议电话号码分类的属性。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP LocationContactMappings  <br/> |此类是联系人映射的位置的多个实例的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP LocationProfile  <br/> |此类是表示特定位置配置文件的容器。  <br/> |-  <br/> |
|msRTCSIP LocationProfiles （已过时）  <br/> |此类是多个位置配置文件的容器，并且自身不包含任何属性。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP LocalNormalizations （已过时）  <br/> |此类是多个本地规范化规则的容器，并且自身不包含任何属性。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP MCU  <br/> |此类表示单个会议服务器。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP MCUFactories  <br/> |此类包含多个 Msrtcsip-mcufactory 类，并且不自身没有任何属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP MCUFactory  <br/> |此类是表示单个媒体类型的会议服务器中心容器。 激活此特定类型和供应商的第一个会议服务器时，将创建此类的实例。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP MCUFactoryService  <br/> |此类提供从特定池到其会议服务器中心的关联。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP MediationServer  <br/> |此类包含中介服务器的服务控制点的条目。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP 会议 （作废）  <br/> |这 msrtcsip-globalcontainer 的辅助类包含表示可配置会议设置属性。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP 移动  <br/> |存储全局移动性设置的容器。  <br/> |-  <br/> |
|msRTCSIP MonitoringServer  <br/> |此类包含表示单个监控服务器的设置的属性。  <br/> |Communications Server 2007 R2 中的新增类。  <br/> |
|msRTCSIP PhoneRoute （已过时）  <br/> |此类是表示到网关或一组网关的最低成本路由的实例的容器。 所有企业版池或运行 Standard Edition 服务器都使用此信息以最经济高效的方式路由到公用电话交换网 (PSTN) 的传出呼叫。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP PhoneRoutes （已过时）  <br/> |此类是多个、 最低成本路由的容器，并且自身不包含任何属性。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP 策略 （作废）  <br/> |此类包含多个 Lync Server 策略类，并且没有任何属性本身。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP 池  <br/> |此类表示单个 Skype 业务服务器池。  <br/> |-  <br/> |
|在 Msrtcsip-pools  <br/> |此类包含多个 Skype 的业务服务器池，并且没有任何属性本身。  <br/> |-  <br/> |
|msRTCSIP PoolService  <br/> |此类表示池的服务控制 pointservice 控制点。 用户承载于池中具有其 Msrtcsip-primaryhomeserver 属性将指向此类的实例。  <br/> |-  <br/> |
|msRTCSIP 状态  <br/> |存储全局状态设置的容器。  <br/> |-  <br/> |
|msRTCSIP 注册器  <br/> |这 msrtcsip-globalcontainer 的辅助类包含表示 SIP 注册器服务器维护的用户设置属性。  <br/> |-  <br/> |
|msRTCSIP RouteUsage （已过时）  <br/> |此类是表示电话路由用法的实例的容器。 电话路由用法类由一个属性字段和一个说明字段组成。 属性字段定义用法类型。 说明字段，管理员可以描述此属性中电话路由用法。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP RouteUsages （已过时）  <br/> |此类包含 Msrtcsip-routeusage 类的多个实例，并且没有任何属性本身。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP 搜索  <br/> |这 msrtcsip-globalcontainer 的辅助类包含用于限定和控制搜索结果的范围的属性。  <br/> |-  <br/> |
|msRTCSIP 服务器  <br/> |此类表示单个服务器运行 Business Server Skype。  <br/> |-  <br/> |
|msRTCSIP 服务  <br/> |此类包含全局设置容器和 Msrtcsip-domain 对象。  <br/> |-  <br/> |
|msRTCSIP TrustedMCU  <br/> |此类包含表示受信任会议服务器的设置的属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedMCUs  <br/> |此类包含 Msrtcsip-trustedmcu 类的多个实例，并且没有任何属性本身。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedProxies  <br/> |此类包含多个 Msrtcsip-trustedproxy 类，并且自身不包含任何属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedProxy  <br/> |此类是表示运行代理服务器的服务器的容器。 激活新的代理服务器的计算机上连接到 AD DS 时，将创建此类的实例。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedServer  <br/> |此类包含表示受信任服务器的设置的属性。  <br/> |-  <br/> |
|msRTCSIP TrustedService  <br/> |此类是表示受信任的服务，可使用全局可路由用户代理 URI (GRUU) 地址路由的容器。 激活受 Business Server Skype 的新服务器时，将创建此类的实例。 此受信任服务器必须加入 Active Directory 域。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedServices  <br/> |此类是多个 GRUU 服务器的容器，并且自身不包含任何属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |此类包含表示受信任的 web 组件的设置的属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |此类包含 Msrtcsip-trustedwebcomponentserver 类的多个实例，并且没有任何属性本身。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP UnifiedCommunications （已过时）  <br/> |此 msrtcsip-globalcontainer 的辅助类包含与统一通信相关的属性。  <br/> |Lync Server 2010 中已过时。  <br/> |
|msRTCSIP web 组件  <br/> |此类包含服务控制 pointservice 控制点的 Internet 信息服务器 (IIS)。 为 web 组件服务器，它标识服务器。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP WebComponentsService  <br/> |此类提供从特定池到该池将使用的 web 组件的关联。  <br/> |Communications Server 2007 中的新增类。  <br/> |
|msRTCSIP WebComponentSettings  <br/> |此 Msrtcsip-webcomponents 的辅助类包含表示 web 组件的设置的属性。  <br/> |Communications Server 2007 中的新增类。  <br/> |
   

