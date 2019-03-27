---
title: 删除现有的 Skype 中业务服务器的 CDR 配置设置集合
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要： 了解如何在 Skype 业务服务器删除 CDR 配置设置。
ms.openlocfilehash: 470aade77fce211ba771c628b913efa4376a4a6f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873075"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>删除现有的 Skype 中业务服务器的 CDR 配置设置集合
 
**摘要：** 了解如何在 Skype 业务服务器删除 CDR 配置设置。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
对于业务服务器，单个，安装 Skype 时为您创建的 CDR 配置设置的全局集合。 管理员还可以选择可应用于各个站点的自定义设置集合。 根据设计，在站点范围配置的设置优先于在全局范围配置的设置。 如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。
  
请注意，您还可以"删除"全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，默认情况下清除启用 CDR 配置设置集合中。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
您可以通过使用 Skype 业务 Server Control Panel 或[Remove-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 删除 CDR 配置设置。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>删除 CDR 配置设置与 Skype 的业务 Server Control Panel

1. 在业务 Server Control Panel 的 Skype，单击**监控和存档**。 
    
2. 在“**呼叫详细信息记录**”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。
    
3. 单击“**编辑**”，然后单击“**删除**”。
    
4. 在业务 Server Control Panel 对话框 Skype，单击**确定**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 CDR 配置设置

您可以删除呼叫详细信息记录配置设置，通过使用 Windows PowerShell 和**Remove-cscdrconfiguration** cmdlet。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>删除指定的 CDR 配置设置集合

 此命令删除适用于 Redmond 站点的 CDR 配置设置：
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>删除适用于站点范围的所有 CDR 配置设置

 此命令删除适用于站点范围的所有 CDR 配置设置：
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>删除禁用呼叫详细信息记录的 CDR 配置设置

 此命令删除已禁用呼叫详细信息记录的所有 CDR 配置设置：
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

有关详细信息，请参阅[Remove-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[为业务 Server 中手动清除呼叫详细信息记录和 Skype 中的用户体验质量数据库](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

