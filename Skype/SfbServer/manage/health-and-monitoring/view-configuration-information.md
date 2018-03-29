---
title: 在 Skype for Business Server 2015 中查看 CDR 配置信息
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要： 了解如何使用业务服务器 2015年在 Skype 呼叫详细记录 (CDR)。
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看 CDR 配置信息
 
**摘要：**了解如何使用业务服务器 2015年在 Skype 呼叫详细记录 (CDR)。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
商业服务器 2015，单一的安装 Skype 时为您创建全局的 CDR 配置设置的集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 可以通过 Skype 业务服务器的控制面板或[获取 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet CDR 配置设置中使用查看您的组织中。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>若要查看通过 Skype 业务服务器控件面板 CDR 配置信息

1. Skype 业务服务器控件面板中单击**监视和归档**。
    
2. 所有 CDR 配置设置的列表将显示在“**呼叫详细信息记录**”选项卡中；对于每个设置集合，您将看到集合“**名称**”；是否已启用 CDR（“**CDR**”属性）；是否已启用清除（“**CDR 清除**”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“**编辑**”，然后单击“**显示详细信息**”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>查看通过使用 Windows PowerShell cmdlet 的 CDR 配置信息

可以通过使用 Windows PowerShell 和 Get CsCdrConfiguration cmdlet 查看 CDR 的配置设置。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-view-cdr-configuration-information"></a>查看 CDR 配置信息

- 若要查看有关您的 CDR 配置设置的信息，请键入下面的命令在 Skype 的业务服务器管理外壳程序，然后按 enter 键：
    
  ```
  Get-CsCdrConfiguration
  ```

    这将返回与以下类似的信息：
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

有关详细信息，请参阅有关[获取 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

