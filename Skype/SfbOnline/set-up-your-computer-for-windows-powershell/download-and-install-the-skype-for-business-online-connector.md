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
description: 下载、安装，然后使用 Skype for Business Online 连接器创建Windows PowerShell Skype for Business Online 的远程桌面会话。
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097198"
---
# <a name="download-and-install-the-teams-powershell-module"></a>下载并安装 Teams PowerShell 模块

> [!NOTE]

> 最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/) 与 Skype for Business Online 连接器集成，为 Teams 和 Skype for Business Online PowerShell 管理提供单个模块。


1. 安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开 Windows PowerShell 命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果需要有关启动 Windows PowerShell，请参阅在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相关主题
[使用 skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)