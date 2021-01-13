---
title: 在 Skype for Business Server 中启用用户体验质量
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：了解如何在 Skype for Business Server (QoE) 用户体验质量。
ms.openlocfilehash: 67b752df3791d3ba0493a7e3575f25c58231ad26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816852"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>在 Skype for Business Server 中启用用户体验质量

**摘要：** 了解如何在 Skype for Business Server (QoE) 用户体验质量。

用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。 有关详细信息，请参阅规划文档中的[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)。

使用以下过程为整个组织或组织中的每个站点启用 QoE。

> [!NOTE]
> 为了启用 QoE，必须首先配置监控和监控后端数据库。 有关详细信息，请参阅[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板启用 QoE

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4. 在“用户体验质量数据”页上，单击表中相应的集合，再单击“操作”，然后单击“启用 QoE”。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 启用 QoE Windows PowerShell Cmdlet

可以通过使用 Windows PowerShell **和 Set-CsQoEConfiguration** cmdlet 启用 QoE。 可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。

### <a name="to-enable-qoe-for-a-single-location"></a>对单个位置启用 QoE

 要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>对单个位置禁用 QoE

 要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>使用单个命令在多个位置启用 QoE

 以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

有关详细信息，请参阅 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>另请参阅

[规划监控](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[部署监控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

