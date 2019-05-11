---
title: 修改业务服务器 Skype 中的用户体验质量设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要： 了解如何为业务服务器中 Skype 指定 QoE 数据的保留。
ms.openlocfilehash: 19342bb3f24f9e93919d0f1a292153d553f4c450
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929509"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>修改业务服务器 Skype 中的用户体验质量设置

**摘要：** 了解如何为业务服务器中 Skype 指定 QoE 数据的保留。

默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“**用户体验质量数据**”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。

> [!NOTE]
> 应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。

以下过程介绍如何配置 QoE 数据的清除设置。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 指定 QoE 数据的保留

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。

4. 在“**用户体验质量数据**”页上，单击表中的相应站点，再单击“**编辑**”，然后单击“**显示详细信息**”。

5. 要打开清除，请选择“**启用 QoE 清除**”。

6. 在“**QoE 最长保留期限（天）**”中选择 QoE 数据的最长保留天数。

7. 单击“**提交**”。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 和**Set-csqoeconfiguration** cmdlet 创建 QoE 保留设置。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>为特定位置指定 QoE 保留

- 此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>为多个位置指定 QoE 保留

- 此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

有关详细信息，请参阅[Set-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
