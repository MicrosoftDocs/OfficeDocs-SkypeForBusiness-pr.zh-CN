---
title: 启用呼叫详细信息记录Skype for Business Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要：了解如何在 CDR 记录中 (呼叫) 记录Skype for Business Server。
ms.openlocfilehash: 1d09e637d75b9617abf669f75e96076333380a075010bd3d641f4c5189be9d89
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301378"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>启用呼叫详细信息记录Skype for Business Server

**摘要：** 了解如何启用呼叫详细信息记录 (CDR) 记录Skype for Business Server。

呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。

使用以下过程为整个组织或组织中的每个站点启用 CDR。

> [!NOTE]
> 为了启用 CDR，必须配置监控和监控数据库。有关详细信息，请参阅[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>使用控制面板Skype for Business Server CDR

1.  从 RTCUniversalServerAdmins 组 (或具有等效用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。

4. 在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“操作”，然后单击“启用 CDR”。

    > [!NOTE]
    > 默认情况下，CDR 处于启用状态。

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用 CDR Windows PowerShell cmdlet

可以使用 **Set-CsCdrConfiguration** cmdlet 和 Windows PowerShell 启用 CDR。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程[PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在Skype for Business Server。

### <a name="to-enable-cdr-for-a-single-location"></a>在单个位置启用 CDR

 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>在单个位置禁用 CDR

 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。 禁用 CDR 不会卸载监控。 它会暂停 CDR 数据的收集和存储。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用单个命令在多个位置启用 CDR

 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

有关详细信息，请参阅 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅

[规划监控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[部署监控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)