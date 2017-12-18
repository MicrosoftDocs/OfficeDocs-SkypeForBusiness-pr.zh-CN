---
title: "分配第三方音频会议提供商为"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# 分配第三方音频会议提供商为

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
音频会议提供商提供 *会议网桥*  。会议网桥提供拨入电话号码、 Pin，并创建的会议的会议 Id。只需将音频会议提供商分配给将要安排或主持Skype for Business或 Microsoft 小组会议的人员。
  
> [!NOTE]
> Microsoft 团队，用户无法使用第三方音频会议提供商，请他们必须在 Office 365 中，它将音频会议提供商设置为 Microsoft 中使用音频会议。 
  
## 执行分配第三方音频会议提供商之前的步骤

1. 根据您的 Office 365 计划，您可能需要购买您的组织中的用户将要安排或主持 Skype 使用音频会议的业务或 Microsoft 小组会议的 **音频会议**加载项许可证。若要了解详细信息，请参阅[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. 如果您购买 **音频会议**加载项许可证，则将其分配给您的组织中将要安排或主持会议中使用音频会议的人员。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
    
    > [!NOTE]
    > 如果您的 **音频会议**许可证分配给 **后** 将其分配第三方音频会议提供商时，该用户将自动设置改为使用 Microsoft 作为其音频会议提供商 ！如果发生这种情况，您需要首先将 Microsoft 作为音频会议提供商删除之前，您可以为其分配第三方音频会议提供商。
  
3. 在[Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530)查找第三方音频会议提供商。联系他们并了解如何使用它们设置的内容。
    
    他们会向你提供： 
    
  - **拨入号码 （电话）** 和免费电话号码，如果可用。
    
  - **会议 ID** ：供每个安排会议的人使用。有些 ACP 将它们称为会议密码。
    
    > [!NOTE]
    > 如果您已完成初始设置为第三方 ACP，但现在，您需要进行更改，请 **单击此处以配置的第三方音频会议提供商** **Microsoft 网桥**页面的底部。 
  
    > [!NOTE]
    > 当您启用人员的音频会议，并将其分配第三方音频会议提供商时，音频号码和会议 Id （密码） 自动添加到他们创建的任何 **新** Skype for Business Online会议。
  
## 如何向用户分配第三方音频会议提供商

1. 在 **Skype for Business 管理中心**中选择" **用户**"。从列表中选择用户，并在操作窗格中单击" **编辑**"。 
    
2. 在用户的属性页上，单击 **音频会议**，然后输入以下信息：
    
  - **提供商名称** 从列表中选择第三方提供商。
    
  - **默认收费电话号码**这是必需的。
    
  - **默认免费电话号码**这不是必需。
    
  - **会议 ID**提供了您的音频会议提供商。
    
3. 单击" **保存**"。
    
4. 向每个人发送您的音频会议提供商从收到的 PIN。可能需要 PIN 来拨入会议呼叫管理器或前导符。
    
    > [!NOTE]
    > 当您使用第三方音频会议提供商时，没有为您要查看或代表会议组织者设置 Pin 的方式。 
  
## 如何一次向许多人分配第三方音频会议提供商

1. 在 **Skype for Business 管理中心**中，选择 **音频会议**> **Microsoft 网桥**。在页面的底部，单击中， **如果您想要配置的第三方音频会议提供商，请单击此处**的链接。
    
    > [!NOTE]
    > 如果您已完成初始设置为第三方 ACP，但现在，您需要进行更改，请 **单击此处以配置的第三方音频会议提供商** **Microsoft 网桥**页面的底部。 
  
2. **配置第三方音频会议提供商**在页面上，在 **导入和导出的用户**，下单击 **导出向导**，然后按照中 **导出用户向导**的步骤。完成后，您将具有一个文件来列出要设置音频会议的人员。
    
3. 发送到您的第三方音频会议提供商创建的文件。他们将添加在文件中，列出的用户的音频会议信息，然后返回到您的文件。
    
4. 请仔细检查返回的文件是否包含正确的信息。 我们曾听说过并非文件中列出的所有人都包含正确信息的情况。 
    
5. 在 **配置第三方音频会议提供程序页上**，在 **导入和导出的用户**，下单击 **导入向导**，，然后按照 **导入用户向导**中的步骤
    
6. 向每个人发送您的音频会议提供商从收到的 PIN。拨入作为前导符的电话会议组织者，可能需要 PIN。
    
    > [!NOTE]
    > 当您使用第三方音频会议提供商时，没有为您要查看或代表会议组织者设置 Pin 的方式。 
  
## 何时使用第三方音频会议提供商

如果您所在国家或地区位置不可用的 Office 365 中的音频会议、 服务质量好由于它的位置，或不现有合同有第三方音频会议提供商，我们建议使用第三方音频会议提供商。否则，我们建议使用 Microsoft 作为您的音频会议提供商。
  
## 通过使用 Windows PowerShell 自动指定第三方音频会议提供商

- 为节省时间或自动执行此操作，可以使用 [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet。
    
    > [!NOTE]
    > 若要更改为第三方音频会议提供商从 Microsoft 音频提供商，必须删除 Microsoft 作为音频会议提供商。若要执行此操作，请使用[禁用 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet。
  
- 有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。
    
## 我还需了解哪些信息？

在您的组织中人员只能使用一个音频会议提供商。若要向 Microsoft 更改某个人的音频会议提供商，请参阅[移动到 Microsoft 的用户的音频会议提供商](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)或[将 Microsoft 作为音频会议提供商分配](assign-microsoft-as-the-audio-conferencing-provider.md)。
  
## 相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

