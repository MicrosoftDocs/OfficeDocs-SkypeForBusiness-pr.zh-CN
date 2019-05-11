---
title: 创建或修改的 Skype 中业务服务器的 CDR 配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要： 了解有关呼叫详细信息记录 (CDR) 中 Skype 业务服务器。
ms.openlocfilehash: 2599e5fc221c8c19737e2f0ca3add665cceb6686
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926604"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>创建或修改的 Skype 中业务服务器的 CDR 配置设置集合
 
**摘要：** 了解有关呼叫详细信息记录 (CDR) 中 Skype 业务服务器。
  
利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。
  
为业务 Server 单个安装 Skype 时，会为您创建的 CDR 配置设置的全局集合。 管理员还具有创建站点作用域的自定义设置的选项。 使用这些站点作用域设置时，它们将优先于全局设置。 例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 CDR。
  
可以通过使用任一 Skype 业务 Server Control Panel 或[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 创建 CDR 配置设置。 Skype 业务 Server Control Panel 或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 可用于修改现有的设置。 如果使用的业务 Server Control Panel Skype 创建或修改设置，将对您可用下列选项：
  
|**UI 设置**|**PowerShell 参数**|**说明**|
|:-----|:-----|:-----|
|名称  <br/> |Identity  <br/> |所创建的 CDR 配置设置的唯一标识符。这些设置只能在站点作用域内创建。  <br/> |
|启用 CDR 监控  <br/> |EnableCDR  <br/> |指示是否启用 CDR。  <br/> |
|启用 CDR 清除  <br/> |EnablePurging  <br/> |指示是否将定期从 CDR 数据库中删除 CDR 记录。  <br/> |
|CDR 最长保留期限（天）  <br/> |KeepCallDetailForDays  <br/> |指示 CDR 记录在 CDR 数据库中保留的天数。任何早于指定天数的记录都将被自动删除。（请注意，仅当启用清除后，才会执行清除操作。）  <br/> |
|错误报告数据最长保留期限（天）  <br/> |KeepErrorReportForDays  <br/> |指示 CDR 错误报告的保留天数。任何早于指定天数的记录都将被自动删除。CDR 错误报告是客户端应用程序上传的诊断报告。  <br/> |
   
> [!NOTE]
> New-cscdrconfiguration 和 Set-cscdrconfiguration cmdlet 包括用于业务 Server Control Panel Skype 中不可用的其他选项。 请参阅[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)和[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)帮助主题的详细信息。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 创建 CDR 配置设置

1. Skype 的业务 Server Control Panel 中单击**监控和存档**。
    
2. 在**呼叫详细信息记录**选项卡中，单击**新建**。
    
3. 在“**选择站点**”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。
    
4. 在“**新建呼叫详细信息记录 (CDR) 设置**”  对话框中进行所需选择，然后单击“**提交**”。
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 修改现有 CDR 配置设置

1. Skype 的业务 Server Control Panel 中单击**监控和存档**。
    
2. 双击要修改的设置集合，或选择集合后单击“**编辑**”，然后单击“**显示详细信息**”。 请注意，一次只能修改一个集合。 对多个集合进行相同的更改，改用 Skype 的业务 Server Management Shell。
    
3. 在“**编辑呼叫详细信息记录 (CDR) 设置**”对话框中进行所需选择，然后单击“**提交**”。
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建 CDR 配置设置

您可以创建 CDR 配置设置也可以创建使用 Windows PowerShell 和**New-cscdrconfiguration** cmdlet。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>创建新的 CDR 配置设置集合

 以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>创建可禁用呼叫详细信息记录的 CDR 配置设置集合

 由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>在创建新的 CDR 配置设置集合时指定多个属性值

 您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

有关详细信息，请参阅[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

