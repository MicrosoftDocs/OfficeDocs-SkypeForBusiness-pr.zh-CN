---
title: Skype for Business 服务器中的架构类和说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: 本部分介绍 Skype for Business Server 使用的所有架构类。
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296593"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Skype for Business 服务器中的架构类和说明
 
本部分介绍 Skype for Business Server 使用的所有架构类。 
  
## <a name="schema-classes-and-descriptions"></a>架构类和说明

|**种类**|**说明**|**注释**|
|:-----|:-----|:-----|
|邮件-收件人  <br/> |Exchange 统一消息 (UM) 电子邮件收件人。  <br/> |此辅助类与 Exchange UM 共享。  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |此类是多个应用程序联系人的容器, 并且不包含任何属性本身。  <br/> |Microsoft Office 通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |此类包含统一通信应用程序服务 (UCAS) 实例的服务控制点的条目。  <br/> |Office 通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |此类提供从特定池到其应用程序服务的关联。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |此辅助类到 msRTCSIP-ApplicationServer 保留表示应用程序服务实例的设置的属性。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-存档 (已过时)  <br/> |此辅助类到 msRTCSIP-GlobalContainer 保存与存档相关的所有设置。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-ArchivingServer (已过时)  <br/> |此类表示单个即时消息存档服务器。 在将计算机激活为即时消息存档服务器 (如安装了即时消息存档服务的计算机) 时, 将创建此类的实例。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |此类是多个会议目录实例的容器, 并且不包含任何属性本身。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |此类包含表示特定会议目录的设置的属性。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |通用服务控制点 (SCP), 用于将计算机指定为运行 Skype for Business Server 的服务器。  <br/> |Lync 2010 中的新增项。  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |此辅助类保存 Skype for business Web 应用库的设置。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-域  <br/> |此类包含用于定义 SIP 注册机构配置的域的属性。  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |此类容器表示单个访问边缘服务。 由于在外围网络中部署了 Access Edge 服务, 并且客户通常不允许从外围网络访问 Active Directory 域服务, 因此 Access Edge 服务的实例未联接到 intranet 的 Active Directory 网络。 因此, 访问代理服务器不会自动在 AD DS 中注册。 管理员必须手动配置 AD DS 中的每个 Access Edge 服务实例的存在。  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |MsRTCSIP 的此辅助类保留表示会议服务器设置的属性。  <br/> |Microsoft Office 通信服务器2007中的新增新增服务。  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |此辅助类到 msRTCSIP-MediationServer 包含表示中介服务器设置的属性。  <br/> |Office 通信服务器2007中的新增项。  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |此辅助类到 msRTCSIP-服务器保留表示 SIP 服务器设置的属性。  <br/> |-  <br/> |
|msRTCSIP-联合  <br/> |此辅助类到 msRTCSIP-GlobalContainer 保存与联盟相关的所有设置。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |此类包含适用于整个 Skype for Business 服务器部署的所有设置。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (已过时)  <br/> |此类表示单个 Office 通信服务器会议策略。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |本地全局拓扑设置对象。  <br/> |Lync Server 2010 中的新增新增服务。  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |用于保存全局拓扑设置对象的容器。  <br/> |Lync Server 2010 中的新增新增服务。  <br/> |
|msRTCSIP-LocalNormalization  <br/> |此类是表示位置规范化规则的实例的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |此类由会议助理应用程序创建, 并保留用于按地区对会议电话号码进行分类的属性。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |此类是位置联系人映射的多个实例的容器, 并且不包含任何属性本身。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-LocationProfile  <br/> |此类是一个表示特定位置配置文件的容器。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (已过时)  <br/> |此类是多个位置配置文件的容器, 并且不包含任何属性本身。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-LocalNormalizations (已过时)  <br/> |此类是多个本地规范化规则的容器, 并且不包含任何属性本身。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-MCU  <br/> |此类表示单个会议服务器。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-MCUFactories  <br/> |此类保存多个 msRTCSIP MCUFactory 类, 并且没有属性本身。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-MCUFactory  <br/> |此类是一个容器, 表示适用于单个媒体类型的会议服务器工厂。 当激活此特定类型和供应商的第一个会议服务器时, 将创建此类的实例。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |此类提供从特定池到其会议服务器工厂的关联。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-MediationServer  <br/> |此类包含用于中介服务器的服务控制点的条目。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-会议 (已过时)  <br/> |此辅助类到 msRTCSIP-GlobalContainer 包含表示可配置的会议设置的属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-移动性  <br/> |存储全局移动设置的容器。  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |此类包含表示单个监视服务器的设置的属性。  <br/> |通信服务器 2007 R2 中的新增项。  <br/> |
|msRTCSIP-PhoneRoute (已过时)  <br/> |此类是一个容器, 表示指向网关或网关集的最低成本路线的实例。 此信息由运行标准版的所有企业池或服务器使用, 以最经济高效的方式将传出呼叫路由到公共交换电话网络 (PSTN)。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-PhoneRoutes (已过时)  <br/> |此类是多个最少的成本路由的容器, 并且不包含任何属性本身。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-政策 (已过时)  <br/> |此类包含多个 Lync 服务器策略类, 并且没有任何属性本身。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-Pool  <br/> |此类表示单个 Skype for Business 服务器池。  <br/> |-  <br/> |
|msRTCSIP-池  <br/> |此类包含多个 Skype for business 服务器池, 并且没有任何属性本身。  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |此类表示池的服务控制 pointservice 控制点。 托管在池中的用户将其 msRTCSIP-PrimaryHomeServer 属性指向此类的实例。  <br/> |-  <br/> |
|msRTCSIP-状态  <br/> |存储全局状态设置的容器。  <br/> |-  <br/> |
|msRTCSIP-注册机构  <br/> |此辅助类到 msRTCSIP-GlobalContainer 包含表示 SIP 注册机构维护的用户设置的属性。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (已过时)  <br/> |此类是一个容器, 表示手机路线使用情况的实例。 电话路由使用类包含一个属性字段和一个说明字段。 属性字段定义使用类型。 "说明" 域允许管理员在手机路线中描述此属性的用法。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-RouteUsages (已过时)  <br/> |此类保留 msRTCSIP 类的多个实例, 并且没有任何属性本身。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-搜索  <br/> |此辅助类到 msRTCSIP-GlobalContainer 包含限制和控制搜索结果范围的属性。  <br/> |-  <br/> |
|msRTCSIP-服务器  <br/> |此类表示运行 Skype for business 服务器的单个服务器。  <br/> |-  <br/> |
|msRTCSIP-服务  <br/> |此类包含全局设置容器和 msRTCSIP 域对象。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |此类包含表示受信任的会议服务器的设置的属性。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |此类保留 msRTCSIP 类的多个实例, 并且没有任何属性本身。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedProxies  <br/> |此类包含多个 msRTCSIP TrustedProxy 类, 并且不包含任何属性本身。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |此类是一个容器, 表示运行代理服务器的服务器。 在加入到 AD DS 的计算机上激活新的代理服务器时, 将创建此类的实例。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedServer  <br/> |此类包含表示受信任服务器的设置的属性。  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |此类是一个容器, 表示可通过全局可路由用户代理 URI (GRUU) 地址进行路由的受信任的服务。 如果激活了 Skype for Business 服务器信任的新服务器, 则会创建此类的实例。 此受信任服务器必须加入 Active Directory 域。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedServices  <br/> |此类是多个 GRUU 服务器的容器, 并且不包含任何属性本身。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |此类包含表示受信任 web 组件的设置的属性。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |此类保留 msRTCSIP 类的多个实例, 并且没有任何属性本身。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-UnifiedCommunications (已过时)  <br/> |此辅助类到 msRTCSIP-GlobalContainer 保存与统一通信相关的属性。  <br/> |在 Lync Server 2010 中已过时。  <br/> |
|msRTCSIP-WebComponents  <br/> |此类包含 Internet information Server (IIS) 的服务控制 pointservice 控制点。 它将服务器标识为 web 组件服务器。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-WebComponentsService  <br/> |此类提供从特定池到该池将使用的 web 组件的关联。  <br/> |通信服务器2007中的新增项。  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |此辅助类到 msRTCSIP-WebComponents 包含表示 web 组件的设置的属性。  <br/> |通信服务器2007中的新增项。  <br/> |
   

