---
title: 在 Skype for Business Online 中管理用户的音频会议设置
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '作为 Office 365 管理员，您可以为组织中的单个用户编辑 Skype for Business Online 音频会议设置，例如提供程序、默认收费或免费电话号码、会议 ID 或 PIN。 '
ms.openlocfilehash: 11ab14b3ebba54e1af8125c2d2f6c2acbd0730b7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779052"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>在 Skype for Business Online 中管理用户的音频会议设置

> [!Note]
> 如果您想要管理 Microsoft Teams 中的用户设置，请参阅[管理 Microsoft Teams 中的用户的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)。

作为 Office 365 管理员，您可以为组织中的单个用户编辑音频会议设置，例如提供程序、默认收费或免费电话号码、会议 ID 或 PIN。 如果想要编辑组织的设置，请参阅[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)。

 
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 选择**管理中心** > **Skype for Business**。
    
3. 在 Skype for Business 管理中心，选择**用户**。
    
4. 选择要为其管理设置的用户，然后在“操作”窗格中单击**编辑**![显示编辑图标](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 在左侧导航栏中选择**音频会议**，然后在用户的**属性**页面上，修改以下任何内容：
    
|**设置**|**说明**|
|:-----|:-----|
|**提供程序名称** <br/> |从列表中选择您的提供程序。  <br/><br/> **注意：** 仅当您选择 Microsoft 作为音频会议提供商时，此表中的其余设置才适用。           |
|**默认收费电话号码** （必需） <br/> |对于第三方提供程序，这些电话号码是您从音频会议提供商处收到的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置要出现在 Skype for Business 和 Microsoft Teams 会议请求中的电话号码的格式。  <br/> |
|**默认免费电话号码** <br/> |对于第三方提供程序，这些电话号码是您从音频会议提供商处收到的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置要出现在 Skype for Business 和 Microsoft Teams 会议请求中的电话号码的格式。  <br/> |
|**允许在组织的 Microsoft 网桥中使用免费电话号码加入此用户的会议** <br/> |如果要允许用户使用免费电话号码加入会议，请选择此选项。  <br/> |
|**通过电子邮件发送会议信息** <br/> |仅当您要立即使用其会议 ID 和电话号码向用户发送电子邮件时，才单击此链接。 （此电子邮件不包括 PIN）。请参阅[使用其音频会议信息向用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。  <br/> |
|**会议 ID** <br/> |如果需要重置用户的会议 ID，请选择**重置**。 有关详细信息，请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。  <br/> |
|**PIN** <br/> |如果需要重置用户的 PIN，请选择**重置**。 有关详细信息，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。  <br/> |
|**允许未经身份验证的呼叫者成为第一个加入会议的人** <br/> |选择此选项可允许未经身份验证的呼叫者成为第一个加入会议的人。  <br/> |
|**限制此用户从会议拨出** <br/> |如果要将拨出限制为仅限国内拨号，或者如果要阻止所有从会议拨出，请在此列表中选择一个选项。  <br/> |
  
![显示用户的音频会议属性页](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>相关主题

[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
