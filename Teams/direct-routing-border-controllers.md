---
title: 经认证可用于直接路由的会话边界控制器列表
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 管理员可以了解哪些会话边界控制器 (SBC) 已通过直接路由认证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d7103ecb4183674fe1e92c7d7e3a37182c0d50
ms.sourcegitcommit: beb66bc2ce70edbaf6c77eee6d8c050c5cb37fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2021
ms.locfileid: "53515167"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>经认证可用于直接路由的会话边界控制器列表

Microsoft 合作伙伴与选定的会话边界控制器 (SBC) 供应商认证其 SBC 可用于直接路由。

Microsoft 与每个供应商合作：

- 就 SIP 互连协议共同协作。
- 使用第三方实验室执行密集测试。 仅对通过测试的设备进行认证。
- 在生产环境和预生产环境中对获得认证的所有设备运行日常测试。 在预生产环境中验证设备可保证云中新版本的直接路由代码可用于获得认证的 SBC。
- 与 SBC 供应商一起提供联合支持。

  > [!NOTE]
  > Microsoft 仅在通过直接路由连接一个或多个获得认证的设备时支持电话系统。 Microsoft 保留在非认证设备通过直接路由连接电话系统的情况下拒绝提供支持的权利。 如果 Microsoft 确定客户的直接路由问题与供应商的 SBC 设备有关，则客户需要与 SBC 供应商联系以获得支持。

下表列出了经认证可用于直接路由的设备。 （如需了解哪些 SBC 供应商支持本地媒体优化的信息，请参阅[为直接路由配置本地媒体优化](direct-routing-media-optimization-configure.md)。）

[详细了解直接路由](https://aka.ms/dr)。
如果你对直接路由的 SBC 认证计划有任何疑问，请发送电子邮件至 drsbccertification@microsoft.com。
<br/>

## <a name="certified-sbc-vendors"></a>认证的 SBC 供应商

|                                                       供应商                                                        |       产品       | 非媒体旁路 | 媒体旁路 | 软件版本 | 支持 911 的服务提供商* | 支持 ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支持的 7.20A.250（推荐 7.20A.258）   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支持的 7.20A.250（推荐 7.20A.258）   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支持的 7.20A.250（推荐 7.20A.258）   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支持的 7.20A.250（推荐 7.20A.258）   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  支持的 7.20A.250（推荐 7.20A.258）  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  支持的 7.20A.250（推荐 7.20A.258）   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支持的 7.20A.250（推荐 7.20A.258） |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支持的 8.2 和 7.2（推荐 9.2）       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支持的 8.2 和 7.2（推荐 9.2）       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支持的 8.2 和 7.2（推荐 9.2）       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支持的 8.2 和 7.2（推荐 9.2）       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支持的 8.2 和 7.2（推荐 9.2）          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 或 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 或 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 或 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc 系列 |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支持的 3.20（推荐 4.0）        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7（4.9 支持媒体旁路）      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     适用于 1000 系列集成服务路由器的 Cisco 统一边界元素 (CUBE)        |     &#10004;   | &#10004; |      支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐 17.3.2）         |    &#10004;     |   |  
|                                   |     适用于 4000 系列集成服务路由器的 Cisco 统一边界元素 (CUBE)        |     &#10004;   | &#10004; |   支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐 17.3.2）         |   &#10004;      |    |  
|                                   |     适用于 1000V 系列云服务路由器的 Cisco 统一边界元素 (CUBE)       |     &#10004;   | &#10004; |      支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐 17.3.2）         |    &#10004;     |    |  
|                                 |     适用于 1000 系列聚合服务路由器的 Cisco 统一边界元素 (CUBE)      |     &#10004;   | &#10004; |      支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐 17.3.2）         |    &#10004;     |    |
|                                 |     适用于 Catalyst 8000 Edge 平台的 Cisco 统一边框元素 (CUBE)      |     &#10004;   | &#10004; |      IOS XE 阿姆斯特丹 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya 会话边界控制器企业版 (ASBCE)    |     &#10004;     |       &#10004;     |       8.1.1 版本（8.1.2 支持媒体旁路）      |     |    |
|                     [诺基亚](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    诺基亚会话边界控制器。    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    诺基亚会话边界控制器。    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       支持的 5.0（推荐 5.1）     |     |    |
|                     [爱立信](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape 会话边界控制器   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies（前身 Media5 Corporation）](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel 系列   |     &#10004;     |         |      DGW 48.0.2340（推荐 DGW 48.1.2503）      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops 会话边界控制器 (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops 虚拟会话边界控制器 (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    超融合语音   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

* 911 服务提供商

- [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 紧急路由服务 (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado 紧急网关 (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>直接路由和模拟设备互操作性

下表列出了已验证直接路由和模拟设备之间互操作性的设备。

|                                                       供应商                                                        |       产品       | 已验证
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 多平台模拟电话适配器 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 软件版本 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 软件版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 软件版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 软件版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 软件版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 软件版本 8.3.0.1.2 |     &#10004;     |
| [功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. 软件版本：8.1.1（内部版本 527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. 软件版本：8.1.1（内部版本 527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  具有 Grandstream GXW42xx 的 anynode (V1.0.7.10) |     &#10004;     |
  
要向我们提供有关 Teams 的产品反馈（例如，新功能想法），请参阅 [UserVoice](https://microsoftteams.uservoice.com)。


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

请注意授予主要版本的认证。 这意味着主要版本后 SBC 固件中任意编号的固件均受支持。
