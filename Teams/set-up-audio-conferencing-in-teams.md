---
title: 设置 Microsoft Teams 的音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要使用电话加入电话会议。 '
ms.openlocfilehash: 30e79282f04c2d1b4dc7ff01673461b7a18254fd
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955027"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>设置 Microsoft Teams 的音频会议

有时您的组织中的人员将需要使用电话呼入会议。 Microsoft 团队包括刚这种情况下的音频会议功能 ！ 人员可以使用电话，而不在移动设备或 PC 上使用团队应用程序的团队会议呼叫。 
  
你只需为打算安排或主持会议的人设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。
  
有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>第 1 步：了解音频会议在你所在国家/地区是否可用
<a name="__top"> </a>

转到[音频会议和通话套餐国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。 
 
## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
 
1. 针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。 若要了解您需要音频会议和它们将成本是多少购买的许可证，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    >[!NOTE] 
    > 包含在 Office 365 企业 E5 许可证和作为音频会议。
        
2. 购买的音频会议许可证后，您需要将其分配给您的组织中要安排或潜在顾客会议的人员。 请参阅[分配对业务的 Office 365 中的用户的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)购买了您的组织中转到安排或负责人会议的人员。
    
3. 我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。 若要了解如何设置 Communications 字幕式，请参阅[设置为您的组织的通信字幕式](set-up-communications-credits-for-your-organization.md)。
    
> [!NOTE]
> 您还可以设置[付薪每分钟音频会议](audio-conferencing-pay-per-minute.md)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步：获取会议网桥服务号码
<a name="__top"> </a>

针对音频会议，你不能使用用户电话号码；你需要获取服务号码。 你可以获取会议网桥的收费或免费电话服务号码。 有三种获取收费和免费电话服务号码的方法： 
  
- **使用 Microsoft 团队管理中心**。 某些国家/地区内，您可以获取您使用的 Microsoft 团队管理中心的会议桥服务号码。 请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。
    
- **端口您现有的服务号码**。 将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。 有关详细信息，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，从而帮助你执行此操作。  
  
- **使用新的号码的请求窗体**。 有时 （根据您的国家/地区） 您将无法获取您使用的 Microsoft 团队管理中心的新服务号码，或需要特定的电话号码或区域代码。 如果是这样，你需要下载表单并将其发送给我们。 有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>第 4 步：将服务号码分配给会议网桥
<a name="__top"> </a>

获取后收费和/或免费电话号码的会议桥，您需要分配的号码，以便可以在会议邀请中使用。  

按照这些 stesps 分配给音频的会议桥的新的电话号码。

![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

 1. 转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。
 2. 选择**语音** > **电话号码**。
 3. 选择电话号码，然后单击**分配**。

有关详细信息，请参阅[Change 音频会议网桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>第 5 步：设置会议网桥的默认和备用语言
<a name="__top"></a>接下来，您需要[设置自动助理语言中的 Microsoft 团队的音频会议](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 从仪表板中，转到**会议** > **会议桥**。
2. 选择的会议桥接电话号码，单击**编辑**，然后选择的默认语言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步：设置你的会议网桥设置
<a name="__top"> </a>
    
设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 从仪表板中，转到**会议** > **会议桥**。
2. 选择**网桥的设置**。 这将打开**网桥设置**窗格。 

有关详细信息，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>第 7 步：给主持会议的用户分配电话拨入式电话号码

在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。

你需要为在组织中主持或安排会议的所有人员执行此操作。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：

1. 在仪表板中，单击**用户**，从列表中，选择用户以及选择**编辑**。
2. 选择**音频会议**，旁边的**编辑**，然后在**音频会议**窗格中，选择**收费电话号码**和**免费电话**号码列表中的一个数字。

如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步：设置会议邀请（可选）
<a name="__top"> </a>
 
为用户设置的电话拨入式号码将自动添加到发送给会议与会者的会议邀请。 但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形，如果您希望。 请参阅[自定义会议邀请](customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
  
[Microsoft Teams 中用于音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)
  
[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
