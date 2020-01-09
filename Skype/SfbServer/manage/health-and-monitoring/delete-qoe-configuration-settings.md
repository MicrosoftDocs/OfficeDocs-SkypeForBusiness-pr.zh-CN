---
title: 在 Skype for Business Server 中删除体验配置设置的质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要：了解如何在 Skype for Business Server 中删除体验质量（QoE）设置。
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992419"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中删除体验配置设置的质量
 
**摘要：** 了解如何删除 Skype for Business Server 中的体验质量（QoE）设置。
  
用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。
  
安装 Skype for Business 服务器时，将为你创建一个 QoE 配置设置的单个全局集合。 管理员还可以选择可应用于各个站点的自定义设置集合。 根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。 如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。
  
请注意，您也可以 "删除" 全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，在 QoE 配置设置的集合中启用了默认清除功能。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
你可以使用 Skype for Business 服务器控制面板或使用[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) Cmdlet 删除 QoE 配置设置。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板删除 QoE 配置设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。
    
4. 在“**用户体验质量数据**”上，单击所需的策略，单击“**编辑**”，然后单击“**删除**”。
    
5. 单击“**确定**”。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 QoE 配置设置

你可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 删除 QoE 配置设置。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
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

有关详细信息，请参阅[Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中手动清除呼叫详细信息录制和体验数据库的质量](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

