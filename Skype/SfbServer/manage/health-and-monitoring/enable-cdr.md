---
title: 在 Skype for Business Server 中启用呼叫详细信息记录
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
description: 摘要：了解如何在 Skype for Business Server (CDR) 记录中启用呼叫详细信息记录。
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816882"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>在 Skype for Business Server 中启用呼叫详细信息记录

**摘要：** 了解如何在 Skype for Business Server 中 (CDR 记录) 呼叫详细信息记录。

呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。

使用以下过程为整个组织或组织中的每个站点启用 CDR。

> [!NOTE]
> 为了启用 CDR，必须配置监控和监控数据库。 有关详细信息，请参阅[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板启用 CDR

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。

4. 在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“操作”，然后单击“启用 CDR”。

    > [!NOTE]
    > 默认情况下，CDR 处于启用状态。

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用 CDR

可以使用 Windows PowerShell **和 Set-CsCdrConfiguration** cmdlet 启用 CDR。 可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。

### <a name="to-enable-cdr-for-a-single-location"></a>在单个位置启用 CDR

 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>在单个位置禁用 CDR

 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。 禁用 CDR 不会卸载监控。 它暂停 CDR 数据的收集和存储。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用单个命令在多个位置启用 CDR

 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

有关详细信息，请参阅 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅

[规划监控](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[部署监控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
