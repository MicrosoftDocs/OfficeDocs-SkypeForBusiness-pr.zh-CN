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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: '了解哪些电话可从 Polycom、HP 和 Mitel 使用 Skype for Business，以及需要的许可证。 '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013146"
---
# <a name="getting-phones-for-skype-for-business-online"></a>获取适用于 Skype for Business Online 的电话

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype for Business对于想要使用传统手机体验而不是使用桌面手机应用的用户，Online 限定并支持Skype for Business电话。 本主题介绍支持在 Skype for Business Online 中使用的电话和固件版本，以及当您在组织中设置电话时可提供帮助的其他信息。

> [!NOTE]
> SkypeFor Business 将缓慢地被 Microsoft Teams 替换为 Microsoft 365 和 Office 365。  有关详细信息[，请参阅](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/)Office 365 智能通信的新愿景。
>
>若要获取有关受支持设备的最新更新和最新信息，请参阅智能通信Microsoft Teams[设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。
  
## <a name="supported-phones"></a>支持的电话
  
Microsoft 与 Polycom、Yealink 和 AudioCodes 密切合作，通过适用于 电话系统 的合作伙伴 IP 电话 计划 (PIP) 开发和认证各种设备。
  
为手机订购Skype for Business时，必须购买具有正确 *产品 ID 的电话*。 这些产品 ID 将确保你收到的电话已安装Skype for Business在线限定版本。
  
|电话合作伙伴  |Skype for Business 特定产品 ID  |
|:-----|:-----|
|Polycom   |产品 ID -019   |
|Yealink   |SIP-TXXG Skype for Business Edition   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
有关 Polycom 电话的更多详细信息，请参阅 [Poly 文档库](https://documents.polycom.com/category/voice)。
  
有关 Yealink 电话的更多详细信息，请参阅 [Skype for Business IP 电话](http://www.yealink.com/products_list_10.html#filter2)。
  
有关 AudioCodes 电话的更多详细信息，请参阅[Skype for Business IP 电话](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync Phone Edition 支持 Skype for Business Online，但不支持 Microsoft Teams。 对 LPE 平台的主流支持于 2014 年 4 月 10 日结束，扩展支持将持续到 2023 年 4 月 11 日，以便与 Lync Server 2013 的产品支持生命周期保持一致。 有关 LPE 生命周期的详细信息，请参阅 [Microsoft 产品生命周期](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO)。 LPE CAP 型号不支持 Skype for Business Online。
>
> 今年晚些时候，Office 365不支持任何版本低于 1.2 的 TLS。 由于 LPE 底层操作系统不支持 TLS 1.2，将不支持 LPE 连接到 Office 365。 如需了解更多信息，请参阅[为 TLS 1.2 在 Office 365 中的强制使用做准备](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) 。
  
## <a name="supported-firmware"></a>支持的固件

这是受支持的电话使用以下设备所需的最低软件版本电话系统：
  

|电话类型 |最低固件 |发布日期 |
|:-----|:-----|:-----|
|优化 (Lync Phone Edition)   |4.0.7577.4463   |2015 年 5 月   |
|已认证的 Polycom VVX 系列   |5.4.0A   |2015 年 12 月   |
|Yealink   |X.8.1.52   |2017 年 2 月   |
|AudioCodes   |3.0.0.459.1   |2016 年 12 月   |

有关当前认证的固件版本的更多详细信息，请参阅 Skype for Business [IP 电话](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

> [!NOTE]
> [!注释] 你为本地部署设置的 Lync Phone Edition (LPE) 电话必须加以更新，以符合最低或最新的必要固件要求，之后才能将这些用户转移到 Skype for Business Online。如果在更新电话上的固件之前将用户从本地部署迁移到 Skype for Business Online，这些电话将无法连接到 Skype for Business Online。 
  
## <a name="required-licenses"></a>所需的许可证

Skype for Business除用户许可证外，Online 不需要任何其他 Microsoft 许可证。 若要详细了解所需的用户许可证，请参阅Skype for Business和Microsoft Teams[附加许可。](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
开放式 SIP 和经认证的固件的制造商Skype for Business模型可能有所不同。 如果打算对开放式 SIP 固件重复使用某个认证模式，则需要向制造商确认固件许可证要求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business联网电话功能集

有关完整的设备特性和功能，请查看制造商用户指南。
  

|功能  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|使用用户凭据登录   |是  |是   |是   |否   |
|通过 PC（配对）登录，仅限 Windows   |是   |是   |是   |是   |
|使用（Web 登录）登录  <br/>  <br/> **注意：** 查看部署指南中的可支持性矩阵。  |是   |是   |是   |否   |
|通过单击加入会议   |是   |是   |是   |是   |
|单击拨号（配对）   |是   |是   |是   |是> |
|会议控制   |是   |是   |是   |是   |
|可视语音邮件   |是   |是   |是   |是   |
|电话锁定   |是   |是   |是   |是   |
|设备更新   |是   |是   |是   |是   |
|带内配置   |是   |是   |是   |是   |
|QoE   |是   |是   |是   |否  |
|日志上传  <br/> <br/> **注意：** 目前，所有日志仅上传到 Microsoft 支持团队;客户对电话日志的访问尚不可用。           |是   |是   |是   |是   |
|现代化身份验证   |是   |是   |是   |否   |
|多个紧急号码   |是   |否   |否   |是   |
|Exchange 日历集成*   |是   |是   |是   |是  <br/> <br/> **注意：** 需要电脑连接           |
|状态集成   |是   |是   |是   |是   |
|公司目录   |是   |是   |是   |是   |
|委派   |是   |是   |是   |否   |
|联系人图片集成   |否   |是  |否   |是   |


     
> [!NOTE]
> CX 600 或任何其他 Aries 电话不支持多因素身份验证 (MFA)。 如果强制采用 MFA，这些设备将无法登录。 这些设备必须仅使用组织 ID 进行身份验证。
 
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？
有关分步设置说明，请参阅[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
