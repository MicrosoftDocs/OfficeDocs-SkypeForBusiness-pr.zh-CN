---
title: 修改 Skype for Business Server 中的用户体验质量设置
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要：了解如何在 Skype for Business Server 中指定 QoE 数据的保留。
ms.openlocfilehash: cba8b2b98aa809c0583ad7323ff846e654ca9ace
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118611"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>修改 Skype for Business Server 中的用户体验质量设置

**摘要：** 了解如何在 Skype for Business Server 中指定 QoE 数据的保留。

默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“用户体验质量数据”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。

> [!NOTE]
> 应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。

以下过程介绍如何配置 QoE 数据的清除设置。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板指定 QoE 数据的保留

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 **Delegate Setup Permissions**。

2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4. 在“用户体验质量数据”页上，单击表中的相应站点，再单击“编辑”，然后单击“显示详细信息”。

5. 要打开清除，请选择“启用 QoE 清除”。

6. 在“QoE 最长保留期限(天)”中选择 QoE 数据的最长保留天数。

7. 单击“提交”。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 指定 QoE Windows PowerShell保留

可以使用 Windows PowerShell **和 Set-CsQoEConfiguration** cmdlet 创建 QoE 保留设置。 可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中是相同的。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>为特定位置指定 QoE 保留

- 此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>为多个位置指定 QoE 保留

- 此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

有关详细信息，请参阅 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅

[部署监控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)