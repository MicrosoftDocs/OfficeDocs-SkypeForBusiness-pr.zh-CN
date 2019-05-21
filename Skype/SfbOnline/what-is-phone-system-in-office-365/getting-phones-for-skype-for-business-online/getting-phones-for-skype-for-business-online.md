---
title: 获取适用于 Skype for Business Online 的电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解哪些电话可从 Polycom、HP 和 Mitel 使用 Skype for Business，以及需要的许可证。 '
ms.openlocfilehash: f3a042a200f821f6e5836eb3fc6b062a88e2da35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297995"
---
# <a name="getting-phones-for-skype-for-business-online"></a>获取适用于 Skype for Business Online 的电话

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
若要获取有关受支持设备的最新更新和最新信息, 请参阅[Skype For Business 设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
## <a name="supported-phones"></a>支持的电话

对于 Skype for Business Online 用户, 您可以从在 skype for business 设备的 Skype for business Online 类别下列出的已*认证的 skype for Business 电话*和电话 (LPE) 中选择多个型号[目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
Microsoft 致力于与 Polycom、Yealink 和 AudioCodes 密切合作, 通过 Office 365 和 Skype for business 服务器中的 "合作伙伴 IP 电话计划" (PIP) 为各种设备进行开发和认证。
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**电话合作伙伴** <br/> |**Skype for Business 特定产品 ID** <br/> |
|Polycom  <br/> |产品 ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
有关 Polycom 电话的更多详细信息，请参阅 [Microsoft 的语音解决方案](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
  
有关 Yealink 电话的更多详细信息，请参阅 [Skype for Business IP 电话](http://www.yealink.com/products_list_10.html#filter2)。
  
有关 AudioCodes 电话的更多详细信息, 请参阅[Skype for BUSINESS IP 手机](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online, but not with Microsoft Teams. Mainstream support for the LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on the LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
>
> Later this year, Office 365 will not support any version of TLS older than 1.2. Since the underlying operating system of LPE does not support TLS 1.2, LPE will not be supported to connect to Office 365 anymore. See [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) for more information.
  
## <a name="supported-firmware"></a>支持的固件

这里是受支持的电话使用 Office 365 中电话系统所需的最低软件版本：
  
||||
|:-----|:-----|:-----|
|**电话类型** <br/> |**最低固件** <br/> |**发布日期** <br/> |
|优化 (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |2015 年 5 月  <br/> |
|已认证的 Polycom VVX 系列  <br/> |5.4.0A  <br/> |2015 年 12 月  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |2017 年 2 月  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |2016 年 12 月  <br/> |

有关当前认证的固件版本的更多详细信息, 请参阅[Skype for BUSINESS IP 手机](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones)。

> [!NOTE]
> [!注释] 你为本地部署设置的 Lync Phone Edition (LPE) 电话必须加以更新，以符合最低或最新的必要固件要求，之后才能将这些用户转移到 Skype for Business Online。如果在更新电话上的固件之前将用户从本地部署迁移到 Skype for Business Online，这些电话将无法连接到 Skype for Business Online。 
  
## <a name="required-licenses"></a>所需的许可证

Skype for business Online 不需要除用户许可证之外的任何其他 Microsoft 许可证。 若要了解有关所需用户许可证的详细信息, 请参阅[Skype for business 和 Microsoft 团队附加许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
制造商许可模型可能因打开的 SIP 和 Skype for Business 认证固件而异。 如果打算对开放式 SIP 固件重复使用某个认证模式，则需要向制造商确认固件许可证要求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Online 连接的手机功能集

有关完整设备功能和功能, 请查看制造商用户指南。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**功能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|使用用户凭据登录  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|通过 PC（配对）登录，仅限 Windows  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|使用（Web 登录）登录  <br/>  <br/> **注意:** 检查部署指南中的 "可支持性" 矩阵。           |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|通过单击加入会议  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|单击拨号（配对）  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|会议控制  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|可视语音邮件  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|电话锁定  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|设备更新  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|带内配置  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|QoE  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|日志上传  <br/> <br/> **注意:** 目前, 所有日志仅上载到 Microsoft 支持团队;客户对电话日志的访问尚不可用。           |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|现代化身份验证  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|多个紧急号码  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange 日历集成*  <br/> |是  <br/> |是  <br/> |是   <br/> |是   <br/> <br/> **注意:** 需要 PC tethering           |
|状态集成  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|公司目录  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|委派  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|联系人图片集成  <br/> |否  <br/> |是  <br/> |否  <br/> |是  <br/> |
||||||

     
> [!NOTE]
> CX 600 或任何其他 Aries 电话不支持多因素身份验证 (MFA)。 如果强制采用 MFA，这些设备将无法登录。 这些设备必须仅使用组织 ID 进行身份验证。
 
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？
有关分步设置说明，请参阅[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](../getting-service-phone-numbers.md)

[以下是 Office 365 中的电话系统功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
