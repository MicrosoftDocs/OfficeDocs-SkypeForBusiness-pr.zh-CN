---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
ms.openlocfilehash: 8659434542696ccb37a0353cd491cc0d01f01e30
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>管理员：为单个用户配置 Skype for Business 设置

本文介绍了管理员如何为少量用户配置 Skype for Business。 为批量中的这些步骤，我们提供了您可以使用 Windows PowerShell cmdlet 的链接。
  
要允许（或阻止）企业中的所有人与外部人员通信，请参阅：
  
- [联系外部适用于业务用户的 Skype 允许用户](allow-users-to-contact-external-skype-for-business-users.md)： 您可以让您的组织使用高级业务功能 （共享桌面，寻找谁是在线等） 的 Skype 在特定人们交流信息的受信任的 （联合） 的业务。 文章还介绍了如何阻止与特定域的通讯。
    
- [适用于业务用户让 Skype 将 Skype 联系人添加](let-skype-for-business-users-add-skype-contacts.md)。 可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。
    
## <a name="configure-general-settings-for-one-user"></a>为一个用户配置常规设置
<a name="__toc325019204"> </a>

您必须具有[管理员权限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行这些步骤。
  
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
|录制对话和会议  <br/> |选择此人可以记录的内容。  <br/> 此选项不可用 Skype 的基本业务。  <br/> |
|为了符合规范，请禁用非存档功能  <br/> | 如果法律要求你以电子形式存储信息，请选择此选项。 <br/>  选择此选项将不会捕获时必须[适当地存放](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)在 Exchange 管理员中心在中设置的功能关闭。 将关闭以下功能： <br/>  使用即时消息传输文件 <br/>  共享 OneNote 页面 <br/>  PowerPoint 批注 <br/> |
   
若要批量配置这些设置，请使用 PowerShell。 请参阅[在 Skype 的在线业务的管理策略](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)。
  
## <a name="block-external-communications"></a>阻止外部通信
<a name="__toc325019206"> </a>

为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。
  
1. 选择**用户**，选择您想要禁用，其设置的用户，然后选择**编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. 选择" **外部通信**"，然后根据需要清除选项：
    
  - **外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。
    
  - **外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。
    
3. 单击" **保存**"。
    
若要批量配置这些设置，请使用 PowerShell。 请参阅[管理 Skype 与外部用户和组织在线业务中的通信](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>编辑音频会议一个用户的设置
<a name="__toc314837483"> </a>

1. 选择**用户**，请选择您想要编辑其音频会议设置的用户，然后选择**编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. 选择**音频会议**、 选择音频会议提供商、 键入或更改请求的信息，然后单击**保存**。
    
|**音频会议设置**|**说明**|
|:-----|:-----|
|**提供程序名称** <br/> |从列表中选择您的提供商。  <br/> |
|**长途电话号码**（必需） <br/> |对于第三方 ACP，这些电话号码是您从音频会议提供商处接收的。 如果用户正在使用 Microsoft 作为音频会议提供商，这些消息将在音频会议桥设置的数字。 设置数字的格式，如您希望它们将出现在 Skype 业务和 Microsoft 小组会议请求。  <br/> |
|**免费电话号码** <br/> |对于第三方 ACP，这些电话号码是您从音频会议提供商处接收的。 如果用户正在使用 Microsoft 作为音频会议提供商，这些消息将在音频会议桥设置的数字。 设置数字的格式，如您希望它们将出现在 Skype 业务和 Microsoft 小组会议请求。  <br/> |
|**会议 ID 和 PIN**（必需） <br/> |参与者的 PIN 或会议使用的代码，加入会议的安排由该用户和第三方音频会议提供商提供。 如果用户正在使用 Microsoft 作为音频会议提供商，这不会是必需的。  <br/> |
   
若要批量配置这些设置，请使用 PowerShell。 请参阅[设置数字包括在邀请电话](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>相关主题 

[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 