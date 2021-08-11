---
title: 在 Skype for Business Online 中管理用户的音频Skype for Business设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
- Audio Conferencing
description: '作为 Microsoft 365 或 Office 365 管理员，您可以编辑 Skype for Business Online 音频会议设置（例如提供商、默认收费或免费电话号码、会议 ID 或 PIN）供您的组织中的单个用户使用。 '
ms.openlocfilehash: 648bb27ce8e6745d765b8fc400494188fd43b5e866ecf0cf927f36fd4d7ca676
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335712"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>在 Skype for Business Online 中管理用户的音频Skype for Business设置

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 如果要管理用户设置Microsoft Teams，请参阅在 Microsoft Teams 中管理[用户的音频会议Microsoft Teams。](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)

作为Microsoft 365管理员Office 365，您可以编辑贵组织中单个用户的音频会议设置，例如提供商、默认收费或免费号码、会议 ID 或 PIN。 如果要编辑组织的设置，请参阅 [管理组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)。

 
1. 使用工作或学校帐户登录。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 在管理Skype for Business，选择"用户 **"。**
    
4. 选择要为其管理设置的用户，然后在“操作”窗格中单击 **编辑**![显示编辑图标](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 在左侧导航栏中选择 **音频会议**，然后在用户的 **属性** 页面上，修改以下任何内容：
    
|**设置**|**说明**|
|:-----|:-----|
|**提供程序名称** <br/> |从列表中选择提供商。  <br/><br/> **注意：** 仅当您选择 Microsoft 作为音频会议提供商时，此表中的其余设置才适用。           |
|**默认收费电话号码** （必需） <br/> |对于第三方提供程序，这些电话号码是您从音频会议提供商处收到的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置数字的格式，因为您希望它们显示在会议请求Skype for Business Microsoft Teams中。  <br/> |
|**默认免费电话号码** <br/> |对于第三方提供程序，这些电话号码是您从音频会议提供商处收到的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置数字的格式，因为您希望它们显示在会议请求Skype for Business Microsoft Teams中。  <br/> |
|**允许在组织的 Microsoft 网桥中使用免费电话号码加入此用户的会议** <br/> |如果要允许用户使用免费电话号码加入会议，请选择此选项。  <br/> |
|**通过电子邮件发送会议信息** <br/> |仅当您要立即使用其会议 ID 和电话号码向用户发送电子邮件时，才单击此链接。 （此电子邮件不包括 PIN）。请参阅[使用其音频会议信息向用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。  <br/> |
|**会议 ID** <br/> |如果需要重置用户的会议 ID，请选择 **重置**。 有关详细信息，请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。  <br/> |
|**PIN** <br/> |如果需要重置用户的 PIN，请选择 **重置**。 有关详细信息，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。  <br/> |
|**允许未经身份验证的呼叫者成为第一个加入会议的人** <br/> |选择此选项可允许未经身份验证的呼叫者成为第一个加入会议的人。  <br/> |
|**限制此用户从会议拨出** <br/> |如果要将拨出限制为仅限国内拨号，或者如果要阻止所有从会议拨出，请在此列表中选择一个选项。  <br/> |
  
![显示用户的音频会议属性页](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>相关主题

[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
