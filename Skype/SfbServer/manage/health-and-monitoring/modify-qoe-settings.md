---
title: 在 Skype for Business Server 2015 中修改用户体验质量设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要： 了解如何指定 QoE 数据保留在 Skype 业务服务器 2015年。
ms.openlocfilehash: 99a85a389b225d57b48b52b3f6f1d5b66e93f122
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中修改用户体验质量设置
 
**摘要：**了解如何指定 QoE 数据保留在 Skype 业务服务器 2015年。
  
默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“**用户体验质量数据**”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。
  
> [!NOTE]
> 应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。 
  
以下过程介绍如何配置 QoE 数据的清除设置。 
  
### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>若要指定保留的 QoE 数据通过 Skype 业务服务器的控制面板

1.  作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。 有关详细信息，请参阅**代理安装程序权限**。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。
    
4. 在“**用户体验质量数据**”页上，单击表中的相应站点，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 要打开清除，请选择“**启用 QoE 清除**”。
    
6. 在“**QoE 最长保留期限（天）**”中选择 QoE 数据的最长保留天数。
    
7. 单击“**提交**”。
    
## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以通过使用 Windows PowerShell 和**一组 CsQoEConfiguration** cmdlet 创建 QoE 保留设置。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-specify-qoe-retention-for-a-specific-location"></a>为特定位置指定 QoE 保留

- 此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。
    
  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>为多个位置指定 QoE 保留

- 此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 
  ```

有关详细信息，请参阅[设置 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

#### 

[部署监视](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

