---
title: 为 for Business 的 Skype 设置音频会议
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要使用电话加入电话会议。 '
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229308"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>为 for Business 的 Skype 设置音频会议

有时您的组织中的人员将需要使用电话呼入会议。 Skype for Business 包含只是这种情况下的音频会议功能 ！ 人员可以呼叫 Skype 业务会议使用电话，而不使用 Skype 在移动设备或 PC 上的业务应用程序。 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>第 1 步：了解音频会议在你所在国家/地区是否可用
<a name="__top"> </a>

转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。 
 
## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
 
1. 针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。 若要了解您需要音频会议和它们将成本是多少购买的许可证，请参阅[业务加载项授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

    >[!NOTE] 
    > 包含在 Office 365 企业 E5 许可证和作为音频会议。
        
2. 购买的音频会议许可证后，您需要将其分配给您的组织中要安排或潜在顾客会议的人员。 请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)购买了您的组织中转到安排或负责人会议的人员。
    
3. 我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。 若要了解如何设置 Communications 字幕式，请参阅[设置为您的组织的通信字幕式](/microsoftteams/set-up-communications-credits-for-your-organization)。
    
> [!NOTE]
> 您还可以设置[付薪每分钟音频会议](/microsoftteams/audio-conferencing-pay-per-minute)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步：获取会议网桥服务号码
<a name="__top"> </a>

针对音频会议，你不能使用用户电话号码；你需要获取服务号码。 你可以获取会议网桥的收费或免费电话服务号码。 有三种获取收费和免费电话服务号码的方法： 
  
- **使用业务管理中心的 Skype**。 某些国家/地区，可获得使用业务管理中心的 Skype 您会议网桥服务号码。 请参阅[Getting 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。
    
- **端口您现有的服务号码**。 将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。 有关详细信息，请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。  
  
- **使用新的号码的请求窗体**。 有时 （根据您的国家/地区） 您将无法获取您的业务管理中心中，使用 Skype 的新服务号码，或需要特定的电话号码或区域代码。 如果是这样，你需要下载表单并将其发送给我们。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>第 4 步：将服务号码分配给会议网桥
<a name="__top"> </a>

获取后收费和/或免费电话号码的会议桥，您需要分配的号码，以便可以在会议邀请中使用。  

将新的电话号码分配给音频会议网桥：

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

 1. 转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。
 2. 选择**语音** > **电话号码**。
 3. 选择电话号码，然后单击**分配**。

有关详细信息，请参阅[Change 音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>第 5 步：设置会议网桥的默认和备用语言
<a name="__top"> </a>

接下来，您要[进行音频会议自动助理语言设置](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 从仪表板中，转到**会议** > **会议桥**。
2. 选择的会议桥接电话号码，单击**编辑**，然后选择的默认语言。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**:

1. 转到**Office 365 管理中心** > **管理中心** > **团队** > **旧门户**。
2. 选择**音频会议** > **Microsoft 桥**。 
3. 选择的会议桥接电话号码，选择**设置语言**，，然后选择的默认语言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步：设置你的会议网桥设置
<a name="__top"> </a>
    
设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 从仪表板中，转到**会议** > **会议桥**。
2. 选择**网桥的设置**。 这将打开**网桥设置**窗格。 

有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

1. 转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。
2. 选择**音频会议** > **Microsoft 网桥的设置**。 这将打开 **Microsoft 网桥设置** 页。 

有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>第 7 步：给主持会议的用户分配电话拨入式电话号码

在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。

你需要为在组织中主持或安排会议的所有人员执行此操作。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 在仪表板中，单击**用户**，从列表中，选择用户以及选择**编辑**。
2. 选择**音频会议**，旁边的**编辑**，然后在**音频会议**窗格中，选择**收费电话号码**和**免费电话**号码列表中的一个数字。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

1. 转到**Microsoft 365 管理中心** > **团队** > **旧门户**。
2. 选择**音频会议** > **用户**，然后从列表中选择用户并单击**编辑**。 

如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步：设置会议邀请（可选）
<a name="__top"> </a>
 
为用户设置的电话拨入式号码将自动添加到发送给会议与会者的会议邀请。 但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形，如果您希望。 请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)
  
[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
