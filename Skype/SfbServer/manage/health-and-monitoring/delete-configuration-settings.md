---
title: 在 Skype for Business Server 2015 中删除现有 CDR 配置设置的集合
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要： 了解如何删除业务服务器 2015年中 Skype CDR 的配置设置。
ms.openlocfilehash: d7379817b808ac800694c01014469fe0d159d68f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中删除现有 CDR 配置设置的集合
 
**摘要：**了解如何删除业务服务器 2015年中 Skype CDR 的配置设置。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
商业服务器 2015，单一的安装 Skype 时为您创建全局的 CDR 配置设置的集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 根据设计，在站点范围配置的设置优先于在全局范围配置的设置。 如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。
  
请注意，您也可以"删除"的全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，默认情况下清除启用 CDR 配置设置的集合中。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
您可以通过使用 Skype 业务服务器的控制面板或[删除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 删除 CDR 配置设置。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>若要删除与 Skype 业务服务器控件面板的 CDR 配置设置

1. 在 Skype 业务服务器的控制面板，单击**监视和存档**。 
    
2. 在“**呼叫详细信息记录**”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。
    
3. 单击“**编辑**”，然后单击“**删除**”。
    
4. 在 Skype 业务服务器控制面板对话框中，单击**确定**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 删除 CDR 配置设置

您可以删除呼叫详细记录通过使用 Windows PowerShell 和**删除 CsCdrConfiguration** cmdlet 的配置设置。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
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

有关详细信息，请参阅[删除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[对于业务服务器 2015年手动清除呼叫详细记录并在 Skype 的体验质量数据库](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

