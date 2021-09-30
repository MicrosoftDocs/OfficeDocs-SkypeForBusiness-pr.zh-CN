---
title: 在 Skype for Business Server 中指定 CDR 数据的保留
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：了解如何管理 Skype for Business Server (CDR) 数据的呼叫详细信息记录。
ms.openlocfilehash: 8588447d7e12123c0d10ae15b07a7727d94c0f27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013756"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>在 Skype for Business Server 中指定 CDR 数据的保留
 
**摘要：** 了解如何管理 Skype for Business Server (CDR) 数据的呼叫详细信息记录。
  
默认情况下，呼叫详细信息记录 (CDR) 数据会在 60 天后清除。可以使用“呼叫详细信息记录”页上的设置将该数据保留更长或更短的时间。如果禁用 CDR，则在启用 CDR 之前捕获的数据也将清除。
  
> [!NOTE]
> 应该对 CDR 和用户体验质量 (QoE) 进行配置，使二者保留数据的天数相同。监控服务器报告网页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。 
  
使用以下过程来配置 CDR 数据的清除设置。 
  
### <a name="to-specify-retention-of-cdr-data"></a>指定 CDR 数据的保留

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。
    
4. 在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“编辑”，然后单击“显示详细信息”。
    
5. 要打开清除，请选择“启用 CDR 清除”。
    
6. 在“CDR 最长保留期限(天):”中选择呼叫详细信息记录的最长保留天数。
    
7. 在“错误报告数据最长保留期限(天):”中选择错误报告的最长保留天数。
    
8. 单击“提交”。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 指定 CDR Windows PowerShell保留

您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration cmdlet 来创建 CDR 保留设置。 可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell Skype for Business Server 的详细信息，请参阅 [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在 Skype for Business Server 中是相同的。
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>指定特定位置的 CDR 保留

- 此命令允许清除 Redmond 站点的 CDR 数据，并将该站点配置为将 CDR 数据和错误报告数据保留 20 天。
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>指定多个位置的 CDR 保留

- 此命令会为组织中使用的所有 CDR 配置设置配置 CDR 保留。
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

有关详细信息，请参阅 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server (CDR) 呼叫详细信息记录](call-detail-recording-cdr.md)