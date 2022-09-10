---
title: 设置 Microsoft Teams 的音频会议
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何为业务中需要使用电话加入电话会议的人员设置拨号或音频会议。 '
ms.openlocfilehash: 04c29b6eaf13d12bee1395d913519c971c7a25d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642123"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>设置 Microsoft Teams 的音频会议

有时组织中的人员会需要使用电话呼入会议。 Microsoft Teams 包含了正是针对此种情况的音频会议功能。 人们可以使用电话呼入 Teams 会议，而无需使用移动设备或电脑上的 Teams 应用。
  
你只需为打算安排或主持会议的人设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。
  
有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>第 1 步：了解音频会议在你所在国家/地区是否可用

转到[音频会议和通话套餐国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证

1. 针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。 若想了解需要为电话音频会议购买哪些许可证以及它们的价格，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    >[!NOTE]
    > Office 365 企业版 E5 许可证中包含音频会议，并用作加载项。

2. 购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。 请参阅向 [Microsoft 365 或Office 365商业版中的用户分配许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，这些用户将购买给组织中要安排或领导会议的人员。

3. 我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。 若要了解如何设置通信点数，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。

   > [!NOTE]
   > 你还可以设置[按分钟付费的音频会议](audio-conferencing-pay-per-minute.md)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>第 3 步：获取会议网桥服务号码

针对音频会议，你不能使用用户电话号码；你需要获取服务号码。 你可以获取会议网桥的收费或免费电话服务号码。 有三种获取收费和免费电话服务号码的方法：
  
- **使用 Microsoft Teams 管理中心**。 某些国家/地区内，你可以使用 Microsoft Teams 管理中心获取会议网桥服务号码。 参见[获取服务电话号码](./getting-service-phone-numbers.md)。

- **转网现有服务号码**。 将现有号码从当前服务提供商或电话运营商移植或传输到 Microsoft 365 或Office 365。 有关详细信息，请参阅[将电话号码转移到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，从而帮助你执行此操作。  
  
- **使用新号码的请求表单**。 有时（具体取决于你的国家/地区），你无法使用 Microsoft Teams 管理中心获取新服务号码，或你需要特定的电话号码或区号。 如果是这样，则需下载表单并将其发回给我们。 有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>第 4 步：将服务号码分配给会议网桥

获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。  

按照下列步骤将新的电话号码分配给音频会议网桥。

 **使用 Microsoft Teams 管理中心**：

 1. 从家里转到 **语音** > **电话号码**。
 2. 选择电话号码，然后单击“**分配**”。

有关详细信息，参见[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步骤 5：为会议桥设置默认和备用语言

 接下来，需要[在 Microsoft 团队中为音频会议设置自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)， 会议自动助理在拨入电话号码进行音频会议时欢迎主叫方。

 **使用 Microsoft Teams 管理中心**：

1. 从家里，去 **会议** > **会议桥**。
2. 选择会议网桥电话号码，单击“**编辑**”，然后选择默认语言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>第 6 步：设置你的会议网桥设置

设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。

 **使用 Microsoft Teams 管理中心**：

1. 从家里，去 **会议** > **会议桥**。
2. 选择“**网桥设置**”。 这将打开 **网桥设置** 窗格。

有关详细信息，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>第 7 步：给主持会议的用户分配电话拨入式电话号码

请参阅 [设置 Microsoft Teams 中邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 还可以通过将电话号码添加到 *TeamsAudioconferencingpolicy* 并将策略分配给用户来设置电话号码。 添加到策略的收费和免费电话号码优先于通过音频会议设置窗格为用户单独设置的电话号码。 如果未将电话号码添加到 *Teamsaudioconferencingpolicy*，则通过音频会议设置窗格为用户单独设置的电话号码将显示在 Microsoft Teams 会议请求中。 [用于收费和免费号码的音频会议策略设置](audio-conferencing-toll-free-numbers-policy.md) 包含更多信息。

> [!IMPORTANT]
> 分配的电话号码最多可能需要 24 小时才能显示在会议邀请中。 如果未显示更新的数字，请等待至少 24 小时，然后再联系支持人员。

## <a name="step-8-set-up-meeting-invitations-optional"></a>第 8 步：设置会议邀请（可选）

为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。 但是，如果需要也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。 参见[自定义会议邀请](meeting-settings-in-teams.md#customize-meeting-invitations)。

## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
  
[Microsoft Teams 中用于音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)
  
[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
