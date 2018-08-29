---
title: 启用业务 Server Skype 中用户体验质量
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要： 了解如何为业务 Server 启用用户体验质量 (QoE) Skype 中。
ms.openlocfilehash: 38c0c14382e8f00abd49f6671af705400c0cff8c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261089"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>启用业务 Server Skype 中用户体验质量

**摘要：** 了解如何为业务 Server 启用用户体验质量 (QoE) Skype 中。

用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。 有关详细信息，请参阅规划文档中的[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 。

使用以下过程为整个组织或组织中的每个站点启用 QoE。

> [!NOTE]
> 为了启用 QoE，必须首先配置监控和监控后端数据库。 有关详细信息，请参阅[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 启用 QoE

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。

4. 在“**用户体验质量数据**”页上，单击表中相应的集合，再单击“**操作**”，然后单击“**启用 QoE**”。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用 QoE

您可以通过使用 Windows PowerShell 和**Set-csqoeconfiguration** cmdlet 启用 QoE。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。

### <a name="to-enable-qoe-for-a-single-location"></a>对单个位置启用 QoE

 要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>对单个位置禁用 QoE

 要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>使用单个命令在多个位置启用 QoE

 以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

有关详细信息，请参阅[Set-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>另请参阅

[规划监控](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[部署监控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

