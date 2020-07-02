---
title: 在 Skype for business Online 中管理用户的音频会议设置
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
description: '作为 Microsoft 365 或 Office 365 管理员，您可以编辑您的组织中的单个用户的 Skype for Business Online 音频会议设置，例如提供商、默认收费或免费号码、会议 ID 或 PIN。 '
ms.openlocfilehash: 47ad2b0d6b5684d2a897055ad43e253e55c67109
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943845"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>在 Skype for business Online 中管理用户的音频会议设置

> [!Note]
> 如果要在 Microsoft 团队中管理用户设置，请参阅[在 Microsoft 团队中管理用户的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)。

As a Microsoft 365 or Office 365 admin, you can edit the Audio Conferencing settings—such as the provider, default toll or toll-free number, conference ID, or PIN—for an individual user in your organization. If you want to edit settings for your organization, see [Manage the Audio Conferencing settings for my organization](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. 使用你的工作或学校帐户登录。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 在 Skype for Business 管理中心，选择 "**用户**"。
    
4. 选择要为其管理设置的用户，然后在“操作”窗格中单击**编辑**![显示编辑图标](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png)。
    
5. 在左侧导航栏中选择**音频会议**，然后在用户的**属性**页面上，修改以下任何内容：
    
|**设置**|**说明**|
|:-----|:-----|
|**提供商名称** <br/> |从列表中选择您的提供商。  <br/><br/> **注意：** 仅当您选择 Microsoft 作为音频会议提供商时，此表中的其余设置才适用。           |
|**默认收费电话号码** （必需） <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**默认免费电话号码** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**允许在组织的 Microsoft 网桥中使用免费电话号码加入此用户的会议** <br/> |如果要允许用户使用免费电话号码加入会议，请选择此选项。  <br/> |
|**通过电子邮件发送会议信息** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**会议 ID** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**允许未经身份验证的呼叫者成为第一个加入会议的人** <br/> |选择此选项可允许未经身份验证的呼叫者成为第一个加入会议的人。  <br/> |
|**限制此用户从会议拨出** <br/> |如果要将拨出限制为仅限国内拨号，或者如果要阻止所有从会议拨出，请在此列表中选择一个选项。  <br/> |
  
![显示用户的音频会议属性页](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>相关主题

[管理我的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization.md)

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
