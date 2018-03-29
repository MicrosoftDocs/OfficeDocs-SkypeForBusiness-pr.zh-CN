---
title: 在 Skype for Business Server 2015 中启用呼叫详细记录
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要： 了解如何启用呼叫详细记录 (CDR) 记录在 Skype 业务服务器 2015年。
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中启用呼叫详细记录
 
**摘要：**了解如何启用呼叫详细记录 (CDR) 记录在 Skype 业务服务器 2015年。
  
呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。 
  
使用以下过程为整个组织或组织中的每个站点启用 CDR。
  
> [!NOTE]
> 为了启用 CDR，必须配置监控和监控数据库。 有关详细信息，请参阅[部署监视](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>若要启用与 Skype 的 CDR 业务服务器的控制面板

1.  从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**呼叫详细信息记录**”。 
    
4. 在“**呼叫详细信息记录**”页上，单击表中的相应站点，再单击“**操作**”，然后单击“**启用 CDR**”。
    
    > [!NOTE]
    > 默认情况下，CDR 处于启用状态。 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 启用 CDR

您可以通过使用 Windows PowerShell 和**一组 CsCdrConfiguration** cmdlet 启用 CDR。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-enable-cdr-for-a-single-location"></a>在单个位置启用 CDR

 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>在单个位置禁用 CDR

 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。禁用 CDR 不会卸载监控。而只会暂停 CDR 数据的收集和存储。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用单个命令在多个位置启用 CDR

 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

有关详细信息，请参阅[设置 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[用于监视计划](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[部署监视](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)