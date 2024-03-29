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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype for Business"联机"允许创建其他外部访问策略。 与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。
ms.openlocfilehash: d0ecf5051de17f923983e16f35eb22b66c41571e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619268"
---
# <a name="create-custom-external-access-policies"></a>创建自定义外部访问策略

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business"联机"允许创建其他外部访问策略。 与客户端或会议策略（可以有多个组合）不同，有三个预定义的外部访问策略可以涵盖大多数方案。 包括：
  
- 没有联合或Skype使用者访问 (_Tag：NoFederationAndPIC_ ) 
    
- 仅联合访问 (_Tag：FederationOnly )_
    
- 联合和使用者访问 (_FederationAndPICDefault)_
    
自定义外部策略允许创建上述设置未涵盖的其他策略。 创建策略时，需要设置所有必需的参数，以后无法更改它们。 创建新的自定义策略允许你控制功能，例如Skype访问或禁用公有云音频/视频的策略，这是预定义设置未涵盖的内容。 自定义外部访问策略遵循的语法与客户端、移动性和会议策略相同。 可在此处了解有关这些设置 [的更多信息](/previous-versions//mt228132(v=technet.10))。
  
若要使此操作正常工作，用户必须使用受支持的 2016 即点即用版本Skype for Business支持该应用。 2016 Skype for Business运行客户端需要以下最低版本：
  
|**类型**|**发布日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (内部版本 7571.2006)   <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (内部版本 7571.2072)   <br/> |
|延期频道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (内部版本 7369.2118)   <br/> |
   
> [!CAUTION]
> 使用较旧版本的 Skype for Business Windows 或 Mac 客户端的用户仍可传输文件。 
  
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
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>为用户创建自定义外部访问策略

为此，请运行：
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
