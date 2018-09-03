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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: '了解哪些电话可从 Polycom、HP 和 Mitel 使用 Skype for Business，以及需要的许可证。 '
ms.openlocfilehash: 92a91d97efabeaaebb074e41e41bc9a8812fa0c5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780606"
---
# <a name="getting-phones-for-skype-for-business-online"></a>获取适用于 Skype for Business Online 的电话

对于希望更喜欢传统电话体验而非不想使用 Skype for Business 应用的用户，Skype for Business Online 提供使用座机的条件和支持。本主题介绍在 Skype for Business Online 中支持使用的电话和固件版本，以及在你为组织设置电话时能够为你提供帮助的其他信息。
  
要获取有关受支持设备的最新更新和最新信息，请参阅 [Skype for Business 设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
## <a name="supported-phones"></a>支持的电话

对于 Skype for Business Online 用户，可以选择范围包括 *Skype for Business 认证电话*中提供的多种型号，以及[ Skype for Business 设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)中 Skype for Business Online 类别下所列的运行 Lync Phone Edition (LPE) 的电话。
  
Microsoft 与 Polycom、Yealink 和 AudioCodes 有合作关系，并与他们密切协作，通过 Office 365 中的电话系统和 Skype for Business Server 的合作伙伴 IP 电话计划 (PIP)，开发并认证各种设备。
  
订购用于 Skype for Business 的新电话时，请务必购买具有*正确产品 ID* 的电话。这些产品 ID 可确保你收到的电话已经安装了经认证的 Skype for Business Online 版本。
  
|||
|:-----|:-----|
|**电话合作伙伴** <br/> |**Skype for Business 特定产品 ID** <br/> |
|Polycom  <br/> |产品 ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
有关 Polycom 电话的更多详细信息，请参阅 [Microsoft 的语音解决方案](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
  
有关 Yealink 电话的更多详细信息，请参阅 [Skype for Business IP 电话](http://www.yealink.com/products_list_10.html#filter2)。
  
有关 AudioCodes 电话的更多详细信息，请参阅 [Skype for Business IP 电话](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync Phone Edition 受 Skype for Business Online 支持，但是不受 Microsoft Teams 支持。对 LPE 平台的主流支持于 2014 年 4 月 10 日结束，扩展支持将持续到 2023 年 4 月 11 日，以便与 Lync Server 2013 的产品支持生命周期保持一致。有关 LPE 生命周期的详细信息，请参阅 [Microsoft 产品生命周期](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO)。Skype for Business Online 不支持 LPE CAP 模式。
>
> 在今年晚些时候，Office 365 将不支持任何早于 1.2 版本的 TLS。 由于 LPE 底层操作系统不支持 TLS 1.2，将不支持 LPE 连接到 Office 365。 如需了解更多信息，请参阅[为 TLS 1.2 在 Office 365 中的强制使用做准备](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) 。
  
## <a name="supported-firmware"></a>支持的固件

这里是受支持的电话使用 Office 365 中电话系统所需的最低软件版本：
  
||||
|:-----|:-----|:-----|
|**电话类型** <br/> |**最低固件** <br/> |**发布日期** <br/> |
|优化 (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |2015 年 5 月  <br/> |
|已认证的 Polycom VVX 系列  <br/> |5.4.0A  <br/> |2015 年 12 月  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |2017 年 2 月  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |2016 年 12 月  <br/> |
   
> [!NOTE]
[!注释] 你为本地部署设置的 Lync Phone Edition (LPE) 电话必须加以更新，以符合最低或最新的必要固件要求，之后才能将这些用户转移到 Skype for Business Online。如果在更新电话上的固件之前将用户从本地部署迁移到 Skype for Business Online，这些电话将无法连接到 Skype for Business Online。 
  
## <a name="required-licenses"></a>所需的许可证

除用户许可证外，Skype for Business Online 不需要任何其他 Microsoft 许可证。 若要了解有关所需用户许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 附加许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
开放式 SIP 和 Skype for Business 认证固件的制造商许可模式可能有所差异。 如果打算对开放式 SIP 固件重复使用某个认证模式，则需要向制造商确认固件许可证要求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Online 连接电话功能集

有关完整的设备功能和特性，请查看制造商用户指南。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**功能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|使用用户凭据登录  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|通过 PC（配对）登录，仅限 Windows  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|使用（Web 登录）登录  <br/>  <br/> **注：** 查看部署指南中的可支持性矩阵表。           |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|通过单击加入会议  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|单击拨号（配对）  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|会议控制  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|可视语音邮件  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|电话锁定  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|设备更新  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|带内配置  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|QoE  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|日志上传  <br/> <br/> **注：** 目前，所有日志仅上传到 Microsoft 支持团队，客户尚不能访问电话日志。           |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|现代化身份验证  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|多个紧急号码  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange 日历集成*  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> <br/> **注：** 需要 PC 数据连线           |
|状态集成  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|公司目录  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|委派  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|联系人图片集成  <br/> |否  <br/> |是  <br/> |否  <br/> |是  <br/> |
||||||

     
> [!NOTE]
> CX 600 或任何其他 Aries 电话不支持多因素身份验证 (MFA)。 如果强制采用 MFA，这些设备将无法登录。 这些设备必须仅使用组织 ID 进行身份验证。
 
## <a name="what-else-should-you-know"></a>还需了解其他哪些信息？
有关分步设置说明，请参阅[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](../getting-service-phone-numbers.md)

[Office 365 中的电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 