---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 930960117a46639e86ed2d24c286a5270b21acb9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理员：为单个用户配置 Skype for Business 设置

本文介绍了管理员如何为少量用户配置 Skype for Business。 To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.
  
要允许（或阻止）企业中的所有人与外部人员通信，请参阅：
  
- [Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business. The article also explains how to block communication with specific domains.
    
- [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md). 可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。
    
## <a name="configure-general-settings-for-one-user"></a>为一个用户配置常规设置
<a name="__toc325019204"> </a>

You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. 选择" **用户**"。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 选择要编辑的用户。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。
    
|**选项**|**详细信息**|
|:-----|:-----|
|音频和 HD 视频  <br/> |允许此人记录音频会议、音频和视频会议或不允许他们安排任何会议（无）。  <br/> |
|录制对话和会议  <br/> |选择此人可以记录的内容。  <br/> This option is not available with Skype for Business Basic.  <br/> |
|为了符合规范，请禁用非存档功能  <br/> | 如果法律要求你以电子形式存储信息，请选择此选项。 <br/>  Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center. 将关闭以下功能： <br/>  使用即时消息传输文件 <br/>  共享 OneNote 页面 <br/>  PowerPoint 批注 <br/> |
   
To configure these settings in bulk, use PowerShell. See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>阻止外部通信
<a name="__toc325019206"> </a>

为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。
  
1. Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. 选择" **外部通信**"，然后根据需要清除选项：
    
  - **外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。
    
  - **外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。
    
3. 单击" **保存**"。
    
To configure these settings in bulk, use PowerShell. See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Edit audio conferencing settings for one user
<a name="__toc314837483"> </a>

1. Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.
    
|**音频会议设置**|**说明**|
|:-----|:-----|
|**Provider name** <br/> |Choose your provider from the list.  <br/> |
|**长途电话号码**（必需） <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**免费电话号码** <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Conference ID and PIN** (required) <br/> |The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, this won't be required.  <br/> |
   
To configure these settings in bulk, use PowerShell. See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>相关主题 

[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 