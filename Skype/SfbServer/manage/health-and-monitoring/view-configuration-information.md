---
title: 查看 CDR 配置信息Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要：了解如何在呼叫记录中 (CDR) CDR Skype for Business Server。
ms.openlocfilehash: 3039db1ff1af74f311f4abc16975f8360509a5c4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844175"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>查看 CDR 配置信息Skype for Business Server
 
**摘要：** 了解如何在呼叫记录中 (CDR) CDR Skype for Business Server。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
在安装Skype for Business Server，将创建一个 CDR 配置设置的全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 可以使用控制面板或[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 查看组织Skype for Business Server CDR 配置设置。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>使用控制面板查看 CDR Skype for Business Server信息

1. 在"Skype for Business Server控制面板"中，单击 **"监控和存档"。**
    
2. 所有 CDR 配置设置的列表将显示在“呼叫详细信息记录”选项卡中；对于每个设置集合，您将看到集合“名称”；是否已启用 CDR（“CDR”属性）；是否已启用清除（“CDR 清除”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“编辑”，然后单击“显示详细信息”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看 CDR Windows PowerShell信息

可以使用 Windows PowerShell cmdlet 和 Get-CsCdrConfiguration 查看 CDR 配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在Skype for Business Server。
  
### <a name="to-view-cdr-configuration-information"></a>查看 CDR 配置信息

- 若要查看有关所有 CDR 配置设置的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：
    
  ```PowerShell
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

有关详细信息，请参阅 [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
