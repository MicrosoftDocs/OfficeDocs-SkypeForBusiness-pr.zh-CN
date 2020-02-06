---
title: 配置存档选项以处理 Skype for Business 服务器中的故障
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：了解如何在可能会阻止存档的 Skype for Business 服务器故障的情况下阻止 IM 和会议会话。
ms.openlocfilehash: c1a6b9930d9f27e9d679710708141c0394c41dc4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818964"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>配置存档选项以处理 Skype for Business 服务器中的故障

**摘要：** 了解如何在可能会阻止存档的 Skype for Business 服务器故障的情况下阻止 IM 和会议会话。
  
如果存档是你的组织的要求，则可以在可能阻止存档的 Skype for Business 服务器故障事件期间阻止 IM 和会议会话。 此功能有时被称作关键模式。 例如，如果存储服务出现问题，将为启用通信存档的用户阻止 IM。 在修复故障后，IM 和会议都会自动恢复。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用控制面板配置关键模式

要指定在出现可阻止存档的故障时是否应允许通信会话：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
6. 单击“**提交**”。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用 Windows PowerShell 配置关键模式

你还可以通过将**CsArchivingConfiguration** Cmdlet 与 BlockOnArchiveFailure 参数一起指定是否允许通信会话，以防出现故障。
  
例如，以下命令在存档失败的情况下禁用通信：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

下一条命令可在出现存档故障时启用通信：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

有关详细信息，请参阅[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) Cmdlet 的帮助主题。
  

