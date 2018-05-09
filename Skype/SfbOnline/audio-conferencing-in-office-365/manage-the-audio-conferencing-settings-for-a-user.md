---
title: 管理用户的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 作为 Office 365 管理员，您可以编辑的音频会议设置 — 例如提供程序、 默认收费电话或免费电话号码、 会议 ID 或 PIN-为您的组织中的单个用户。 如果您想要编辑您的组织的设置，请参阅 Manage 音频会议设置我的组织。
ms.openlocfilehash: 141ede21a99ff251786c7dfc63f4c55358b61c72
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-a-user"></a>管理用户的音频会议设置

作为 Office 365 管理员，您可以编辑的音频会议设置 — 例如提供程序、 默认收费电话或免费电话号码、 会议 ID 或 PIN-为您的组织中的单个用户。 如果您想要编辑您的组织的设置，请参阅[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)。

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在下，**音频会议**，修改以下任一项：

|**设置**|**说明**|
|:-----|:-----|
|**音频会议**|若要启用音频会议或关闭用户，请单击**编辑**旁边**音频会议**，然后在**音频会议**窗格中，请打开或关闭切换**音频会议**。|
|**电子邮件中发送会议信息**  |仅当您想要立即将电子邮件发送给他/她会议 ID 和电话号码的用户，请单击此链接。 （此电子邮件不包括 PIN）。请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。  |
|**会议 ID**  |如果您需要重置用户的会议 ID，请单击**重置的会议 ID** 。 有关详细信息，请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。  |
|**PIN** |如果您需要重置用户的 PIN，请单击**重置 PIN** 。 有关详细信息，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。 |
|**默认会议收费电话号码**（必需） |这些消息将音频会议桥设置的号码。 设置的数字格式如您所愿 Skype 中显示的业务和 Microsoft 团队会议请求。 若要更改默认收费电话号码，单击**编辑**下一步参加**音频会议**和**音频会议**窗格中，选择一个号码，在**收费电话号码**下。 |
|**从该用户的邀请可以包括免费电话号码**|若要更改此设置，请单击**编辑**旁边**音频会议**和**音频会议**窗格中，切换**包括免费电话号码在会议请求来自此用户**打开或关闭。 |
|**电话拨出式权限**|要更改此设置，请单击**编辑**旁边**音频会议**和**音频会议**窗格中，选择**从会议拨出权限**下的选项。|

![显示用户的音频会议设置](../images/sfbaudioconf-usersettings.png)
 
![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. 在业务管理中心的 Skype，选择**用户**。
    
4. 选择您要为其管理设置，的用户，然后单击在操作窗格的**编辑**![显示编辑图标](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 在左侧导航窗格中，选择**要进行音频会议**，然后在用户**属性**页中，修改以下任一：
    
|**设置**|**说明**|
|:-----|:-----|
|**提供程序名称** <br/> |从列表中选择您的提供商。  <br/><br/> **注意：**此表中的其余设置应用仅当选择 Microsoft 作为音频会议提供商。           |
|**默认收费电话号码**（必需） <br/> |对于第三方提供程序，都从音频会议提供商那里收到的以下电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，这些消息将音频会议桥设置的号码。 设置的数字格式如您所愿 Skype 中显示的业务和 Microsoft 团队会议请求。  <br/> |
|**默认免费对** <br/> |对于第三方提供程序，都从音频会议提供商那里收到的以下电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，这些消息将音频会议桥设置的号码。 设置的数字格式如您所愿 Skype 中显示的业务和 Microsoft 团队会议请求。  <br/> |
|**允许使用组织的 Microsoft 桥中免费电话号码加入此用户的会议** <br/> |如果您想要允许的用户的免费电话号码加入会议，请选择此选项。  <br/> |
|**发送会议信息通过电子邮件** <br/> |仅当您想要立即将电子邮件发送给他/她会议 ID 和电话号码的用户，请单击此链接。 （此电子邮件不包括 PIN）。请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。  <br/> |
|**会议 ID** <br/> |如果您需要重置用户的会议 ID，请选择**重置**。 有关详细信息，请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。  <br/> |
|**PIN** <br/> |如果您需要重置用户的 PIN，请选择**重置**。 有关详细信息，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。  <br/> |
|**允许未经身份验证的呼叫者要在会议中的第一个人员** <br/> |选择此选项可允许未经身份验证的呼叫者要加入会议的第一个。  <br/> |
|**限制为电话拨出会议此用户** <br/> |如果您想要将拨出限制为仅，国内或如果您想要阻止从会议的所有电话拨出此列表中选择一个选项。  <br/> |
  
![显示用户的音频会议属性页](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>相关主题

[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)

[音频会议常见问题](audio-conferencing-common-questions.md)
