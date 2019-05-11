---
title: 配置存档选项为业务服务器处理中 Skype 失败
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要： 了解如何阻止 IM 和会议会话 Skype 对于业务服务器故障会阻止存档。
ms.openlocfilehash: 356db70f9e1be630b8ff6daa8b619b13caf817b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885043"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>配置存档选项为业务服务器处理中 Skype 失败

**摘要：** 了解如何阻止 IM 和会议会话 Skype 对于业务服务器故障会阻止存档。
  
如果存档是组织的要求，您可以发生业务服务器故障会阻止存档的 Skype 阻止 IM 和会议会话。 此功能有时被称作关键模式。 例如，如果存储服务出现问题，将为启用通信存档的用户阻止 IM。 在修复故障后，IM 和会议都会自动恢复。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用控制面板配置关键模式

要指定在出现可阻止存档的故障时是否应允许通信会话：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
6. 单击“**提交**”。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用 Windows PowerShell 配置关键模式

您还可以指定是否应出现故障会阻止存档与 BlockOnArchiveFailure 参数一起使用**Set-csarchivingconfiguration** cmdlet 的时允许通信会话。
  
例如，下面的命令禁用 communications 存档失败的情况下：
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

下一条命令可在出现存档故障时启用通信：
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

有关详细信息，请参阅[Set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

