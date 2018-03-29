---
title: 在 Skype for Business Server 2015 中删除用户体验质量配置设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要： 了解如何删除业务服务器 2015 Skype 在体验质量 (QoE) 设置。
ms.openlocfilehash: 52008e14ca7a7b2a7a26726a2749f6d4dd083bbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中删除用户体验质量配置设置
 
**摘要：**了解如何删除业务服务器 2015 Skype 在体验质量 (QoE) 设置。
  
用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。
  
商业服务器 2015，单一的安装 Skype 时为您创建全局 QoE 配置设置的集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。 如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。
  
请注意，您也可以"删除"的全局设置。 但将不会实际删除全局设置。 不过，该集合中的所有属性将重置为其默认值。 例如，在 QoE 配置设置的集合中启用了默认清除功能。 假定您修改了全局集合，这样就会禁用清除功能。 如果稍后删除全局设置，则会将这些属性全部重置为其默认值。 在这种情况下，这意味着又重新启用清除功能。
  
通过 Skype 业务服务器控件面板或通过[删除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet，您可以删除 QoE 配置设置。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>若要通过 Skype 业务服务器控件面板中删除 QoE 配置设置

1.  作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。 有关详细信息，请参阅**代理安装程序权限**。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。
    
4. 在“**用户体验质量数据**”上，单击所需的策略，单击“**编辑**”，然后单击“**删除**”。
    
5. 单击“**确定**”。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 删除 QoE 配置设置

您可以通过使用 Windows PowerShell 和**删除 CsQoEConfiguration** cmdlet 删除 QoE 配置设置。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>删除 QoE 配置设置的指定的集合

 此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>删除应用于该站点作用域的所有 QoE 配置设置

 此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>删除禁用 QoE 监控处的所有 QoE 配置设置

 此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

有关详细信息，请参阅[删除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>另请参阅

[对于业务服务器 2015年手动清除呼叫详细记录并在 Skype 的体验质量数据库](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

