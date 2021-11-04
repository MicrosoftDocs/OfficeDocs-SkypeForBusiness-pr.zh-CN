---
title: 配置存档选项以处理Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：了解如何在出现可能阻止存档的Skype for Business Server阻止 IM 和会议会话。
ms.openlocfilehash: 24bfa5190f4aa86a51d7737c952e6536a7d89b34
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767920"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>配置存档选项以处理Skype for Business Server

**摘要：** 了解如何在出现可能阻止存档的故障时Skype for Business Server IM 和会议会话。
  
如果存档是组织的要求，可以在发生阻止存档的故障时Skype for Business Server IM 和会议会话。 这有时称为关键模式。 例如，如果存储服务出现问题，将阻止其通信已启用存档的用户使用 IM。 IM 和会议都能在修复故障后自动恢复。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用控制面板配置关键模式

若要指定在阻止存档的故障时是否允许通信会话：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 单击存档配置列表中的相应全局、站点或池配置的名称，再单击"编辑"，然后单击"显示 **详细信息"。**
    
5. 要设置存档在失败时的行为方式，请选中或清除“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。
    
6. 单击“提交”。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用配置关键模式Windows PowerShell

您还可以使用 **Set-CsArchivingConfiguration** cmdlet 和 BlockOnArchiveFailure 参数指定在阻止存档的故障时是否允许通信会话。
  
例如，以下命令在存档失败时禁用通信：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

下一个命令在存档失败时启用通信：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

有关详细信息，请参阅 [Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。
