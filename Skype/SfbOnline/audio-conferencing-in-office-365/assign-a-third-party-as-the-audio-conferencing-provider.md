---
title: "将第三方指定为音频会议提供商"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>将第三方指定为音频会议提供商

音频会议提供商提供*会议桥*。 会议网桥会为已创建的会议提供拨入式电话号码、PIN 和会议 ID。 您只需要将音频会议提供商给人打算安排或导致 Skype 业务或 Microsoft 小组会议。
  
> [!NOTE]
> 对于 Microsoft 团队，用户将无法使用第三方音频会议提供商，他们必须在 Office 365，将音频会议提供商设置为 Microsoft 中使用音频会议。 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>完成分配的第三方音频会议提供商之前操作的步骤

1. 这取决于您的 Office 365 计划，您可能需要购买**音频会议**附加许可的组织中的人来说要安排或导致 Skype 业务或 Microsoft 小组使用音频会议的会议。 若要了解详细信息，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. 如果您购买**音频会议**附加许可，则将它们分配给您的组织中将安排或会导致使用音频会议的会议的人。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
    
    > [!NOTE]
    > 如果将**音频会议**许可分配给某人**之后**将它们指派第三方音频会议提供商，此人将自动设置 Microsoft 改为用作其音频会议提供商 ！ 如果发生这种情况，您需要首先将 Microsoft 作为音频会议提供商删除之前可以将第三方音频会议提供商分配给它们。
  
3. 在[Microsoft 查明其](https://go.microsoft.com/fwlink/?LinkId=797530)查找第三方音频会议提供商。 联系他们并弄清楚如何完成相关设置。
    
    他们会向你提供：
    
  - **拨入号码 （收费）** ，如果有免费电话号码。
    
  - **会议 ID** ：供每个安排会议的人使用。有些 ACP 将它们称为会议密码。
    
    > [!NOTE]
    > 如果您已完成初始设置的第三方 ACP 但现在需要进行更改，请**单击此处以配置第三方音频会议提供商，** **Microsoft 桥**页面底部。 
  
    > [!NOTE]
    > 当启用音频会议，有关人员并将它们指派第三方音频会议提供商时，音频数字和会议 Id （密码） 自动添加到任何**新**Skype 为他们创建的联机业务会议。
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>如何为用户分配第三方音频会议提供商

1. 在 **Skype for Business 管理中心**中选择" **用户**"。从列表中选择用户，并在操作窗格中单击" **编辑**"。
    
2. 在用户的属性页上单击**音频会议**并输入以下信息：
    
  - **提供程序名称**从列表中选择第三方提供程序。
    
  - **默认收费电话号码**这是必需的。
    
  - **默认免费电话号码**这不是必需。
    
  - **会议 ID**这是由您的音频会议提供商提供的。
    
3. 单击" **保存**"。
    
4. 向每个人发送您从音频会议提供商处接收的 PIN。 作为领导者的会议呼叫管理器调用中可能需要 PIN。
    
    > [!NOTE]
    > 当您使用第三方音频会议提供商时，没有为您要查看或设置针脚代表会议组织者的一种方法。 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>如何在同一时间向许多人指派第三方音频会议提供商

1. 在**Skype 的业务管理中心**，选择**音频会议** > **Microsoft 桥**。 在页面的底部，单击**如果您想要配置第三方音频会议提供商，请单击此处**链接。
    
    > [!NOTE]
    > 如果您已完成初始设置的第三方 ACP 但现在需要进行更改，请在**Microsoft 桥**页上，**单击此处以配置第三方音频会议提供商**的底部。 
  
2. 在**第三方音频会议提供商的配置**页上，在**导入和导出用户**，单击**导出向导**，然后按照**导出用户向导**中的步骤。 完成后，将有一个文件，列出您想要设置音频会议的人。
    
3. 将发送到第三方音频会议提供商创建的文件。 他们将添加在文件中，列出的人员的音频会议信息，然后将该文件返回给您。
    
4. 请仔细检查返回的文件是否包含正确的信息。 我们曾听说过并非文件中列出的所有人都包含正确信息的情况。
    
5. 在" **配置第三方音频会议提供商**"页面上的" **导入和导出用户**"下方，单击" **导入向导**"，然后按照 **导入用户向导**中的步骤进行操作
    
6. 向每个人发送您从音频会议提供商处接收的 PIN。 电话会议的组织者或主持人拨入时，可能需要 PIN。
    
    > [!NOTE]
    > 当您使用第三方音频会议提供商时，没有为您要查看或设置针脚代表会议组织者的一种方法。 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>何时使用第三方音频会议提供商

如果您是在一个国家或地区在 Office 365 中的音频会议不可用、 服务质量不好因为它的位置，或现有合同具有第三方音频会议提供商，我们建议使用第三方音频会议提供商。 否则，我们建议您使用 Microsoft 为您的音频会议提供商。
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>通过使用 Windows PowerShell 自动指定第三方音频会议提供商

- 为节省时间或自动执行此操作，可以使用 [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet。
    
    > [!NOTE]
    > 要更改音频提供商从 Microsoft 为第三方音频会议提供商，您必须删除 Microsoft 作为音频会议提供商。 可以通过使用 [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet 执行此操作
  
- 有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。
    
## <a name="what-else-do-i-need-to-know"></a>我还需了解哪些信息？

您的组织中的用户只能使用一个音频会议提供商。 若要更改 Microsoft 个人的音频会议提供商，请参阅[移动用户的音频会议提供商向 Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)或[作为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md)。
  
## <a name="related-topics"></a>相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

