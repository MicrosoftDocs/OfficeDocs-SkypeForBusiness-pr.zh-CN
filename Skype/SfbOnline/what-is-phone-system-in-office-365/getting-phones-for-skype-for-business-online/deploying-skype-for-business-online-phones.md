---
title: 部署 Skype for Business Online 电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 了解部署步骤以获取正确的固件、根据需要进行更新、分配许可证并配置 Skype for Business Online 电话设置。
ms.openlocfilehash: 3b695f0198e5edb23a8746babb071742d7b7712f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860456"
---
# <a name="deploying-skype-for-business-online-phones"></a>部署 Skype for Business Online 电话

本部署指南将帮助你部署 Skype for Business Online IP 电话。
  
在所有类型的企业中，拥有电话号码便于用户拨打和接听语音呼叫，这也是开展业务的重要要求。 拥有电话号码的用户将能够跨各种 Skype for Business 设备进行语音通话，包括 IP 电话、PC 和移动设备。 如需了解有关 Skype for Business IP 电话的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
## <a name="deployment-steps-for-ip-phones"></a>部署 IP 电话的步骤

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>第 1 步 - 下载制造商的管理员指南和电话手册

开始之前，最好先下载电话制造商的管理指南和电话用户手册。
  
- 有关 Polycom 电话，请参阅 [Polycom 部署指南] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
    
