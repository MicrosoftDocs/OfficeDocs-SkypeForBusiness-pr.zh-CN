---
title: 删除用户体验质量配置设置Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要：了解如何删除 (QoE) QoE Skype for Business Server。
---

# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>删除用户体验质量配置设置Skype for Business Server
 
**摘要：** 了解如何删除 Skype for Business Server 中的用户体验质量 (QoE) 设置。
  
用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。
  
在安装 Skype for Business Server，将创建 QoE 配置设置的单个全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。 如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。
  
请注意，您还可以"删除"全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，在 QoE 配置设置的集合中启用了默认清除功能。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
可以使用控制面板或 [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet 删除 qoE Skype for Business Server设置。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用控制面板删除 QoE Skype for Business Server设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅 **Delegate Setup Permissions**。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。
    
4. 在“用户体验质量数据”上，单击所需的策略，单击“编辑”，然后单击“删除”。
    
5. 单击“确定”。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 设置 QoE 配置Windows PowerShell QoE 配置

可以通过使用 Windows PowerShell **和 Remove-CsQoEConfiguration** cmdlet 删除 QoE 配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在 Skype for Business Server 中Skype for Business Server。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>删除 QoE 配置设置的指定的集合

 此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>删除应用于该站点作用域的所有 QoE 配置设置

 此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>删除禁用 QoE 监控处的所有 QoE 配置设置

 此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

有关详细信息，请参阅 [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>另请参阅

[手动清除呼叫详细信息记录和用户体验质量数据库中的Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)