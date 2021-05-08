---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 0123f285101b8d7190dd7450ddb876a136de13ce
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237528"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理员：为单个用户配置 Skype for Business 设置

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Microsoft Teams管理中心已Skype for Business旧版门户 (管理) 。 现在，管理Skype for Business的所有设置都位于Teams中心。 必须分配全局管理员或 Skype for Business 管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员角色Skype for Business管理中心Teams功能。 有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。

本文介绍了管理员如何为少量用户配置 Skype for Business。 为了批量执行这些步骤，我们包含了指向Windows PowerShell cmdlet 的链接。
  
要允许（或阻止）企业中的所有人与外部人员通信，请参阅：
  
- [](allow-users-to-contact-external-skype-for-business-users.md)允许用户联系外部 Skype for Business 用户：可以让组织使用高级 Skype for Business 功能 (共享桌面、查找在线人员等 ) 来与特定受信任 (联合) 企业中的人员进行通信。 本文还介绍了如何阻止与特定域的通信。
    
- [让用户Skype for Business添加Skype联系人](let-skype-for-business-users-add-skype-contacts.md)。 可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。
    
## <a name="configure-general-settings-for-one-user"></a>为一个用户配置常规设置
<a name="__toc325019204"> </a>

必须具有管理员 [权限才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 执行这些步骤。

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**
  
1. 使用工作或学校帐户登录。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 选择" **用户**"。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 选择要编辑的用户。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。
    
|**选项**|**详细信息**|
|:-----|:-----|
|音频和 HD 视频  <br/> |允许此人录制音频会议、音频和视频会议，或不允许他们安排任何会议， (会议) 。  <br/> |
|录制对话和会议  <br/> |选择此人可以记录的内容。  <br/> 此选项不适用于基本Skype for Business。  <br/> |
|为了符合规范，请禁用非存档功能  <br/> | 如果法律要求你以电子形式存储信息，请选择此选项。 <br/>  选择此选项会关闭在管理中心设置就地保留时未捕获Exchange的功能。 [](/exchange/security-and-compliance/in-place-and-litigation-holds) 将关闭以下功能： <br/>  使用即时消息传输文件 <br/>  共享 OneNote 页面 <br/>  PowerPoint 批注 <br/> |
   
若要批量配置这些设置，请使用 PowerShell。 请参阅[为计算机设置 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>阻止外部通信
<a name="__toc325019206"> </a>

为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。
  
1. 选择 **"** 用户"，选择要禁用其设置的用户，然后选择" **编辑编辑** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) "。
    
2. 选择" **外部通信**"，然后根据需要清除选项：
    
   - **外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。
    
   - **外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。
    
3. 单击" **保存**"。
    
若要批量配置这些设置，请使用 PowerShell。 请参阅[为计算机设置 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>编辑一个用户的音频会议设置
<a name="__toc314837483"> </a>

1. 选择 **"** 用户"，选择要编辑其音频会议设置的用户，然后选择"编辑 **编辑** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) "。
    
2. 选择 **"音频会议"，** 选择音频会议提供商，键入或更改请求的信息，然后单击"保存 **"。**
    
|**音频会议设置**|**说明**|
|:-----|:-----|
|**提供程序名称** <br/> |从列表中选择提供商。  <br/> |
|**长途电话号码**（必需） <br/> |对于第三方 ACP，这些电话号码是音频会议提供商提供的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置数字的格式，因为您希望它们显示在会议请求Skype for Business Microsoft Teams中。  <br/> |
|**免费电话号码** <br/> |对于第三方 ACP，这些电话号码是音频会议提供商提供的电话号码。 如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。 设置数字的格式，因为您希望它们显示在会议请求Skype for Business Microsoft Teams中。  <br/> |
|**会议 ID 和 PIN** (必需)  <br/> |参与者 PIN 或会议代码，用于加入由此用户安排并且由第三方音频会议提供商提供的会议。 如果用户使用 Microsoft 作为音频会议提供商，则不需要这样做。  <br/> |
   
若要批量配置这些设置，请使用 PowerShell。 请参阅[设置邀请中包含的电话号码](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[设置计算机以Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>相关主题 

[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[Skype for Business 和 Microsoft Teams 加载项许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
