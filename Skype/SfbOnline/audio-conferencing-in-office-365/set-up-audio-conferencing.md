---
title: 为 Skype for Business 和 Microsoft Teams 设置音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
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
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何为需要加入使用电话的电话会议的企业人员设置电话拨入式或音频会议。 '
ms.openlocfilehash: 02c04afa0a1079a53123ee56094dc6ddc764038c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780528"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>为 Skype for Business 和 Microsoft Teams 设置音频会议

有时，组织中的人员需要使用电话拨入会议。 Skype for Business 和 Microsoft Teams 包括适用于这种情况的音频会议功能！ 人们可以使用电话拨入 Skype for Business 或 Microsoft Teams 会议，而无需使用移动设备或电脑上的 Skype for Business 或 Microsoft Teams 应用。 
  
你只需为计划要安排或主持会议的人员设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。
  
有关音频会议的常见问题，请参阅[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>第 1 步：了解音频会议在你所在国家/地区是否可用
<a name="__top"> </a>


转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。 
 
## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
 
1. 针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。 要想了解需要为音频会议购买哪些许可证以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
        
2. 购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。 请参阅[分配或删除 Office 365 for business 许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)你购买给组织中打算安排或主持会议的人员。
    
3. 我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。 要了解如何设置通信点数，请参阅[为你的组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization)。
    
> [!NOTE]
> 你还可以设置按分钟付费的音频会议。 转到[此处](/microsoftteams/audio-conferencing-pay-per-minute)查找有关如何使用的更多信息。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步：获取会议网桥服务号码
<a name="__top"> </a>

针对音频会议，你不能使用用户电话号码；你需要获取服务号码。 你可以获取会议网桥的收费或免费电话服务号码。 有三种获取收费和免费电话服务号码的方法： 
  
- **使用 Skype for Business 管理中心。** 某些国家/地区内，你可以使用 Skype for Business 管理中心获取会议网桥服务号码，请参阅[获取服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。
    
- **转网现有的服务号码。** 将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。 有关详细信息，请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。  
  
- **使用新号码的请求表单。** 有时（具体取决于你的国家/地区），你无法使用 Skype for Business 管理中心获取新服务号码，或你需要特定的电话号码或区号。 如果是这样，你需要下载表单并将其发送给我们。 有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>第 4 步：将服务号码分配给会议网桥
<a name="__top"> </a>

获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。  

将新的电话号码分配给音频会议网桥：

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**

 转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码**，选择电话号码，然后单击**分配**。

有关详细信息，请参阅 [更改音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>第 5 步：设置会议网桥的默认和备用语言
<a name="__top"> </a>

接下来，你要[设置音频会议自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)，会议自动助理使用这些语言在致电者拨入音频会议电话号码时向其发出问候。 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

从仪表板中，转到**会议** > **会议网桥**，选择会议网桥电话号码，单击**编辑**，然后选择默认语言。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**

转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **Microsoft 网桥设置**，选择会议网桥电话号码，然后单击**设置语言**。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步：设置你的会议网桥设置
<a name="__top"> </a>
    
设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

从仪表板中，转到**会议** > **会议网桥** > **网桥设置**。 这将打开**网桥设置**窗格。 有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**

转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **Microsoft 网桥设置**。 这将打开 **Microsoft 网桥设置** 页。 有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>第 7 步：给主持会议的用户分配电话拨入式电话号码

在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。

你需要为在组织中主持或安排会议的所有人员执行此操作。 待办事项：

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

从仪表板中，单击**用户**，从列表中选择用户，单击**编辑**，单击**音频会议**旁边的**编辑**，然后在**音频会议**窗格中，在**收费电话号码**和**免费**电话号码列表中选择一个号码。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**

转到 **Office 365 管理中心** > **Skype for Business** > **音频会议** > **用户**，然后从列表中选择用户并单击**编辑**。 如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步：设置会议邀请（可选）
<a name="__top"> </a>
 
为用户设置的电话拨入式号码将自动添加到要发送给与会者的会议邀请中。 但是，如果你想要，你也可以添加自己的帮助和法律链接、文本消息和小公司图形。 请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)
  
[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
