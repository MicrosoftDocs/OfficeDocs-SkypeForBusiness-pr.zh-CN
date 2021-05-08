---
title: 下载并安装 Skype for Business Online 连接器模块
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
- PowerShell
description: 下载、安装并使用 Skype for Business Online 连接器创建连接到 Windows PowerShell Online 的远程Skype for Business会话。
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238863"
---
# <a name="download-and-install-the-teams-powershell-module"></a>下载并安装 Teams PowerShell 模块

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)最新版本与 Skype for Business Online 连接器集成，为 Teams 和 Skype for Business Online PowerShell 管理提供单个模块。


1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相关主题
[使用 Skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