- 对于 Yealink 电话，请参阅 [Yealink Skype for Business HD SIP 电话解决方案](http://www.yealink.com/products_top_2.html)。
    
- 对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件

支持 Skype for Business Online 的电话和固件也兼容 Skype for Business Server，反之则不一定成立。 要确保你购买或配置的是受支持的电话和固件，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。

检查电话上的固件版本。 对于：
  
- **Polycom VVX 电话**，请转到**设置** > **状态** > **平台** > **应用程序** > **主要**。
    
- **Yealink 电话** ，请转到电话主屏幕上的" **状态** "。
    
- **AudioCodes 电话**，请转到开始菜单的**菜单** > **设备状态** > **固件版本**。
    
    > [!NOTE]
    > 有关远程访问电话的详细信息，请参阅制造商管理指南。 请通过上面的链接获取用户指南和电话手册。 
  
- **Lync Phone Edition (LPE) 电话**，请转到开始屏幕的**菜单** > **系统信息**。
    
### <a name="step-4---device-update-considerations"></a>第 4 步 - 设备更新注意事项

> [!NOTE]
> 5.5.1.X 之前的 Polycom 固件拥有一个特定于制造商的设备锁定机制，该机制已被替换为 Skype for Business 实施"电话锁定"。 将电话从使用“设备锁定”确保安全性的 5.4.X.X 升级到使用"电话锁定"的 5.5.1.X 不会继承“设备锁定”的 PIN 码，这会导致电话不安全。 对于已经激活“设备锁定”的用户，需要启用以下 Polycom 设备配置文件参数，以便为用户提供对升级时间的控制 (lync.deviceUpdate.popUpSK.enabled=1)。 
  
固件更新由 Skype for Business 服务管理。 每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。 根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。 你可以通过使用 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将 _EnableDeviceUpdate_ 参数设置为 `false` 来禁用设备更新设置。
  
![部署电话。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
新固件可用且能够进行下载和安装时，电话会通知用户。 Polycom 电话会通知用户并让用户选择"**更新**"或"**推迟更新** "。
  
![部署电话。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。
  
![部署电话。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。
  
> [!CAUTION]
> [!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>第 5 步 - 配置和基础结构电话设置

你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。
  
有关网络基础结构规划，请参阅 [Skype Operations Framework](https://www.skypeoperationsframework.com/)。
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>第 6 步 - 为用户登录做准备

要使用户能够成功登录 Skype for Business Online 电话并进行通话，需要确保为用户分配正确的许可证。 至少需要分配电话系统许可证和通话套餐。 有关其他信息，可参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 和 [分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
  
有关通话套餐的详细信息，请参阅[什么是 Office 365 的通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365)
  
- Online 用户可以使用的 **登录选项** 包括：
    
  - 使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![部署电话。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - 使用 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink 电话登录。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    有关制造商支持的登录选项的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 *amosm@contoso.com*  的 UPN 格式作为其用户名。
    
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。 
  
- **使用 PC** 如果用户 PC 上安装并启用了 Better Together over Ethernet (BToE) 软件，用户可以使用其 Windows Skype for Business 应用上的身份验证窗口登录其电话。 有关其他信息，请参阅[第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE)。
    
    > [!NOTE]
    > [!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  *amosm@contoso.com*  的 UPN 格式作为其用户名。
  
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **使用Web 登录**：这是联机户使用标准 Web 浏览器进行身份验证的新方式。 当用户使用浏览器登录时，会收到一套需要遵循的说明。
    
  - 使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![部署电话。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - 使用 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink 电话登录。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    生成的代码将于 15 分钟后过期。 代码过期后，用户必须单击"**重试**"或"**确定**"，以便根据电话生成新代码。
    
  - 使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![PIN 代码已过期。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - 使用 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink 电话登录。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。
    
     ![部署电话。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    输入电话上显示的代码。
    
     ![部署电话。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    确认站点显示"[电话制造商名称] **Skype for Business 认证电话**"，然后单击" **继续**"。
    
     ![部署电话。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    单击用户的凭据或单击" **使用其他帐户**"：
    
     ![部署电话。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    显示下面的页面后，便可以安全地关闭浏览器。
    
     ![部署电话。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。 
  
- **支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**交换** <br/> |**电话登录方法** <br/> |**Skype For Business 访问** <br/> |**禁用新式验证和 MFA 的 Exchange 访问** <br/> |**启用新式验证和 MFA 的 Exchange 访问** <br/> |
|Online  <br/> |Online  <br/> |Web 登录  <br/> |是  <br/> |是  <br/> |是  <br/> |
|Online  <br/> |Online  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |Web 登录  <br/> |是  <br/> |否  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |PIN 身份验证  <br/> |是  <br/> |否  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |不适用  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |通过 PC 登录 (BTOE)  <br/> |是  <br/> |是  <br/> |不适用  <br/> |
   
- **电话功能** 不同 IP 电话合作伙伴的功能集可能会略有不同。 有关完整功能集和各电话制造商的功能的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **电话锁定** Skype for Business 认证电话新近引入的用于保护电话的功能。 如果启用，用户将被要求在身份验证成功后创建一个 PIN。 一旦创建，当定义的空闲超时过期、 用户手动锁定其电话或使用电话配使其电话锁定与其 PC 锁定同步时，电话将锁定。 如果多次输错电话锁定 PIN，电话会将此用户注销或要求输入管理员的代码才能解锁电话，但不同电话合作伙伴在这方面的要求有所差异。 用户的 PIN 应为 6-15 位数字。
    
    可以为组织禁用电话锁定（默认情况下处于启用状态）、更改空闲超时时间并选择用户在处于锁定状态或不使用带内设置时是否可以进行电话通话。 有关这些设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE 是适用于合作伙伴 IP 电话的电话配对机制，用于将用户的电话与其 Windows Skype for Business 应用进行配对。 利用 BToE，用户可以：
  
- 使用其 Skype for Business 桌面应用（使用 PC）登录其 IP 电话
    
- 使电话锁定与 PC 锁定同步
    
- 单击进行呼叫
    
BToE 可以配置为采用两种模式运行：*自动*  （默认）和*手动*。 也可以为使用 Skype for Business 带内设置的用户启用（默认）/禁用此功能。 采用 *手动*  模式运行时，用户还必须执行其他步骤，以便将其电话与其 Windows 应用配对。
  
 **为用户部署 BToE**
  
1. 使用 PC 端口将 PC 与电话相连。
    
     ![部署电话。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。要获取更好的用户体验，可以使用 System Center Configuration Manager (SCCM) 等管理员分发解决方案来分发并安装 BToE 软件。有关使用 SCCM 的帮助，请参阅[ System Center Configuration Manager 中的软件包和程序](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)。
    
  - [Polycom BToE 软件下载网站](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Yealink BToE 软件下载](http://www.yealink.com/products_list_10.html)
    
  - [AudioCodes BToE 软件下载](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. 默认情况下，BToE 的服务器设置设为已启用和自动模式。** ** ** ** 若要更改这些设置，请参阅[设置 CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) 。
    
> [!NOTE]
> [!注释] Mac 和 VDI 平台目前不支持 BToE。 
  
## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Office 365 中的电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
