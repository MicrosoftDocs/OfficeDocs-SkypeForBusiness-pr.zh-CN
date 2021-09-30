---
title: Create or modify a collection of CDR configuration settings in Skype for Business Server
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：了解呼叫详细信息记录 (CDR) Skype for Business Server。
ms.openlocfilehash: 1f508df7d139d81d3c91dc1cf9355b61fd028dbc
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015146"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Create or modify a collection of CDR configuration settings in Skype for Business Server
 
**摘要：** 了解呼叫详细信息记录 (CDR) 中Skype for Business Server。
  
呼叫详细信息记录 (CDR) 使您可以跟踪对等即时消息会话、Internet 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。 此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
在安装Skype for Business Server将创建一个 CDR 配置设置的全局集合。 管理员还可以选择在站点范围创建自定义设置。 每当使用这些站点范围的设置时，它们优先于全局设置。 例如，如果为 Redmond 站点创建站点作用域设置，则这些设置 (而不是全局设置) 用于管理 Redmond 中的 CDR。
  
您可以使用控制面板或[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet Skype for Business Server CDR 配置设置。 您可以使用控制面板Skype for Business Server [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 修改现有设置。 如果要使用Skype for Business Server控制面板创建或修改设置，可以使用以下选项：
  
|**UI 设置**|**PowerShell 参数**|**说明**|
|:-----|:-----|:-----|
|名称  <br/> |标识  <br/> |要创建的 CDR 配置设置的唯一标识符。 只能在站点范围创建这些设置。  <br/> |
|启用 CDR 监视  <br/> |EnableCDR  <br/> |指示是否启用 CDR。  <br/> |
|启用 CDR 清除  <br/> |EnablePurging  <br/> |指示是否定期从 CDR 数据库中删除 CDR 记录。  <br/> |
|CDR 最长保留期限为 (天)   <br/> |KeepCallDetailForDays  <br/> |指示 CDR 记录在 CDR 数据库中保留的天数。 超过指定天数的任何记录将自动删除。  (请注意，只有在启用了清除后，才进行清除)   <br/> |
|将错误报告数据最长保留 (天)   <br/> |KeepErrorReportForDays  <br/> |指示 CDR 错误报告保留的天数。 超过指定天数的任何报告将自动删除。 CDR 错误报告是由客户端应用程序上载的诊断报告。  <br/> |
   
> [!NOTE]
> New-CsCdrConfiguration cmdlet Set-CsCdrConfiguration cmdlet 包括"控制面板"中Skype for Business Server选项。 有关详细信息，请参阅 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) [和 Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 帮助主题。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用控制面板创建 CDR Skype for Business Server设置

1. 在"Skype for Business Server控制面板"中，单击 **"监控和存档"。**
    
2. 在"**呼叫详细信息记录"选项卡上**，单击"**新建"。**
    
3. 在 **"选择站点** "对话框中，选择要创建新配置设置的站点。 如果对话框为空，这意味着所有站点已分配有 CDR 配置设置的集合。 每个网站限制为一个此类集合。 在这种情况下，可以删除设置，然后重新创建设置，也可以只修改现有设置。
    
4. 在"**新建呼叫详细信息记录 (CDR**) 设置"对话框中，进行所需的选择，然后单击"提交 **"。**
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用控制面板修改现有 CDR Skype for Business Server设置

1. 在"Skype for Business Server控制面板"中，单击 **"监控和存档"。**
    
2. 双击要修改的设置集合，或选择该集合，单击"编辑 **"，然后单击**"显示 **详细信息"。** 请注意，一次只能修改一个集合。 若要对多个集合进行相同的更改，请Skype for Business Server命令行管理程序。
    
3. 在"**编辑呼叫详细信息记录 (CDR**) 设置"对话框中，进行所需的选择，然后单击"提交 **"。**
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 创建 CDR Windows PowerShell设置

您还可以使用 **New-CsCdrConfiguration** cmdlet 和 Windows PowerShell创建 CDR 配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在Skype for Business Server。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>创建新的 CDR 配置设置集合

 此命令创建应用于 Redmond 站点的 CDR 配置设置的新集合：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>创建禁用呼叫详细信息记录的 CDR 配置设置集合

 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用类似这样的命令：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>在创建新的 CDR 配置设置集合时指定多个属性值

 可以通过包含多个参数来修改多个属性值。 例如，此命令将新设置配置为将呼叫详细信息记录保留 30 天，将错误报告保留 90 天：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

有关详细信息，请参阅 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
