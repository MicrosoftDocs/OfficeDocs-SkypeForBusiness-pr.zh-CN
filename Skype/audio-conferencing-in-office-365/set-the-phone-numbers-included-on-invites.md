---
title: "为会议组织者包含在邀请中设置音频会议电话号码"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# 为会议组织者包含在邀请中设置音频会议电话号码

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](32954439-d365-4125-872f-b37466ecb035.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/32954439-d365-4125-872f-b37466ecb035) 中查找本文的英文版本以便参考。
  
在 Office 365 中的音频会议使您的组织中的用户创建 Skype for Business 和 Microsoft 小组会议，然后允许用户为其使用电话拨入。在 Office 365 中，您可以选择使用 Microsoft 音频会议网桥，或使用第三方音频会议网桥承载的已批准的音频会议提供商 (ACP)。
  
会议网桥为你提供了贵组织的一组电话拨入式电话号码。 它们全部可用于加入会议组织者已创建的会议，但是你可以选择将在其会议邀请中包括的电话号码。
  
> [!NOTE]
> 可以有一个收费和一个免费电话号码，在会议邀请为会议组织者，最大值，但还没有位于每个打开的所有电话拨入电话号码可用于加入会议的完整列表的会议邀请底部的链接。 
  
## 设置会议组织者的默认电话拨入式电话号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 选择" **管理中心**">" **Skype for Business**"。
    
3. 选择" **用户**"。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 选择要编辑的用户： 
    
  - 要选择单个用户，请选择该用户的名称。
    
  - 要选择页面上的所有用户，请选中列表顶部的" **显示名称**"旁边的复选框。
    
  - 要选择多个用户，请按住 Ctrl，然后选择所需用户。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在 **提供商**下拉列表，选择用户的提供商。根据提供商，填写以下框。
    
  - **Microsoft 是提供商** ： 使用 **默认收费电话号码**和 **免费电话号码的默认**列表以选择用户的默认数字。
    
    > [!NOTE]
    > 必须先将至少一个免费电话号码分配给你的会议网桥，才能将它设置为用户的默认免费电话号码。 若要获取免费电话号码，请参阅[获取 Skype for Business 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)。 
  
  - **提供商为第三方** ：使用" **收费电话号码**"和" **免费电话号码**"字段输入用户的电话号码。
    
## 重置音频会议电话号码

1. 在 **Skype for Business 管理中心**中，选择 **音频会议**。
    
2. 在页面顶部，选择 **拨入用户**。
    
3. 选择要重置的用户，然后选择" **清除**"。 
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
默认情况下，当您更改用户的会议设置，向用户发送电子邮件。若要更改此设置，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)。
  
> [!IMPORTANT]
> 当您更改用户的音频会议设置时，必须更新定期和将来 Skype for Business 和 Microsoft 小组会议并发送给与会者。 
  
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。
    
- 使用[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 来更改默认收费或为特定用户的免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge** 。
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要设置默认免费电话号码没有 1 到 +18005551234 的所有用户，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要更改默认的 +18005551234 +18005551239 到其默认免费电话号码为所有用户的免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要设置默认的所有用户都位于 +18005551234 到美国的免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要更改默认的 +18005551234 +18005551239 到其默认免费电话号码和重新安排与新的免费电话号码的所有会议的所有用户的免费电话号码，请运行：
    
  -     > [!NOTE]
    > 上面使用的位置信息需要与 Office 365 管理中心中设置的用户联系信息匹配。 
  
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

