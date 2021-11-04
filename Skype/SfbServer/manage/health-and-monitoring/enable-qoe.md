---
title: 启用用户体验质量Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：了解如何在 (中) QoE Skype for Business Server。
ms.openlocfilehash: aa1f755dbc19da959f54f6af882bff2049363d6f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767700"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>启用用户体验质量Skype for Business Server

**摘要：了解如何** 在 Skype for Business Server 中 (QoE) 用户体验质量。

用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。有关详细信息，请参阅规划文档中的[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)。

使用以下过程为整个组织或组织中的每个站点启用 QoE。

> [!NOTE]
> 为了启用 QoE，必须首先配置监控和监控后端数据库。有关详细信息，请参阅[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"启用Skype for Business Server QoE

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4. 在“用户体验质量数据”页上，单击表中相应的集合，再单击“操作”，然后单击“启用 QoE”。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 启用 qoE Windows PowerShell Cmdlet

可以使用 Windows PowerShell **Set-CsQoEConfiguration** cmdlet 启用 QoE。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在 Skype for Business Server 中Skype for Business Server。

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

有关详细信息，请参阅 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>另请参阅

[规划监控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[部署监控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)