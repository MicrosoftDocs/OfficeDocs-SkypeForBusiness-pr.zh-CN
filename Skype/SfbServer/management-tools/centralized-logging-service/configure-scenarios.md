---
title: 配置 Skype for Business Server 2015 中的集中日志记录服务的方案
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要： 了解如何创建、 修改和删除在集中式日志记录服务 Skype 在业务服务器 2015年方案。
ms.openlocfilehash: e8b9575ed949e1769e867113be301deede981018
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>配置 Skype for Business Server 2015 中的集中日志记录服务的方案
 
**摘要：**了解如何创建、 修改和删除在集中式日志记录服务 Skype 在业务服务器 2015年方案。
  
方案定义的作用域 （即全局站点、 池或计算机） 和内容提供商在集中式日志记录服务中使用。 通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。 通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。 如果您发现需要进行修改以满足故障诊断并记录需求的方案，为业务服务器 2015年调试工具 Skype 提供了一个名为 ClsScenarioEdit.psm1，其中包含函数的 namedEdit CsClsScenario 的 Windows PowerShell 模块。 此模块的用途是编辑命名的方案的属性。 本主题提供了此模块的工作方式的示例。 在进行下一步之前业务服务器 2015年[的调试工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)下载 Skype。
  
> [!IMPORTANT]
> 对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。 若要确定当前正在运行的情况下，使用 Windows PowerShell 和[Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。 通过使用 Windows PowerShell 和[一组 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)，可以动态更改运行哪些方案。 可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。 
  
若要通过 Skype 业务服务器管理外壳程序运行的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色的成员，包含这两个组之一。 返回列表中的所有 RBAC 角色此 cmdlet 已指配给，包括自己，创建的任何自定义的 RBAC 角色运行下面的命令从 Skype 业务服务器管理外壳或者 Windows PowerShell 提示：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。 可以使用业务服务器管理外壳的 Skype 发布 Windows PowerShell 命令。 当您使用 Windows PowerShell 时，可以定义日志记录会话中使用的新方案。
  
由于介绍[业务 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)，方案的要素包括：
  
- **提供程序**如果您熟悉 OCSLogger，提供程序告诉 OCSLogger 跟踪引擎应收集日志从您选择的组件。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您还不熟悉 OCSLogger，提供程序特定服务器角色的组件中的集中式记录服务可以收集日志。 有关配置的提供程序的详细信息，请参阅[配置业务服务器 2015年的 Skype 在集中式日志记录服务的提供商](configure-providers.md)。
    
- **标识**参数-标识设置范围和名称的方案。 例如，可以设置的"全局"范围，确定与"LyssServiceScenario"的方案。 当组合这两个时，您定义的标识 (例如，"全局/LyssServiceScenario")。
    
    或者，您可以使用-名称和父参数。 定义 Name 参数可对方案进行唯一标识。 如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。 
    
    > [!IMPORTANT]
    > 如果您使用参数的名称和父级，则无法使用**-标识**参数。
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario cmdlet 创建新的方案

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 为日志记录会话创建一个新的方案，使用[New CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) ，并定义 （即，如何那么将进行唯一标识） 的方案的名称。 从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。 然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。
    
    对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。
    
    若要使用定义的选项创建方案，请键入：
    
  ```
  New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
  ```

    例如：
    
  ```
  New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
  ```

    备用格式使用的名和父：
    
  ```
  New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
  ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 每个范围只能有两个方案。 但是，您并不限于一定数量的提供程序。 在此示例中，假定我们已经创建了三个供应商，您想要分配到方案定义的所有三个。 提供程序变量名称是 LyssProvider、 ABServerProvider 和 SIPStackProvider。 要定义并将多个供应商分配给方案，Skype 业务服务器管理外壳程序或 Windows PowerShell 命令提示符处键入以下命令：
    
  ```
  New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
  ```

    > [!NOTE]
    > 已知在 Windows PowerShell，用于创建使用的值的哈希表的约定`@{<variable>=<value1>, <value2>, <value>…}`称为 assplatting。 在 Windows PowerShell 展开有关详细信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)。 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 Set-CsClsScenario cmdlet 修改现有方案

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 每个范围只能有两个方案。 您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。 如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。 但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。 若要定义一个新的方案，请执行以下操作 （即，假设名为"S4Provider"已定义提供程序添加）：
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
  ```

    例如：
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
  ```

    若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
  ```

    例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
  ```

    若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
  ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 Remove-CsClsScenario cmdlet 删除现有方案

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要删除之前已定义的方案，请键入：
    
  ```
  Remove-CsClsScenario -Identity <name of scope and scenario>
  ```

    例如，删除定义的方案 site:Redmond/LyssServiceScenario：
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
  ```

**删除 CsClsScenario** cmdlet 中移除指定的方案中，但仍可在日志中，您可以搜索已捕获的跟踪。
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>使用 ClsScenarioEdit.psm1 模块加载和卸载 Edit-CsClsScenario cmdlet

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 模块是作为单独的 Web 下载提供的。 该模块是业务服务器 2015年调试工具 Skype 的一部分。 默认情况下，调试工具将安装到目录 C:\Program Files\Skype for Business Server 2015\Debugging Tools 中。 
  
2. 从 Windows PowerShell 中，请键入：
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > 成功加载的模块将返回到 Windows PowerShell 命令提示符。 若要确认在模块加载和编辑 CsClsScenario 是可用，请键入`Get-Help Edit-CsClsScenario`。 您应看到 EditCsClsScenario 的语法的基本概要。 
  
3. 若要卸载模块，请键入：
    
  ```
  Remove-Module ClsController
  ```

    > [!TIP]
    > 成功卸载模块返回您 Windows PowerShell 命令提示符。 若要确认该模块被卸载，请键入`Get-Help Edit-CsClsScenario`。 Windows PowerShell 将尝试找到该 cmdlet 的帮助并失败。 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块从方案中删除现有提供程序

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 从 Windows PowerShell 中，请键入：
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > 成功加载的模块将返回到 Windows PowerShell 命令提示符。 若要确认在模块加载和编辑 CsClsScenario 是可用，请键入`Get-Help Edit-CsClsScenario`。 您应看到 EditCsClsScenario 的语法的基本概要。 
  
3. 若要从 AlwaysOn 方案中删除提供程序，请键入：
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
  ```

  例如：
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
  ```

   参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Remove
  ```

  参数值的位置放置仅适用于的方案和提供程序。 必须显式定义所有其他参数。
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块将提供程序添加到方案

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要将提供程序添加到 AlwaysOn 方案，请键入：
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
  ```

    例如：
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
  ```

    -Loglevel 的类型可以是 Fatal、Error、Warning、Info、Verbose、Debug 或 All。 标志可以是任何提供程序支持，如 TF_COMPONENT，TF_DIAG 的标志。 标志还可以为所有的值
    
  还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
  ```


