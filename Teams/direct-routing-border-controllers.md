---
title: 经认证可用于直接路由的会话边界控制器列表
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 了解哪些会话边界控制器 (SBC) 已通过直接路由认证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1908fc1dbfdecc978444d7fc004979c940f8b2a
ms.sourcegitcommit: 3b2e8ec8c104863208f49f282ab0ffa619ff5057
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2022
ms.locfileid: "68697351"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>经认证可用于直接路由的会话边界控制器

Microsoft 合作伙伴与选定的会话边界控制器 (SBC) 供应商认证其 SBC 可用于直接路由。

Microsoft 与每个供应商合作：

- 就 SIP 互连协议共同协作。
- 使用第三方实验室执行密集测试。 仅对通过测试的设备进行认证。
- 在生产环境和预生产环境中对获得认证的所有设备运行日常测试。 在预生产环境中验证设备可保证云中新版本的直接路由代码可用于获得认证的 SBC。
- 与 SBC 供应商一起提供联合支持。

  > [!NOTE]
  > Microsoft 仅在与认证设备一起使用时支持具有直接路由的电话系统。 如果出现问题，必须先联系 SBC 供应商的客户支持。 如果需要，SBC 供应商将通过内部渠道将问题呈报给 Microsoft。 Microsoft 保留在非认证设备通过直接路由连接电话系统的情况下拒绝提供支持的权利。 如果 Microsoft 确定客户的直接路由问题与供应商的 SBC 设备有关，则客户需要重新联系 SBC 供应商以获得支持。
  >
  > 认证将授予特定的 SBC 固件版本。 下面介绍的任何 SBC 固件版本都经过认证且受支持。 只要 major.minor 版本相同，就支持高于所述内容的固件版本。
  >
  > 示例：
  >
  > - 支持的 6.10.258 - 在这种情况下，Microsoft 支持固件版本 6.10。（258 或更高版本）。
  > - 建议的 6.20.100 - 在这种情况下，Microsoft 建议使用固件版本 6.20。（100 或更高版本）。
  > - 有关特定版本的可支持性问题，请联系 SBC 供应商。

下表列出了经认证可用于直接路由的设备。 （如需了解哪些 SBC 供应商支持本地媒体优化的信息，请参阅[为直接路由配置本地媒体优化](direct-routing-media-optimization-configure.md)。）

