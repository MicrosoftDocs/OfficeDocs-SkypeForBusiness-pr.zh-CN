---
title: 删除现有 CDR 配置设置集合Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：了解如何删除 SKYPE FOR BUSINESS SERVER 中的 CDR 配置设置。
ms.openlocfilehash: 8218d0b51045d3962825555bd5b248cb58262a37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854316"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>删除现有 CDR 配置设置集合Skype for Business Server
 
**摘要：** 了解如何删除 CDR 配置设置Skype for Business Server。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
在安装Skype for Business Server，将创建一个 CDR 配置设置的全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 根据设计，在站点范围配置的设置优先于在全局范围配置的设置。 如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。
  
请注意，您还可以"删除"全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，默认情况下，在 CDR 配置设置集合中启用清除。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
可以使用控制面板或[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet Skype for Business Server CDR 配置设置。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>使用控制面板删除 CDR Skype for Business Server设置

1. 在Skype for Business Server控制面板中，单击"**监控和存档"。** 
    
2. 在“呼叫详细信息记录”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。
    
3. 单击“编辑”，然后单击“删除”。
    
4. 在"Skype for Business Server控制面板"对话框中，单击"确定 **"。**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 删除 CDR Windows PowerShell设置

可以通过使用 Windows PowerShell **和 Remove-CsCdrConfiguration** cmdlet 删除呼叫详细信息记录配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 该过程在 Skype for Business Server 中Skype for Business Server。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>删除指定的 CDR 配置设置集合

 此命令删除适用于 Redmond 站点的 CDR 配置设置：
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>删除应用于站点范围的所有 CDR 配置设置

 此命令删除适用于站点范围的所有 CDR 配置设置：
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

有关详细信息，请参阅 [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[手动清除呼叫详细信息记录和用户体验质量数据库中的Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)