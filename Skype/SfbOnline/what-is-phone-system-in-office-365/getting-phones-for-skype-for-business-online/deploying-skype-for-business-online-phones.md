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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 了解部署步骤以获取正确的固件、根据需要更新、分配许可证以及配置 Skype for Business online 手机的设置
ms.openlocfilehash: f4f1a36e5a2e98c4566a81b41bc6e6c281ac9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113145"
---
# <a name="deploying-skype-for-business-online-phones"></a>部署 Skype for Business Online 电话

本部署指南将帮助你部署 Skype for Business Online IP 电话。
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>部署 IP 电话的步骤

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>第 1 步 - 下载制造商的管理员指南和电话手册

开始之前，最好先下载电话制造商的管理指南和电话用户手册。
  
- 对于 Polycom 电话，请参阅[Poly 文档库](https://documents.polycom.com/category/voice)。
    
- 对于 Yealink 电话，请参阅[Yealink Skype for BUSINESS HD SIP 手机解决方案](http://www.yealink.com/products_top_2.html)。
    
- 对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。

Check the firmware version on your phones. For:
  
- **Polycom VVX 电话**，请转到**设置** > **状态** > **平台** > **应用程序** > **主要**。
    
- **Yealink 电话** ，请转到电话主屏幕上的" **状态** "。
    
- **AudioCodes 电话**，请转到开始菜单的**菜单** > **设备状态** > **固件版本**。
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- **Lync Phone Edition (LPE) 电话**，请转到开始屏幕的**菜单** > **系统信息**。
    
### <a name="step-4---device-update-considerations"></a>第 4 步 - 设备更新注意事项

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![显示部署手机的屏幕截图](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![显示 "更新和延期" 选项的屏幕截图。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。
  
![显示 SwUpdate 选项的屏幕截图](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。
  
> [!CAUTION]
> [!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>步骤 5-配置和基础结构电话设置

你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)。
  
有关网络基础结构规划，请参阅[Skype 操作框架](https://www.skypeoperationsframework.com/)。
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>步骤 6-准备用户登录

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
您可以通过阅读[电话系统和通话计划](/microsoftteams/calling-plan-landing-page)了解有关呼叫计划的详细信息
  
- Online 用户可以使用的 **登录选项** 包括：
    
  - 具有**POLYCOM VVX 5xx/6xx**电话的用户将看到：
    
     ![显示 Polycom 电话登录的屏幕截图](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - 具有**YEALINK T48G/T46G**电话的用户将看到：
    
     ![显示 Yealink 电话登录的屏幕截图。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    有关制造商支持的登录选项的详细信息，请参阅[获取 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。
    
     ![显示登录屏幕的屏幕截图](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.
    
  > [!NOTE]
  > [!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。
  
     ![显示登录屏幕的屏幕截图](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - 具有**POLYCOM VVX 5xx/6xx**电话的用户将看到：
    
     ![显示 Polycom 说明的屏幕截图](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - 具有**YEALINK T48G/T46G**电话的用户将看到：
    
     ![显示 Yealink 说明的屏幕截图](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - 具有**POLYCOM VVX 5xx/6xx**电话的用户将看到：
    
     ![显示已过期的 Polycom 代码的屏幕截图](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - 具有**YEALINK T48G/T46G**电话的用户将看到：
    
     ![显示已过期的 Yealink 代码的屏幕截图](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。
    
     ![显示电子邮件验证的屏幕截图](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    输入电话上显示的代码。
    
     ![屏幕截图显示在登录屏幕上输入代码](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    验证该站点是否显示 "[电话制造商名称] **Skype For Business 认证电话**"，然后单击 "**继续**"。
    
     ![显示名称验证的屏幕截图](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    单击用户的凭据或单击" **使用其他帐户**"：
    
     ![显示凭据选项的屏幕截图](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    显示以下页面时，可以安全地关闭浏览器。
    
     ![显示确认消息的屏幕截图](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。 
  
- **支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**交换** <br/> |**电话登录方法** <br/> |**Skype for Business 访问** <br/> |**禁用新式验证和 MFA 的 Exchange 访问** <br/> |**启用新式验证和 MFA 的 Exchange 访问** <br/> |
|Online  <br/> |Online  <br/> |Web 登录  <br/> |是  <br/> |是  <br/> |是  <br/> |
|Online  <br/> |Online  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |Web 登录  <br/> |是  <br/> |否  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |PIN 身份验证  <br/> |是  <br/> |否  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |不适用  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |通过 PC 登录 (BTOE)  <br/> |是  <br/> |是  <br/> |不适用  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    你可以为你的组织禁用电话锁定（默认情况下处于启用状态），更改空闲超时，并选择用户是否可以在电话被锁定或未使用 inband 设置时进行电话呼叫。有关这些设置的详细信息，请参阅[设置 CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 。
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- 使用 Skype for Business 桌面应用（使用电脑）登录到其 IP 电话
    
- 将电话锁定与 PC 锁同步
    
- 单击以呼叫
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **将 BToE 部署到用户**
  
1. 使用 PC 端口将 PC 与电话相连。
    
     ![显示与电脑的连接的屏幕截图](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 从下面的链接下载并安装制造商网站中的最新 BToE 软件。为了获得更好的用户体验，你可以使用 Microsoft 终结点配置管理器等管理员分发解决方案分发和安装 BToE 软件。有关使用配置管理器的帮助，请参阅[Configuration manager 中的程序包和程序](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。
    
   - [Polycom BToE 软件下载网站](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToE 软件下载](http://www.yealink.com/products_list_10.html)
    
   - [AudioCodes BToE 软件下载](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).
    
> [!NOTE]
> [!注释] Mac 和 VDI 平台目前不支持 BToE。 
  
## <a name="related-topics"></a>相关主题
[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[以下是 Office 365 中的电话系统功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
