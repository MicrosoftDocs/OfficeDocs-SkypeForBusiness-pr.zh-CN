---
title: 在 Skype for Business Server 中删除 CDR 配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：了解如何在 Skype for Business Server 中删除 CDR 配置设置。
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818022"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中删除 CDR 配置设置的现有集合
 
**摘要：** 了解如何在 Skype for Business Server 中删除 CDR 配置设置。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
安装 Skype for Business 服务器时，将为你创建单个的 CDR 配置设置的全局集合。 管理员还可以选择可应用于各个站点的自定义设置集合。 根据设计，在站点范围配置的设置优先于在全局范围配置的设置。 如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。
  
请注意，您也可以 "删除" 全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，默认情况下，在 CDR 配置设置的集合中启用清除。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
你可以使用 Skype for Business Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) CMDLET 删除 CDR 配置设置。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>要删除 "Skype for Business 服务器" 控制面板中的 CDR 配置设置

1. 在 "Skype for Business 服务器控制面板" 中，单击 "**监视和存档**"。 
    
2. 在“**呼叫详细信息记录**”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。
    
3. 单击“**编辑**”，然后单击“**删除**”。
    
4. 在 "Skype for Business 服务器控制面板" 对话框中，单击 **"确定"**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 CDR 配置设置

你可以使用 Windows PowerShell 和**CsCdrConfiguration** cmdlet 删除呼叫详细信息录制配置设置。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>删除指定的 CDR 配置设置集合

 此命令删除适用于 Redmond 站点的 CDR 配置设置：
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>删除适用于站点范围的所有 CDR 配置设置

 此命令删除适用于站点范围的所有 CDR 配置设置：
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

有关详细信息，请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中手动清除呼叫详细信息录制和体验数据库的质量](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

