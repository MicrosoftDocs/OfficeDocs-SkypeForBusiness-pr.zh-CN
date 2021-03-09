---
title: 创建自定义外部访问策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype for Business Online 允许你创建其他外部访问策略。 与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569128"
---
# <a name="create-custom-external-access-policies"></a>创建自定义外部访问策略

Skype for Business Online 允许你创建其他外部访问策略。 与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。 包括：
  
- _Tag：NoFederationAndPIC_ (没有联合用户或 Skype 使用者) 
    
- 仅联合访问 (_Tag：FederationOnly )_
    
- _FederationAndPICDefault (联合访问和_ 使用者) 
    
自定义外部策略允许你创建上述设置未涵盖的其他策略。 创建策略时，需要设置所有必需的参数，以后无法更改它们。 创建新的自定义策略允许你控制 Skype 使用者访问等功能，或者用于禁用公有云音频/视频的策略，这是预定义设置未涵盖的内容。 自定义外部访问策略遵循的语法与客户端、移动性和会议策略相同。 可在此处了解有关这些设置 [的更多信息](https://technet.microsoft.com/library/mt228132.aspx)。
  
若要使此操作正常工作，用户必须使用受支持的 2016 即点即用 Skype for Business 应用支持它。 需要以下最低版本的 Skype for Business 2016 点击运行客户端：
  
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
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>为用户创建自定义外部访问策略

为此，请运行：
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 
