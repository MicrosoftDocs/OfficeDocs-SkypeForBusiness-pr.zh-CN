---
title: 设置音频会议 for Skype Business 和 Microsoft 团队
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
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要加入使用电话的电话会议。 '
ms.openlocfilehash: 52872b9995d5973ee872e3105c870ccf7bb07abc
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703481"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>设置音频会议 for Skype Business 和 Microsoft 团队

有时，组织中的用户需要使用电话拨入会议。 商业和 Microsoft 团队的 Skype 包括刚这种情况下的音频会议功能 ！ 人员可以呼叫 Skype 使用电话，而不使用 Skype 为移动设备或 PC 上的业务或 Microsoft 团队应用程序的业务或 Microsoft 小组会议。 
  
您只需为建立音频会议计划安排或潜在顾客会议的人员。 拨入会议与会者不需要任何许可证分配给他们或其他设置。
  
有关音频会议的常见问题进行了问题，请参阅[音频会议的常见问题](audio-conferencing-common-questions.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>步骤 1： 找出音频会议是否在您的国家/地区中可用
<a name="__top"> </a>


转到[音频会议和调用计划国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择您的国家或地区，获取有关音频会议的可用性信息以及有关电话系统，调用计划，收费和免费电话信息数字和 Communications 字幕式。 
 
## <a name="step-2-get-and-assign-licenses"></a>步骤 2： 获取和分配许可证
 
1. 音频会议，需要将电话拨入式会议设置每个用户一个许可证。 若要了解您需要音频会议和它们将成本是多少购买的许可证，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
        
2. 购买的音频会议许可证后，您将结束，以将其分配给您的组织中要安排或潜在顾客会议的人员。 请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)购买了您的组织中转到安排或负责人会议的人员。
    
3. 我们还建议您将 （它们不成本任何） 的通信字幕式许可证分配给同一个人您分配到上一步骤中的许可证。 若要了解如何设置 Communications 字幕式，请参阅[设置为您的组织的通信字幕式](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。
    
> [!NOTE]
> 您还可以设置付薪每分钟音频会议。 转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md)以找出有关如何使用它们的详细信息。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>步骤 3： 获取服务号码的会议桥
<a name="__top"> </a>

对于音频会议，您不能使用电话号码为用户;您将需要获取服务号码。 您可以获取收费电话或免费电话服务号码的会议桥。 有三种方法获取收费和免费电话服务号码： 
  
- **Skype 用于业务管理中心。** 某些国家/地区内，您可以获得使用业务管理中心的 Skype 您会议网桥服务号码，请参阅[Getting 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。
    
- **端口您现有的服务号码。** 端口或将现有号码从您的当前服务提供商或电话运营商转移到 Office 365。 您可以看到[转移到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)或[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的详细信息，可帮助您执行此操作。  
  
- **使用新的号码的请求窗体。** 有时 （根据您的国家/地区） 您将无法获取您的业务管理中心中，使用 Skype 的新服务号码，或需要特定的电话号码或区域代码。 如果是这样，你需要下载表单并将其发送给我们。 有关详细信息，请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>步骤 4： 将服务号码分配的会议桥
<a name="__top"> </a>

获取后收费和/或免费电话号码的会议桥，您需要分配的号码，以便他们可以在会议邀请上使用。  

若要分配给音频的会议桥的新电话号码：

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

 转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **语音** > **电话号码**，选择电话号码，然后单击**分配**。

有关详细信息，请参阅[分配到音频会议桥的新电话号码](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步骤 5： 设置的默认和备用语言的会议桥
<a name="__top"> </a>

接下来，您要[进行音频会议自动助理语言设置](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype for Business Admin Center:**

从仪表板中，转到**会议** > **会议网桥**，选择的会议桥接电话号码，单击**编辑**，然后选择的默认语言。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **音频会议** > **Microsoft 网桥的设置**，选择的会议桥接电话号码，然后单击**设置语言**。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步： 设置您的会议桥
<a name="__top"> </a>
    
设置您的会议桥之后, 验证的默认设置，如条目/退出通知和 PIN 长度想要使用; 的起来如果不，您可以更改它们。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype for Business Admin Center:**

从仪表板中，转到**会议** > **会议网桥** > **网桥的设置**。 这将打开**桥设置**窗格。 有关详细信息，请参阅[更改现有音频会议桥的设置](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **音频会议** > **Microsoft 网桥的设置**。 这将打开**Microsoft 桥设置**页。 有关详细信息，请参阅[更改现有音频会议桥的设置](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>步骤 7： 导致会议的用户分配电话拨入式电话号码

在创建音频会议网桥后，您需要为您的用户设置收费和免费电话号码。

您将需要执行此操作的人员在组织中会导致或安排会议的所有。 若要此操作：

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype for Business Admin Center:**

从仪表板，单击**用户**，从列表中选择用户、 单击**编辑**，单击**音频会议**，旁边的**编辑**，然后在**音频会议**窗格中，选择**收费电话号码**和**的数字免费电话**的列表编号。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**

转到**Office 365 管理中心** > **for Business 的 Skype** > **音频会议** > **用户**，然后从列表中选择用户并单击**编辑**。 如果您需要更多详细信息，请参阅[分配 Microsoft 作为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>步骤 8： 设置会议邀请 （可选）
<a name="__top"> </a>
 
为用户设置的电话拨入式号码将自动添加到发送给会议与会者的会议邀请。 但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形，如果您希望。 请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)
  
[为联机会议和电话会议设置选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
