---
title: 经认证可用于直接路由的会话边界控制器列表
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: Microsoft 合作伙伴与选定的 SBC 供应商认证其 SBC 可用于直接路由。
ms.openlocfilehash: b574911c2d819e665f088ec8be12f24e1830daf2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837582"
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
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20   |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20   |    |    |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20   |     |    |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20   |     |    |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  7.20  |    |    |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  7.20   |    |    |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20 |    |    |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 7。2       |  Intrado ERS <br>Intrado EGW |   否 |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 7。2       |   Intrado ERS <br>Intrado EGW  | 否   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 7。2       |  Intrado ERS <br>Intrado EGW    |否|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 7。2       |   Intrado ERS <br>Intrado EGW  |  否  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 7。2       |   Intrado ERS <br>Intrado EGW |   否 |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.3 （内部版本537）     |  Intrado ERS <br>Intrado EGW   |  Pending  |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.3 （内部版本537）     |  Intrado ERS <br>Intrado EGW  |  Pending  |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.3 （内部版本216）    |  Intrado ERS <br>Intrado EGW   |  Pending  |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |   Pending    |       V1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   Intrado ERS <br>Intrado EGW  |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |   Intrado ERS <br>Intrado EGW  |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   Intrado ERS <br>Intrado EGW |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  Intrado ERS <br>Intrado EGW  |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   Intrado ERS <br>Intrado EGW |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   Intrado ERS <br>Intrado EGW  |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |     |    |    

若要向我们提供有关团队的产品反馈（如新功能的创意），请参阅[Uservoice](https://microsoftteams.uservoice.com)注意授予主要版本的证书。 这意味着支持在主要版本之后的 SBC 固件中包含任何数字的固件。
