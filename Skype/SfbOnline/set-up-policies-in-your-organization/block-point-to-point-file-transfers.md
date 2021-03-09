---
title: 阻止点到点文件传输
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 在 Skype for Business Online 中，你可以控制点到点 (P2P) 文件传输作为现有会议策略设置的一部分。 但是，无论用户是否将文件传输到同一组织内部的用户或其他组织的联合用户，这都允许或阻止用户进行文件传输。 按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569098"
---
# <a name="block-point-to-point-file-transfers"></a>阻止点到点文件传输

在 Skype for Business Online 中，你可以控制点到点 (P2P) 文件传输作为现有会议策略设置的一部分。 但是，无论用户是否将文件传输到同一组织内部的用户或其他组织的联合用户，这都允许或阻止用户进行文件传输。 按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。
  
 一种非常常见的方案是，希望允许内部用户使用 P2P 文件传输，但阻止与联合合作伙伴进行文件传输。 对于此方案，需要：
  
- 将已启用 P2P 文件传输的会议策略 (_EnableP2PFileTransfer_ 设置为 _True_) 组织中用户。
    
- 创建全局外部用户通信策略设置为阻止外部 P2P 文件传输 (_EnableP2PFileTransfer_ 设置为 _False_) 并将其分配给组织的用户。 
    
可在此处了解有关这些设置 [的更多信息](https://technet.microsoft.com/library/mt228132.aspx)。
  
如果组织外部的联合用户尝试向应用了策略的用户发送文件，则会收到"传输失败 **"** 错误。 如果用户尝试发送文件，他们将收到"文件传输 **已关闭"** 错误。
  
为此，用户必须使用支持它的 2016 即点即用 Skype for Business 应用的支持版本。 需要以下最低版本的 Skype for Business 2016 点击运行客户端：
  
|**类型**|**发布日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (内部版本 7571.2006)   <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (内部版本 7571.2072)   <br/> |
|延期频道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (内部版本 7369.2118)   <br/> |
   
> [!CAUTION]
> 使用旧版 Skype for Business Windows 应用或 Mac 客户端的用户仍可传输文件。 
  
## <a name="start-windows-powershell"></a>启动Windows PowerShell

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell提示符并运行以下命令： 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   如果需要有关启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>为组织禁用 P2P 文件传输

默认情况下 _，EnableP2PFileTransfer_ 在组织的全局策略上启用。 创建时，会为用户分配 _BposSAllModality_ 策略。
  
若要允许将 P2P 传输用于组织内部但阻止将外部文件传输给另一个组织，只需在全局级别更改它。 为此，请运行：
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>为用户禁用 P2P 文件传输

可以通过创建新策略并授予该用户来向该用户应用此策略。 为此，请运行： 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。 通过以下主题了解这些优势：
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 
