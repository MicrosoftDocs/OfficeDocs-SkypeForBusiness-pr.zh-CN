---
title: "管理员：为单个用户配置 Skype for Business 设置"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# 管理员：为单个用户配置 Skype for Business 设置

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](77b26eac-8228-4161-ba9f-733b187bd836.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/77b26eac-8228-4161-ba9f-733b187bd836) 中查找本文的英文版本以便参考。
  
本文介绍如何管理员配置 Skype 商业版少量用户。若要执行这些步骤批量，我们提供了您可以使用 Windows PowerShell cmdlet 的链接。
  
要允许（或阻止）企业中的所有人与外部人员通信，请参阅：
  
- [允许用户联系外部 Skype for Business 用户](allow-users-to-contact-external-skype-for-business-users.md) ：可以让你的组织使用高级 Skype for Business 功能（共享桌面、查找在线用户）以与特定的受信任（联盟）企业中的人员进行通信。它还介绍了如何阻止与特定的域通信。
    
- [允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md) 。可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。
    
## 为一个用户配置常规设置
<a name="__toc325019204"> </a>

您必须具有[关于 Office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行这些步骤。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 选择" **管理中心**">" **Skype for Business**"。
    
3. 选择" **用户**"。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 选择要编辑的用户。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。
    
|**选项**|**详细信息**|
|:-----|:-----|
|音频和 HD 视频  <br/> |允许此人记录音频会议、音频和视频会议或不允许他们安排任何会议（无）。  <br/> |
|录制对话和会议  <br/> |选择此人可以记录的内容。  <br/> 此选项不可用Skype for Business Basic。  <br/> |
|为了符合规范，请禁用非存档功能  <br/> | 如果法律要求你以电子形式存储信息，请选择此选项。 <br/>  选择此选项将关闭必须在 Exchange admin center 设置了[就地保留](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)时不捕获的功能。关闭以下功能：  <br/>  使用即时消息传输文件 <br/>  共享 OneNote 页面 <br/>  PowerPoint 批注 <br/> |
   
若要批量配置这些设置，请使用 PowerShell。请参阅[Skype for Business Online 中的管理策略](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)。
  
## 阻止外部通信
<a name="__toc325019206"> </a>

为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。
  
1. 选择 **用户**，选择您想要禁用，其设置的用户，然后选择 **编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. 选择" **外部通信**"，然后根据需要清除选项：
    
  - **外部 Skype for Business 用户**： 如果您不希望用户能够与联合域中的Skype for Business用户通信，请清除此框。
    
  - **外部的 Skype 用户**： 如果您不希望用户能够与使用免费Skype应用程序的人员进行通信，请清除此框。
    
3. 单击" **保存**"。
    
若要批量配置这些设置，请使用 PowerShell。请参阅[管理 Skype for Business Online 与外部用户和组织中的通信](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)。
  
## 编辑为一个用户的音频会议设置
<a name="__toc314837483"> </a>

1. 选择 **用户** ，选择您要编辑，其音频会议设置的用户，然后选择 **编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。
    
2. 选择 **音频会议**，选择您的音频会议提供商，键入或更改请求的信息，然后单击 **保存**。
    
|**音频会议设置**|**描述**|
|:-----|:-----|
|**提供商名称** <br/> |从列表中选择您的提供商。  <br/> |
|**收费电话号码**（必需）  <br/> |对于第三方 ACP，这些电话号码是您收到来自音频会议提供商。如果用户使用 Microsoft 作为音频会议提供商，这些将在音频会议网桥设置的数字。 设置数字的格式，根据需要出现在Skype for Business和 Microsoft 小组会议请求。  <br/> |
|**免费电话号码** <br/> |对于第三方 ACP，这些电话号码是您收到来自音频会议提供商。如果用户使用 Microsoft 作为音频会议提供商，这些将在音频会议网桥设置的数字。 设置数字的格式，根据需要出现在Skype for Business和 Microsoft 小组会议请求。  <br/> |
|**会议 ID 和 PIN**（必需）  <br/> |参与者 PIN 或会议代码，用于加入会议的计划通过此用户并从第三方音频会议提供商提供。如果用户使用 Microsoft 作为音频会议提供商，不会被要求。  <br/> |
   
若要批量配置这些设置，请使用 PowerShell。请参阅[为会议组织者包含在邀请中设置音频会议电话号码](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 相关主题
<a name="__toc314837483"> </a>

[设置 Skype for Business Online](set-up-skype-for-business-online.md)[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

