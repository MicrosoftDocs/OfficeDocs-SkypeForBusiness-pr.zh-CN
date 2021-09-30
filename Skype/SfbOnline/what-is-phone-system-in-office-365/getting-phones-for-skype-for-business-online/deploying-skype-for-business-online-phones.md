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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 了解部署步骤，获取正确的固件、根据需要更新固件、分配许可证以及配置在线电话Skype for Business设置
ms.openlocfilehash: b9724677a3217b73b727a72343f35ebe51a4de09
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011896"
---
# <a name="deploying-skype-for-business-online-phones"></a>部署 Skype for Business Online 电话

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

本部署指南将帮助你部署 Skype for Business Online IP 电话。
  
在所有类型的业务中，拥有电话号码允许用户拨打和接听语音呼叫，这是一项重要的业务要求。 拥有电话号码的用户将能够跨所有 Skype for Business设备进行语音呼叫，包括 IP 电话、电脑和移动设备。 有关 IP 电话Skype for Business，可阅读[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
## <a name="deployment-steps-for-ip-phones"></a>部署 IP 电话的步骤

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>第 1 步 - 下载制造商的管理员指南和电话手册

开始之前，最好先下载电话制造商的管理指南和电话用户手册。
  
- 对于 Polycom 电话，请参阅 [Poly 文档库](https://documents.polycom.com/category/voice)。
    
- 有关 Yealink 电话，请参阅[Yealink Skype for Business HD SIP 电话解决方案](http://www.yealink.com/products_top_2.html)。
    
- 对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件

支持 Skype for Business Online 的电话和固件也兼容 Skype for Business Server，反之则不一定成立。 若要确保购买或预配受支持的电话和固件，请参阅获取适用于 Skype for Business [Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。

检查手机上的固件版本。 对于：
  
- **Polycom VVX 电话**，请转到 **设置** > **状态** > **平台** > **应用程序** > **主要**。
    
- **Yealink 电话** ，请转到电话主屏幕上的" **状态** "。
    
- **AudioCodes 电话**，请转到开始菜单的 **菜单** > **设备状态** > **固件版本**。
    
    > [!NOTE]
    > 有关远程访问电话的详细信息，请参阅制造商管理指南。 请通过上面的链接获取用户指南和电话手册。 
  
- **Lync Phone Edition (LPE) 电话**，请转到开始屏幕的 **菜单** > **系统信息**。
    
### <a name="step-4---device-update-considerations"></a>第 4 步 - 设备更新注意事项

> [!NOTE]
> 5.5.1.X 之前的 Polycom 固件具有特定于制造商的设备锁机制，该机制已替换为 Skype for Business 实现"电话-Lock"。 将使用"Device-Lock"保护的手机从 5.4.X.X 升级到具有"电话-Lock"的 5.5.1.X 不会从"Device-Lock"继承 PIN 码，因此手机可能不安全。 已激活"Device-Lock"的用户需要启用以下 Polycom 设备配置文件参数，以便用户控制 (lync.deviceUpdate.popUpSK.enabled=1) 的升级时间。 
  
固件更新由 Skype for Business 服务管理。 每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。 根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。 可以使用 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet 将 _EnableDeviceUpdate_ 参数设置为 来禁用设备更新设置 `false` 。
  
![显示部署手机的屏幕截图。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
新固件可用且能够进行下载和安装时，电话会通知用户。 Polycom 电话将通知用户，并为用户提供"更新 **"或** "推迟 **"选项**。
  
![显示"更新"和"推迟"选项的屏幕截图。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。
  
![显示"SwUpdate"选项的屏幕截图。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。
  
> [!CAUTION]
> [!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>步骤 5 - 配置和基础结构电话设置

你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy)。
  
有关网络基础结构规划，请参阅[operations Framework Skype。](https://www.skypeoperationsframework.com/)
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>步骤 6 - 准备让用户登录

若要让用户成功登录到 Skype for Business Online 电话并拨打电话，需要确保为用户分配正确的许可证。 至少需要分配一个电话系统和呼叫计划。 有关其他信息，可参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 和 [分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
  
有关通话套餐的更多内容，电话系统[和通话套餐](/microsoftteams/calling-plan-landing-page)
  
- Online 用户可以使用的 **登录选项** 包括：
    
  - 使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：
    
     ![显示 Polycom 电话登录的屏幕截图。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - 使用 **Yealink T48G/T46G 电话** 的用户将看到：
    
     ![显示 Yealink 手机登录的屏幕截图。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    有关制造商支持的登录选项的详细信息，请参阅获取适用于 Skype for Business [Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。
    
     ![显示登录屏幕的屏幕截图。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。 
  
- **使用电脑** 在用户的电脑上安装并 (BToE) 软件后，用户可以使用其 Windows Skype for Business 应用中的身份验证窗口登录到其手机。 有关[其他信息，Skype Operations Framework (SOF) Skype Academy？。](https://techcommunity.microsoft.com/t5/skype-for-business-blog/what-is-skype-operations-framework-sof-and-skype-academy/ba-p/30506)
    
  > [!NOTE]
  > [!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。
  
     ![显示登录屏幕的屏幕截图。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **使用 Web 登录**：这是联机用户使用标准 Web 浏览器进行身份验证的一种新方式。 当用户使用浏览器登录时，将为用户提供一组要遵循的说明。
    
  - 使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：
    
     ![显示 Polycom 说明的屏幕截图。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - 使用 **Yealink T48G/T46G 电话** 的用户将看到：
    
     ![显示 Yealink 说明的屏幕截图。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    生成的代码将于 15 分钟后过期。 到期时，用户必须单击"重试"或"确定"以生成新代码，具体取决于手机。
    
  - 使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：
    
     ![显示已过期 Polycom 代码的屏幕截图。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - 使用 **Yealink T48G/T46G 电话** 的用户将看到：
    
     ![显示过期的 Yealink 代码的屏幕截图。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。
    
     ![显示电子邮件验证的屏幕截图。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    输入电话上显示的代码。
    
     ![显示登录屏幕上的输入代码的屏幕截图。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    验证站点是否显示"[电话制造商名称] **Skype for Business认证** 电话"，然后单击"继续 **"。**
    
     ![显示名称验证的屏幕截图。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    单击用户的凭据或单击" **使用其他帐户**"：
    
     ![显示凭据选项的屏幕截图。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    显示以下页面时，可以安全地关闭浏览器。
    
     ![显示确认消息的屏幕截图。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。 
  
- **支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。

  
 
 
|Skype for Business |Exchange |电话登录方法 |Skype for Business访问权限 |禁用新式验证和 MFA 的 Exchange 访问 |启用新式验证和 MFA 的 Exchange 访问 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Online   |Online   |Web 登录   |是   |是   |是   |
|Online   |Online   |用户名/密码   |是   |是   |否   |
|Online   |本地部署   |Web 登录   |是   |否   |否   |
|Online   |本地部署   |用户名/密码   |是   |是   |否   |
|本地部署   |Online/本地部署   |PIN 身份验证   |是   |否   |否   |
|本地部署   |Online/本地部署   |用户名/密码   |是   |是   |不适用   |
|本地部署   |Online/本地部署   |通过 PC 登录 (BTOE)  |是   |是   |不适用   |
   
- **电话功能** 根据 IP 电话合作伙伴，功能集可能会略有不同。 有关完整功能集和各电话制造商的功能的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **电话锁定** Skype for Business 认证电话新近引入的用于保护电话的功能。 如果启用，用户将被要求在身份验证成功后创建一个 PIN。 一旦创建，当定义的空闲超时过期、 用户手动锁定其电话或使用电话配使其电话锁定与其 PC 锁定同步时，电话将锁定。 如果多次输错电话锁定 PIN，电话会将此用户注销或要求输入管理员的代码才能解锁电话，但不同电话合作伙伴在这方面的要求有所差异。 用户的 PIN 应为 6-15 位数字。
    
    你可以为Phone-Lock禁用 (默认启用的) ，更改空闲超时，并选择用户是否可以在锁定时进行电话呼叫或不使用带内设置。 有关[这些设置的更多详细信息，请参阅 Set-CsUCPhoneConfiguration。](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE 是合作伙伴 IP 电话的一种电话处理机制，用于将用户的手机与他们的 Windows Skype for Business 应用配对。 利用 BToE，用户可以：
  
- 使用电脑设备通过 Skype for Business 桌面应用 (登录到其 IP) 
    
- 将Phone-Lock电脑锁同步
    
- 单击以呼叫
    
BToE 可以配置为在两种模式下运行：自动 (默认) *手动。* 也可以为使用 Skype for Business 带内设置的用户启用（默认）/禁用此功能。 采用 *手动*  模式运行时，用户还必须执行其他步骤，以便将其电话与其 Windows 应用配对。
  
 **将 BToE 部署到用户**
  
1. 使用 PC 端口将 PC 与电话相连。
    
     ![显示与电脑连接的屏幕截图。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。 若要获得更好的用户体验，可以使用管理员分发解决方案（如 Microsoft 终结点配置管理器）分发和安装 BToE 软件。 有关使用 Configuration Manager 的帮助，请参阅 Configuration [Manager 中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。
    
   - [Polycom BToE 软件下载站点](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToE 软件下载](http://www.yealink.com/products_list_10.html)
    
   - [AudioCodes BToE 软件下载](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. 默认情况下，BToE 的服务器设置设置为 **"已启用****"和"自动** 模式"。 若要更改这些设置，请参阅[设置 CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) 。
    
> [!NOTE]
> [!注释] Mac 和 VDI 平台目前不支持 BToE。 
  
## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