[详细了解直接路由](https://aka.ms/dr)。

请注意，在下一步通知之前，我们不会接受新的认证提名。

## <a name="certified-sbc-vendors"></a>认证的 SBC 供应商

|供应商|产品|非媒体旁路|媒体旁路|软件版本|支持 911 的服务提供商*|支持 ELIN|
|---|---|---|---|---|---|---|
|[Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|Mediant 500 SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 800 SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 2600 SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 4000 SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 1000B SBC|&#10004;|&#10004;|支持的 7.20A.250（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 9000  SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Virtual Edition SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
||Mediant 云版本 SBC|&#10004;|&#10004;|支持的 7.20A.258（推荐的 7.40A.100 或 7.40A.250）|&#10004;|&#10004;|
|[Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)|SBC 5100/5110|&#10004;|&#10004;|支持 10.1、9.2、8.2 和 7.2 的所有版本 (建议最新版本的 10.1) |&#10004;||
||SBC 5200/5210|&#10004;|&#10004;|支持 10.1、9.2、8.2 和 7.2 的所有版本 (建议最新版本的 10.1) |&#10004;||
||SBC 5400|&#10004;|&#10004;|支持 10.1、9.2、8.2 和 7.2 的所有版本 (建议最新版本的 10.1) ) |&#10004;||
||SBC 7000|&#10004;|&#10004;|支持 10.1、9.2、8.2 和 7.2 的所有版本 (建议最新版本的 10.1) |&#10004;||
||所有 SBC SWe 变体，包括托管产品/服务|&#10004;|&#10004;|支持 10.1、9.2、8.2 和 7.2 的所有版本 (建议最新版本的 10.1) |&#10004;||
||SBC 1000|&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||SBC 2000|&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||SBC SWe Edge (前 SWe Lite) |&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||EdgeMarc 系列|&#10004;|&#10004;|16.3.2||
|[Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)|Think 365 SBC|&#10004;||1.4|||
|[Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)|AP 1100|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||AP 3900|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||AP 4600|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||AP 6300|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||AP 6350|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||VME|&#10004;|&#10004;|支持 8.3.0.0.1 并建议 8.4.x 和 9.x|&#10004;|&#10004;|
||AP 3950|&#10004;|&#10004;|支持的 9.x|&#10004;|&#10004;|
||AP 4900|&#10004;|&#10004;|支持的 9.x|&#10004;|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|anynode|&#10004;|&#10004;|支持的 3.20（推荐 4.0）|&#10004;|&#10004;|
|[Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)|Perimeta SBC|&#10004;|&#10004;|4.7（4.9 支持媒体旁路）|&#10004;|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)|适用于 1000 系列集成服务路由器的 Cisco 统一边界元素 (CUBE)|&#10004;|&#10004;|支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐的 17.6.1a）|&#10004;||
||适用于 4000 系列集成服务路由器的 Cisco 统一边界元素 (CUBE)|&#10004;|&#10004;|支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐的 17.6.1a）|&#10004;||
||适用于 1000V 系列云服务路由器的 Cisco 统一边界元素 (CUBE)|&#10004;|&#10004;|支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐的 17.3.3）|&#10004;||
||适用于 1000 系列聚合服务路由器的 Cisco 统一边界元素 (CUBE)|&#10004;|&#10004;|支持的 IOS XE 阿姆斯特丹 17.2.1r（推荐的 17.6.1a）|&#10004;||
||适用于 Catalyst 8000 Edge 平台的 Cisco 统一边框元素 (CUBE)|&#10004;|&#10004;|支持的 IOS XE 阿姆斯特丹 17.3.2（推荐的 17.6.1a）|&#10004;||
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|适用于企业的 Avaya 会话边界控制器 （ASBCE）|&#10004;|&#10004;|8.1.1 版本（8.1.2 支持媒体旁路）|||
|[诺基亚](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|诺基亚会话边界控制器。|&#10004;|&#10004;|22.0|&#10004;||
|[Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|NetMatch-S CI|&#10004;|&#10004;|支持的 5.0、5.1 (推荐 5.3) |||
|[爱立信](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|vSBC 2.16|&#10004;|||||
|[Cataleya](https://cataleya.com/orchidplatforms/)|Orchid Link|&#10004;||3.1|||
|[ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|Teams SBC|&#10004;|&#10004;|1.6|||
|[Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|Atos Unify OpenScape 会话边界控制器|&#10004;|&#10004;|V10R2.2.0|||
|[Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|vmVSXi|&#10004;|&#10004;|10.5.1.354-vm-S-x64|&#10004;||
|[Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|Dialogic BorderNet SBC|&#10004;|&#10004;|3.9.x|||
|[Patton Electronics Co.](https://www.patton.com/microsoft/)|Patton SmartNode eSBC|&#10004;||3.19.x|||
|[M5 Technologies（前身 Media5 Corporation）](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|Mediatrix Sentinel 系列|&#10004;||DGW 48.0.2340（推荐 DGW 48.1.2503）|||
|[Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|Ekinops Session Border Controller (ONeSBC)|&#10004;|&#10004;|支持的 6.8.x (建议的 6.9.x) |||
||Ekinops Virtual Session Border Controller (ONEvSBC)|&#10004;|&#10004;|支持 6.6.1m5ha1 (建议 6.8.x) |||
|[46 Labs LLC](https://46labs.atlassian.net/wiki/spaces/peeredge/pages/61603842/Microsoft+Teams+Implementation+Guide+v1.0)|对等互连业务流程协调程序|&#10004;|&#10004;|1.0.6|||
|[Frafos](https://www.frafos.com/ms-teams-abc-sbc)|ABC SBC|&#10004;||4.6|||

<br/>

\* **911 服务提供商**

- [带宽动态位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 紧急路由服务 (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado 紧急网关 (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

## <a name="support-for-local-media-optimization"></a>支持本地媒体优化

下表描述了哪些 SBC 供应商支持[本地媒体优化](direct-routing-media-optimization.md)。

|供应商|产品|软件版本|
|:---|:---|:---|
|[Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)|Mediant 500 SBC|7.20A.256|
||Mediant 800 SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 2600 SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 4000 SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 1000B SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 9000 SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 虚拟版本 SBC|支持的 7.20A.258（推荐 7.40A.100）|
||Mediant 云版本 SBC|支持的 7.20A.258（推荐 7.40A.100）|
|[功能区 SBC 核心](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)|SBC 5110|8.2|
||SBC 5210|8.2|
||SBC 5400|8.2|
||SBC 7000|8.2|
||SBC SWe|8.2|
|[功能区 SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)|SBC SWe Lite|8.1.5|
||SBC 1000|8.1.5|
||SBC 2000|8.1.5|
|[TE-SYSTEMS](https://www.anynode.de/local_media_optimization/)|anynode|4.0.1+|
|[Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html)|AP 1100|8.4.0.0.0|
||AP 3900|8.4.0.0.1 & 9.x|
||AP 4600|8.4.0.0.1 & 9.x|
||AP 6300|8.4.0.0.1 & 9.x|
||AP 6350|8.4.0.0.1 & 9.x|
||VME|8.4.0.0.1 & 9.x|
||AP 3950|9.x|
||AP 4900|9.x|
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|适用于企业的 Avaya 会话边界控制器 （ASBCE）|10.1.2|

## <a name="direct-routing-and-analog-devices-interoperability"></a>直接路由和模拟设备互操作性

下表列出了已验证直接路由和模拟设备之间互操作性的设备。

|供应商|产品|已验证
|---|---|---|
|[Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)|&#10004;|
|[Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html)|ATA 191 多平台模拟电话适配器|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 1100 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3900 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4600 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6300 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6350 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|VME 软件版本支持 8.3.0.1.2 &推荐 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3950 软件版本支持 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4900 软件版本支持 9.x|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 1000. 软件版本：8.1.1（内部版本 527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 2000. 软件版本：8.1.1（内部版本 527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 302。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 304。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 2900A。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4806。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4808。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 6000。软件版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|具有 Grandstream GXW42xx 的 anynode (V1.0.7.10)|&#10004;|

请注意授予主要版本的认证。 这意味着主要版本后 SBC 固件中任意编号的固件均受支持。

如要提供有关 Teams 的反馈（例如，新功能的想法），请参阅 [Microsoft 反馈门户](https://feedbackportal.microsoft.com/)。

> [!NOTE]
> 不支持媒体重新定位。 在直接路由呼叫期间，如果 SBC 向 Teams 直接路由发送新的媒体 IP，尽管它是在 SIP 信令中协商的，但媒体永远不会从 Teams 直接路由发送到新的 IP 地址。
