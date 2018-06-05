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
description: 摘要： 了解如何使用业务服务器 2015 Skype 中呼叫详细信息记录 (CDR)。
ms.openlocfilehash: cd143db6ebc0c4e284763ccf4beb9c545fa24ff5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569440"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看 CDR 配置信息
 
**摘要：** 了解如何使用业务服务器 2015 Skype 中呼叫详细信息记录 (CDR)。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
为业务服务器 2015，单个，安装 Skype 时为您创建的 CDR 配置设置的全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 可以使用 Skype 业务 Server Control Panel 或[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的 CDR 配置设置中使用查看您的组织中。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 查看 CDR 配置信息

1. Skype 的业务 Server Control Panel 中单击**监控和存档**。
    
2. 所有 CDR 配置设置的列表将显示在“**呼叫详细信息记录**”选项卡中；对于每个设置集合，您将看到集合“**名称**”；是否已启用 CDR（“**CDR**”属性）；是否已启用清除（“**CDR 清除**”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“**编辑**”，然后单击“**显示详细信息**”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看 CDR 配置信息

您可以使用 Windows PowerShell 和 Get-cscdrconfiguration cmdlet 查看 CDR 配置设置。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-view-cdr-configuration-information"></a>查看 CDR 配置信息

- 若要查看有关所有 CDR 配置设置的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:
    
  ```
  Get-CsCdrConfiguration
  ```

    这将返回与以下类似的信息：
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

有关详细信息，请参阅[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

