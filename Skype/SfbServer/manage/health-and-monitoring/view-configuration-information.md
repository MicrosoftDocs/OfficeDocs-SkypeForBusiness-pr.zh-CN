---
title: 在 Skype for Business Server 中查看 CDR 配置信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要：了解如何在 Skype for Business Server (CDR) 呼叫详细信息记录。
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816632"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>在 Skype for Business Server 中查看 CDR 配置信息
 
**摘要：** 了解如何在 Skype for Business Server (CDR) 呼叫详细信息记录。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
安装 Skype for Business Server 时，会创建一个 CDR 配置设置的全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 可以使用 Skype for Business Server 控制面板或 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 查看组织使用的 CDR 配置设置。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看 CDR 配置信息

1. 在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**
    
2. 所有 CDR 配置设置的列表将显示在“呼叫详细信息记录”选项卡中；对于每个设置集合，您将看到集合“名称”；是否已启用 CDR（“CDR”属性）；是否已启用清除（“CDR 清除”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“编辑”，然后单击“显示详细信息”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看 CDR Windows PowerShell信息

可以使用 Windows PowerShell 和 Get-CsCdrConfiguration cmdlet 查看 CDR 配置设置。 可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。
  
### <a name="to-view-cdr-configuration-information"></a>查看 CDR 配置信息

- 若要查看有关所有 CDR 配置设置的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：
    
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

有关详细信息，请参阅 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

