---
title: 为 Skype for business 设置音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
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
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何为企业中需要使用电话加入电话会议的人员设置电话拨入式会议或音频会议。 '
ms.openlocfilehash: 499a8a8ef05d23c74b030536d33b7a02cd6d9a1a
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924973"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>为 Skype for business 设置音频会议

您的组织中的人员有时需要使用电话拨入会议。Skype for business 仅为这种情况提供音频会议功能！用户可以使用手机与 Skype for business 会议通话，而不是在移动设备或电脑上使用 Skype for business 应用。 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>第 1 步：了解音频会议在你所在国家/地区是否可用
<a name="__top"> </a>

转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。 
 
## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
 
1. 对于音频会议，需要将设置拨入式会议的每个用户都拥有一个许可证。若要了解需要购买哪些许可证才能购买音频会议和费用，请参阅[Skype for business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

    >[!NOTE] 
    > 音频会议包含在 Office 365 企业版 E5 许可证和加载项中。
        
2. 购买音频会议许可证后，你需要将他们分配给组织中打算安排或主持会议的人员。 请参阅为你购买的[Office 365 for business 中的 "分配或删除许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)"，以安排或领导会议。
    
3. 我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。 若要了解如何设置通讯信用点数，请参阅[为你的组织设置通信信用点数](/microsoftteams/set-up-communications-credits-for-your-organization)。
    
> [!NOTE]
> 您还可以设置[每分钟付费的音频会议](/microsoftteams/audio-conferencing-pay-per-minute)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步：获取会议网桥服务号码
<a name="__top"> </a>

针对音频会议，你不能使用用户电话号码；你需要获取服务号码。 你可以获取会议网桥的收费或免费电话服务号码。 有三种获取收费和免费电话服务号码的方法： 
  
- **使用 Skype For business 管理中心**。 对于某些国家/地区，您可以使用 Skype for Business 管理中心获取您的会议桥的服务号码。 请参阅[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。
    
- **移植您的现有服务号码**。 将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。 您可以参阅将[电话号码转移到团队](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)或[管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，以获取详细信息，帮助您执行此操作。  
  
- **为新号码使用请求表单**。 有时（取决于您所在的国家/地区）您将无法使用 Skype for Business 管理中心获取新的服务号码，或者您需要特定的电话号码或区号。 如果是这样，你需要下载表单并将其发送给我们。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>第 4 步：将服务号码分配给会议网桥
<a name="__top"> </a>

一旦您为您的会议桥购买了收费电话号码和/或免费电话号码，您就需要分配号码，以便他们可以在会议邀请中使用。  

将新的电话号码分配给音频会议网桥：

![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标：

 1. 转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧版门户**。
 2. 选择 "**语音** > **电话号码**"。
 3. 选择电话号码，然后单击 "**分配**"。

有关更多详细信息，请参阅[在音频会议网桥上更改电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>第 5 步：设置会议网桥的默认和备用语言
<a name="__top"> </a>

接下来，你希望为会议自动助理在拨入到音频会议的电话号码时使用的[音频会议设置自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)问候呼叫者。 

![](../images/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标：

1. 从仪表板中，转到**会议** > **桥**。
2. 选择 "会议桥接电话号码"，单击 "**编辑**"，然后选择默认语言。

![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标：

1. 转到管理中心**团队** >  >  **> "管理中心"** 团队 "**旧版门户**"。
2. 选择 "**音频会议** > "**Microsoft 网桥**。 
3. 选择 "会议桥接电话号码"，选择 "**设置语言**"，然后选择默认语言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步：设置你的会议网桥设置
<a name="__top"> </a>
    
设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。 

![](../images/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标：

1. 从仪表板中，转到**会议** > **桥**。
2. 选择 "**桥接设置**"。 这将打开**网桥设置**窗格。 

有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标：

1. 转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧版门户**。
2. 选择 "**音频会议** > "**Microsoft bridge 设置**。 这将打开 **Microsoft 网桥设置** 页。 

有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>第 7 步：给主持会议的用户分配电话拨入式电话号码

在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。

你需要为在组织中主持或安排会议的所有人员执行此操作。 

![](../images/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标：

1. 从仪表板中，单击 "**用户**"，从列表中选择用户，然后选择 "**编辑**"。
2. 选择 "**音频会议**" 旁边的 "**编辑**"，然后在 "**音频会议**" 窗格中，选择 "**收费电话**号码" 和 "免费**电话**号码" 列表中的号码。

![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标：

1. 转到**Microsoft 365 管理中心** > **团队** > "**旧版门户**"。
2. 选择 "**音频会议** > **用户**"，然后从列表中选择用户，然后单击 "**编辑**"。 

如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步：设置会议邀请（可选）
<a name="__top"> </a>
 
为用户设置的拨入号码将自动添加到发送给会议与会者的会议邀请中。 但是，如果需要，您可以添加自己的帮助和法律链接、文本消息和小型公司图形。 请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音频会议电话号码](phone-numbers-for-audio-conferencing.md)
  
[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
