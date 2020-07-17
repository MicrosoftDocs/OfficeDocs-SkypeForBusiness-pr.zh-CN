---
title: 为直接路由认证的会话边框控制器
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 管理员可以了解哪些会话边界控制器（SBCs）已验证了直接路由。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b27bcc55ad2039d7e51af835c0b64c514d7dc303
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042944"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>经认证可用于直接路由的会话边界控制器列表

Microsoft 合作伙伴与选定的会话边界控制器 (SBC) 供应商认证其 SBC 可用于直接路由。 

Microsoft 与每位供应商协作： 

- 联合处理 SIP 互连协议。
- 使用第三方实验执行密集测试。 只有通过测试的设备才经过认证。 
- 在生产环境和预生产环境中通过所有已认证的设备运行每日测试。 在预生产环境中验证设备可保证云中新版本的直接路由代码可用于获得认证的 SBC。 
- 与 SBC 供应商建立联合支持流程。


  > [!NOTE]
  > 只有经过认证的设备或设备通过直接路由连接时，Microsoft 才支持电话系统。 Microsoft 保留拒绝未验证设备通过直接路由连接到手机系统的支持案例的权利。 

下表列出了经认证可用于直接路由的设备。 

[详细了解直接路由](https://aka.ms/dr)。 如果您对用于直接路由的 SBC 认证计划有任何疑问，请联系 drsbccertification@microsoft.com。


|                                                       供应商                                                        |       产品       | 非媒体旁路 | 媒体绕过 | 软件版本 | 已通过 E911 提供商验证 | ELIN 支持
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支持的7.20 （推荐的7.20，即256位）   | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支持的7.20 （推荐的7.20，即256位）   | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支持的7.20 （推荐的7.20，即256位）   |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支持的7.20 （推荐的7.20，即256位）   |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  支持的7.20 （推荐的7.20，即256位）  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支持的7.20 （推荐的7.20，即256位）   | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支持的7.20 （推荐的7.20，即256位） |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       支持的7.2 （推荐8.2）       | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       支持的7.2 （推荐8.2）       |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支持的7.2 （推荐8.2）       |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支持的7.2 （推荐8.2）       |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支持的7.2 （推荐8.2）       |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.0.3 （内部版本537）     |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.0.3 （内部版本537）     |  <ul> <li>[带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.0.3 （内部版本216）    |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>    |     &#10004;     |   
| | EdgeMarc 系列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支持的3.20 （推荐4.0）        |     |    |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     用于1000系列集成服务路由器的 Cisco 统一 Border 元素（多维数据集）        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |   |  
|                                   |     用于4000系列集成服务路由器的 Cisco 统一 Border 元素（多维数据集）        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>     |    |  
|                                   |     用于1000V 系列云服务路由器的 Cisco 统一 Border 元素（多维数据集）       |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |  
|                                 |     用于1000系列聚合服务路由器的 Cisco 统一边框元素（多维数据集）      |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 紧急路由服务（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 急诊网关（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |  

下表列出了直接路由和模拟设备之间的互操作性验证的设备。

|                                                       供应商                                                        |       产品       | 确认
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [带](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。软件版本：8.1.1 （内部版本527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [带](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。软件版本：8.1.1 （内部版本527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 软件版本8.3.0.1。2 |     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 软件版本8.3.0.1。2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 软件版本8.3.0.1。2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 软件版本8.3.0.1。2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 软件版本8.3.0.1。2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 软件版本8.3.0.1。2 |     &#10004;     |
  | [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode 与 Grandstream GXW42xx （V 1.0.7.10） |     &#10004;     |

若要向我们提供有关团队的产品反馈，例如新功能的想法，请参阅[Uservoice](https://microsoftteams.uservoice.com)。
请注意授予主要版本的证书。 这意味着支持在主要版本之后的 SBC 固件中包含任何数字的固件。
