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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 在 Skype for Business Online 中，你可以控制点到点 (P2P) 作为现有会议策略设置的一部分。 但是，无论用户是否将文件传输到同一组织内部的用户或另一组织的联合用户，这都允许或阻止用户进行文件传输。 按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。
ms.openlocfilehash: 0e5dc2f2407d5d510ec6dc559a8192d91ac3260f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619278"
---
# <a name="block-point-to-point-file-transfers"></a>阻止点到点文件传输

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在 Skype for Business Online 中，你可以控制点到点 (P2P) 作为现有会议策略设置的一部分。 但是，无论用户是否将文件传输到同一组织内部的用户或另一组织的联合用户，这都允许或阻止用户进行文件传输。 按照以下步骤，可以阻止与联合组织或合作伙伴进行 P2P 文件传输。
  
 一种很常见的情况是，希望允许内部用户使用 P2P 文件传输，但阻止与联合合作伙伴进行文件传输。 对于此方案，需要：
  
- 将已启用 P2P 文件传输的会议策略 (_EnableP2PFileTransfer_ 设置为 _True_) 组织中用户。
    
- 创建全局外部用户通信策略设置为阻止外部 P2P 文件传输 (_EnableP2PFileTransfer_ 设置为 _False_) 并将其分配给组织的用户。 
    
可在此处了解有关这些设置 [的更多信息](/previous-versions//mt228132(v=technet.10))。
  
如果组织外部的联合用户尝试向应用了策略的用户发送文件，则会收到"传输失败 **"** 错误。 如果用户尝试发送文件，他们将收到"文件传输 **已关闭"** 错误。
  
若要使此操作正常工作，用户必须使用支持它的 2016 即点即Skype for Business版本。 2016 Skype for Business运行客户端需要以下最低版本：
  
|**类型**|**发布日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (内部版本 7571.2006)   <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (内部版本 7571.2072)   <br/> |
|延期频道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (内部版本 7369.2118)   <br/> |
   
> [!CAUTION]
> 使用较旧版本的应用或 Mac Skype for Business Windows仍能够传输文件。 
  
## <a name="start-windows-powershell"></a>启动Windows PowerShell

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   如果需要有关启动 Windows PowerShell连接，请参阅在单个 Microsoft 365[](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)窗口中Microsoft 365或 Office 365 服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>为组织禁用 P2P 文件传输

默认情况下，对组织的全局策略启用 _EnableP2PFileTransfer。_ 创建时，会为用户分配 _BposSAllModality_ 策略。
  
若要允许在组织内部进行 P2P 传输，但阻止将外部文件传输给另一个组织，只需在全局级别更改它。 为此，请运行：
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>为用户禁用 P2P 文件传输

可以通过创建新策略并授予该用户来向用户应用此策略。 为此，请运行： 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365 Office 365 Skype for Business单点管理来管理 Microsoft 365 或 Skype for Business Online，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
