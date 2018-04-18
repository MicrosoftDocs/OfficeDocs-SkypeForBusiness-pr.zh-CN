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
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: '了解如何设置拨入或音频会议的人员在您的业务需要加入会议呼叫使用电话。 '
ms.openlocfilehash: f5258ed7f0b056bb9c3381211f5adf3c8ea91715
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>设置音频会议 for Skype Business 和 Microsoft 团队

有时，组织中的用户需要使用电话拨入会议。 Skype 业务和 Microsoft 小组包括音频会议功能，只是这种情况 ！ 人们可以在调用到 Skype 使用电话，而不使用 Skype 业务或 Microsoft 小组在移动设备或 PC 上的应用程序的业务或 Microsoft 小组会议。 
  
您只需设置音频会议的计划安排或会导致会议的人员。 拨入的会议与会者无需分配给它们或其他设置的任何许可证。
  
常见问题及解答有关音频会议，请参阅[音频会议的常见问题的解决方案](audio-conferencing-common-questions.md)。
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>步骤 1： 找出是否音频会议将在您的国家/地区
<a name="__top"> </a>


转到[音频会议和调用计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择您的国家 / 地区，若要获取有关音频会议的可用性信息以及有关电话系统，调用计划，收费和免费的信息数字和通信的贷方。 
 
## <a name="step-2-get-and-assign-licenses"></a>第 2 步： 获取和分配许可证
 
1. 对于音频会议，您需要为每个用户都将设置拨入会议许可证。 您需要购买音频会议和多少成本的许可证，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
        
2. 购买的音频会议许可证后，您将结束将它们指派给您的组织中将安排或会导致会议的人员。 请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)您购买到您的组织中要发送到时间表或领导会议的人。
    
3. 我们还建议您指定通信片尾许可证 （它们不收取任何费用） 许可证上一步中的分配给同一个人。 若要了解如何设置通讯片尾，请参阅[设置为您的组织的通信贷](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。
    
> [!NOTE]
> 您还可以设置付薪每分钟音频会议。 转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md)以了解更多关于如何使用它们。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步： 获得的会议桥的服务数
<a name="__top"> </a>

对于音频会议，您不能使用电话号码用户;您将需要获得服务号码。 可以获取会议桥的收费或免费的服务号码。 有三种方式获取收费和免费电话服务号码： 
  
- **使用 Skype 业务管理中心。** 某些国家/地区，您可以获得您会议桥的业务管理中心使用 Skype 的服务数，请参阅[获得服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。
    
- **您现有的服务编号的端口。** 端口或从您的当前服务提供商或电话运营商的现有数字转移到 Office 365。 您可以看到[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)或[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的详细信息可帮助您做到这一点。  
  
- **使用新的号码请求窗体。** 有时 （具体取决于您的国家/地区） 将能够获得新业务管理中心，使用 Skype 服务数字或您需要特定的电话号码或区号。 如果是这样，你需要下载表单并将其发送给我们。 有关更多信息，请参见[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>步骤 4： 将服务号码分配给会议桥
<a name="__top"> </a>

一旦您获取会议桥收费和/或免费电话号码，您需要分配编号，以便可以在会议邀请中使用它们。  

要为音频会议桥新的电话号码，请转到**Office 365 管理中心** > **中心管理** > **业务的 Skype** > **语音** > **的电话号码**，选择电话编号，然后单击**分配**。

有关详细信息，请参阅[指派到音频会议桥的新电话号码](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步骤 5： 设置默认和备用语言会议桥
<a name="__top"> </a>

接下来，您需要[设置自动助理语言音频会议的](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理用来招呼呼叫者，当他们拨入电话号码的音频会议。 

请转到**Office 365 管理中心** > **中心管理** > **Skype 业务** > **音频会议** > **Microsoft 网桥的设置**，选择会议桥的电话号码，然后再单击**设置语言**。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步： 设置您的会议网桥的设置
<a name="__top"> </a>
    
设置会议桥后, 确认，如入口/出口通知和针长度的默认设置是您想要使用;如果他们不这样做，您可以更改它们。 

您可以转到**Office 365 管理中心** > **中心管理** > **业务的 Skype** > **音频会议** > **Microsoft 网桥的设置**。 这将打开**Microsoft 桥设置**页。 有关详细信息，请参阅[更改音频会议桥的设置](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a>第 7 步： 指定音频会议提供商和拨入电话号码

现在，您需要确保 Microsoft 指定为该提供程序，并且为它们设置的收费和免费电话号码，在同一时间。

将 Microsoft 作为提供程序分配给组织中的人员，领导或计划会议，请转到**Office 365 管理中心** > **业务的 Skype** > **音频会议** > **用户**，然后选择用户从列表，然后单击**编辑**。 如果您需要更多详细信息，请参阅[分配作为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。

在设置提供程序时，您还可以设置收费和免费电话号码将被添加到会议，邀请该用户。 只需从下拉列表中选择电话号码。 有关详细信息，请参阅[设置数字包括在邀请电话](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。 


## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步： 设置会议邀请 （可选）
<a name="__top"> </a>
 
为用户设置拨入号码将自动添加到向与会者发送会议邀请。 但是，您可以添加您自己的帮助和法律链接、 文本消息和小型公司图形如果希望。 请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)
  
[设置选项用于联机会议和电话会议](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
