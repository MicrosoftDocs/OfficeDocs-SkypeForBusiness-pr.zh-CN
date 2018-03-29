---
title: 在 Skype for Business Server 2015 中配置存档选项以处理故障
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要： 了解如何阻止 IM 和会议会话在 Skype 的情况下会阻止归档的业务服务器 2015年失败。
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置存档选项以处理故障

**摘要：**了解如何阻止 IM 和会议会话在 Skype 的情况下会阻止归档的业务服务器 2015年失败。
  
如果存档是为您的组织的要求，可以在 Skype 业务服务器故障，将导致无法存档的阻止 IM 和会议会话。 此功能有时被称作关键模式。 例如，如果存储服务出现问题，将为启用通信存档的用户阻止 IM。 在修复故障后，IM 和会议都会自动恢复。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用控制面板配置关键模式

要指定在出现可阻止存档的故障时是否应允许通信会话：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
6. 单击“**提交**”。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用 Windows PowerShell 配置关键模式

您还可以指定是否应该存档**集 CsArchivingConfiguration** cmdlet 使用 BlockOnArchiveFailure 参数也会导致出现故障时允许通信会话。
  
例如，以下命令禁用在存档失败情况下的通信：
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

下一条命令可在出现存档故障时启用通信：
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

有关详细信息，请参阅[设置 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

