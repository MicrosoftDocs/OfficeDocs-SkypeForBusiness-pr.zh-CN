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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解哪些电话可从 Polycom、HP 和 Mitel 使用 Skype for Business，以及需要的许可证。 '
ms.openlocfilehash: e79c942923e9a9d4d0df0bc18172eb10caff57bc
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952394"
---
# <a name="getting-phones-for-skype-for-business-online"></a>获取适用于 Skype for Business Online 的电话

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
若要获取最新的更新和受支持的设备上的大多数最新信息，请参阅[Skype 业务设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
## <a name="supported-phones"></a>支持的电话

为业务 Online 用户 Skype，您可以从多个模型中*的业务电话的 Skype Certified*选择和电话运行 Lync Phone Edition (LPE) 列出下[Skype 中的业务联机类别 Skype 业务设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
Microsoft 是合作，紧密合作 Polycom、 Yealink，与 AudioCodes 开发和业务服务器的 Office 365 和 Skype 中的电话系统确认各种设备通过合作伙伴 IP 电话程序 （点数）。
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**电话合作伙伴** <br/> |**Skype for Business 特定产品 ID** <br/> |
|Polycom  <br/> |产品 ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
有关 Polycom 电话的更多详细信息，请参阅 [Microsoft 的语音解决方案](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
  
有关 Yealink 电话的更多详细信息，请参阅 [Skype for Business IP 电话](http://www.yealink.com/products_list_10.html#filter2)。
  
AudioCodes 电话的详细信息，请参阅[业务 IP 电话的 Skype](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
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

当前已认证的固件版本的详细信息，请参阅[业务 IP 电话的 Skype](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones)。

> [!NOTE]
> [!注释] 你为本地部署设置的 Lync Phone Edition (LPE) 电话必须加以更新，以符合最低或最新的必要固件要求，之后才能将这些用户转移到 Skype for Business Online。如果在更新电话上的固件之前将用户从本地部署迁移到 Skype for Business Online，这些电话将无法连接到 Skype for Business Online。 
  
## <a name="required-licenses"></a>必需的许可证

Skype 业务 online 不需要任何其他的 Microsoft 许可之外的用户许可证。 若要了解有关所需的用户许可证的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
打开 SIP 和 Skype 之间业务认证固件的情况下，制造商许可模型可能会有所不同。 如果打算对开放式 SIP 固件重复使用某个认证模式，则需要向制造商确认固件许可证要求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>业务 Online 连接的电话功能集的的 Skype

有关完整的设备特性和功能，检查制造商用户指南。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**功能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|使用用户凭据登录  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|通过 PC（配对）登录，仅限 Windows  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|使用（Web 登录）登录  <br/>  <br/> **注意：** 检查部署指南中的可支持性矩阵。           |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|通过单击加入会议  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|单击拨号（配对）  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|会议控制  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|可视语音邮件  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|电话锁定  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|设备更新  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|带内配置  <br/> |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|QoE  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|日志上传  <br/> <br/> **注意：** 目前，所有日志都上载到 Microsoft 支持团队仅;客户访问电话日志尚不可用。           |是  <br/> |是  <br/> |是  <br/> |是   <br/> |
|现代化身份验证  <br/> |是  <br/> |是  <br/> |是   <br/> |否  <br/> |
|多个紧急号码  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange 日历集成*  <br/> |是  <br/> |是  <br/> |是   <br/> |是   <br/> <br/> **注意：** 需要 PC tethering           |
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

  
 
