---
title: 通过直接路由认证的会话边界控制器
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
description: 管理员可以了解哪些会话边界控制器 (SDC) 直接路由的认证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 256451e778ed0e5864a7144003d44eb7ffc28767
ms.sourcegitcommit: b8e697d52dcedace66cec2a06a5bd9889a780623
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "49782535"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>经认证可用于直接路由的会话边界控制器列表

Microsoft 合作伙伴与选定的会话边界控制器 (SBC) 供应商认证其 SBC 可用于直接路由。 

Microsoft 与每个供应商合作，以： 

- 共同开发 SIP 互连协议。
- 使用第三方实验室执行密集测试。 只有通过测试的设备才通过认证。 
- 在生产和预生产环境中，使用所有经过认证的设备运行每日测试。 在预生产环境中验证设备可保证云中新版本的直接路由代码可用于获得认证的 SBC。 
- 与 SBC 供应商建立联合支持流程。


  > [!NOTE]
  > Microsoft 仅在经过认证的设备或设备通过直接路由连接时支持电话系统。 Microsoft 保留拒绝未认证设备通过直接路由连接到电话系统的支持案例的权利。 如果 Microsoft 确定客户的直接路由问题与供应商的 SBC 设备有关，则客户需要联系 SBC 供应商提供支持。

下表列出了经认证可用于直接路由的设备。  (有关哪些 SBC 供应商支持本地媒体优化的信息，请参阅"为直接路由[.) ](direct-routing-media-optimization-configure.md)

[详细了解直接路由](https://aka.ms/dr)。 如果对直接路由的 SBC 认证计划有任何疑问，请联系drsbccertification@microsoft.com。
<br/>
<br/>

|                                                       供应商                                                        |       产品       | 非媒体旁路 | 媒体旁路 | 软件版本 | 使用 E911 提供程序进行验证 | 支持 ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支持的 7.20A.250 (推荐 7.20A.258)    | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支持的 7.20A.250 (推荐 7.20A.258)    | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支持的 7.20A.250 (推荐 7.20A.258)    |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支持的 7.20A.250 (推荐 7.20A.258)    |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  支持的 7.20A.250 (推荐 7.20A.258)   |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支持的 7.20A.250 (推荐 7.20A.258)    | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支持的 7.20A.250 (推荐 7.20A.258)  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支持的 8.2 和 7.2 (建议 9.2)        | <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支持的 8.2 和 7.2 (建议 9.2)        |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支持的 8.2 和 7.2 (建议 9.2)        |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支持的 8.2 和 7.2 (建议 9.2)        |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支持的 8.2 和 7.2 (建议 9.2)           |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 或 9.x     |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 或 9.x     |  <ul> <li>[带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 或 9.x    |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>    |     &#10004;     |   
| | EdgeMarc 系列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支持的 3.20 (推荐的 4.0)         |  <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>   |    |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) 1000 系列集成服务路由器        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |   |  
|                                   |     Cisco Unified Border Element (CUBE) 4000 系列集成服务路由器        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1r      |   <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>     |    |  
|                                   |     适用于 1000V (路由器) CUBE 的 Cisco 统一边界元素       |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |  
|                                 |     适用于 1000 系列聚合 (路由器) CUBE 的 Cisco 统一边界元素      |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1r      |    <ul> <li> [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[内部紧急路由服务 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW 网关内 (网关) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |
|                     [Avya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    适用于 Enterprise ( ASBCE)     |     &#10004;     |           |       版本 8.1.1       |     |    | 
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 会话边界控制器    |     &#10004;     |           |       1908 (19.5)        |     |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       5.0       |     |    | 
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 

<br/>
<br/>
下表列出了已验证直接路由和模拟设备之间的互操作性的设备。

|                                                       供应商                                                        |       产品       | 已验证
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。软件版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。软件版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 软件版本 8.3.0.1.2 |     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 软件版本 8.3.0.1.2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 软件版本 8.3.0.1.2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 软件版本 8.3.0.1.2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 软件版本 8.3.0.1.2|     &#10004;     |
  | [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 软件版本 8.3.0.1.2 |     &#10004;     |
  | [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  具有 Grandstream GXW42xx (V1.0.7.10 的 anynode)  |     &#10004;     |

若要向我们提供有关 Teams 的产品反馈，例如新功能的想法，请参阅[Uservoice。](https://microsoftteams.uservoice.com)
请注意授予主要版本的认证。 这意味着支持在 SBC 固件中具有任意编号的固件（主要版本后）。
