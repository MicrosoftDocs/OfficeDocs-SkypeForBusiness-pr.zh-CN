---
title: 指定 Skype for Business 服务器中 CDR 数据的保留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：了解如何管理 Skype for business 服务器的呼叫详细记录（CDR）数据。
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817671"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>指定 Skype for Business 服务器中 CDR 数据的保留
 
**摘要：** 了解如何管理 Skype for business 服务器的呼叫详细记录（CDR）数据。
  
默认情况下，呼叫详细信息记录 (CDR) 数据会在 60 天后清除。可以使用“呼叫详细信息记录”**** 页上的设置将该数据保留更长或更短的时间。如果禁用 CDR，则在启用 CDR 之前捕获的数据也将清除。
  
> [!NOTE]
> 应该对 CDR 和用户体验质量 (QoE) 进行配置，使二者保留数据的天数相同。监控服务器报告网页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。 
  
使用以下过程来配置 CDR 数据的清除设置。 
  
### <a name="to-specify-retention-of-cdr-data"></a>指定 CDR 数据的保留

1. 从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“呼叫详细信息记录”****。
    
4. 在“呼叫详细信息记录”**** 页上，单击表中的相应站点，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 要打开清除，请选择“启用 CDR 清除”****。
    
6. 在“CDR 最长保留期限(天)****:”中选择呼叫详细信息记录的最长保留天数。
    
7. 在“错误报告数据最长保留期限(天)****:”中选择错误报告的最长保留天数。
    
8. 单击“提交”****。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 指定 CDR 保留

你可以使用 Windows PowerShell 和 CsCdrConfiguration cmdlet 创建 CDR 保留设置。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
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

有关详细信息，请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[Skype for Business 服务器中的呼叫详细记录（CDR）](call-detail-recording-cdr.md)
