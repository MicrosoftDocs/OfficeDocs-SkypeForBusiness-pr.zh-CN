---
title: 在 Skype for Business Server 中创建或修改 CDR 配置设置的集合
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：了解 Skype for Business Server (CDR) 呼叫详细信息记录。
ms.openlocfilehash: 77529204483924664a462913e8d33eaa54e55453
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817012"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中创建或修改 CDR 配置设置的集合
 
**摘要：** 了解 Skype for Business Server (CDR) 呼叫详细信息记录。
  
通过 CDR (记录呼叫详细信息) 可以跟踪对等即时消息会话、Internet 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。 此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
安装 Skype for Business Server 时，会创建一个 CDR 配置设置的全局集合。 管理员还可以选择在站点范围创建自定义设置。 每当使用这些站点范围的设置时，它们优先于全局设置。 例如，如果为 Redmond 站点创建站点作用域设置，则这些设置 (而不是全局设置) 在 Redmond 中管理 CDR。
  
可以使用 Skype for Business Server 控制面板或 [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 创建 CDR 配置设置。 可以使用 Skype for Business Server 控制面板或 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 修改现有设置。 如果你使用 Skype for Business Server 控制面板创建或修改设置，可以使用以下选项：
  
|**UI 设置**|**PowerShell 参数**|**说明**|
|:-----|:-----|:-----|
|名称  <br/> |标识  <br/> |要创建的 CDR 配置设置的唯一标识符。 只能在站点范围创建这些设置。  <br/> |
|启用 CDR 监视  <br/> |EnableCDR  <br/> |指示是否启用 CDR。  <br/> |
|启用 CDR 清除  <br/> |EnablePurging  <br/> |指示是否定期从 CDR 数据库中删除 CDR 记录。  <br/> |
|将 CDR 最长保留 (天数)   <br/> |KeepCallDetailForDays  <br/> |指示 CDR 记录在 CDR 数据库中保留的天数。 超过指定天数的任何记录将自动删除。  (请注意，只有在启用清除后，才进行清除。)   <br/> |
|将错误报告数据最长保留 (天)   <br/> |KeepErrorReportForDays  <br/> |指示 CDR 错误报告保留的天数。 超过指定天数的任何报告将自动删除。 CDR 错误报告是由客户端应用程序上载的诊断报告。  <br/> |
   
> [!NOTE]
> 此New-CsCdrConfiguration和Set-CsCdrConfiguration cmdlet 包括 Skype for Business Server 控制面板中不可用的其他选项。 有关详细信息，请参阅 [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) [和 Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 帮助主题。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板创建 CDR 配置设置

1. 在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**
    
2. 在"**呼叫详细信息记录"选项卡上**，单击"**新建"。**
    
3. 在 **"选择站点"** 对话框中，选择要创建新配置设置的站点。 如果对话框为空，则意味着所有站点已分配有 CDR 配置设置集合。 每个网站限制为一个此类集合。 在这种情况下，可以删除设置，然后重新创建设置，也可以只修改现有设置。
    
4. 在 **"新建呼叫详细信息记录 (CDR) 设置**"对话框中，进行所需的选择，然后单击"**提交"。**
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板修改现有 CDR 配置设置

1. 在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**
    
2. 双击要修改的设置集合，或选择该集合，单击"编辑"，然后单击"**显示详细信息"。** 请注意，一次只能修改一个集合。 若要对多个集合进行相同的更改，请改为使用 Skype for Business Server 命令行管理程序。
    
3. 在 **"编辑呼叫详细信息记录 (CDR**) 设置"对话框中，进行所需的选择，然后单击"**提交"。**
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 创建 CDR Windows PowerShell设置

您还可以使用 Windows PowerShell **和 New-CsCdrConfiguration** cmdlet 创建 CDR 配置设置。 可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>创建新的 CDR 配置设置集合

 此命令将创建应用于 Redmond 站点的 CDR 配置设置的新集合：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>创建禁用呼叫详细信息记录的 CDR 配置设置集合

 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，若要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用类似这样的命令：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>在创建新的 CDR 配置设置集合时指定多个属性值

 可以通过包含多个参数来修改多个属性值。 例如，此命令将新设置配置为将呼叫详细信息记录保留 30 天，将错误报告保留 90 天：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

有关详细信息，请参阅 [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

