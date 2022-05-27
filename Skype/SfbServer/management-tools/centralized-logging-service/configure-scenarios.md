---
title: 在 2015 Skype for Business Server为集中日志记录服务配置方案
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要：了解如何在 2015 Skype for Business Server创建、修改和删除集中日志记录服务的方案。
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676354"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>在 2015 Skype for Business Server为集中日志记录服务配置方案

**总结：** 了解如何在 2015 Skype for Business Server为集中日志记录服务创建、修改和删除方案。

方案定义范围 (即全局、站点、池或计算机) 以及要在集中日志记录服务中使用的提供程序。 通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。 通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。 如果发现需要修改方案以满足故障排除和日志记录需求，Skype for Business Server 2015 调试工具将提供名为 ClsScenarioEdit.psm1 的Windows PowerShell模块，其中包含名为Edit-CsClsScenario 的函数。 此模块的用途是编辑命名的方案的属性。 本主题提供了此模块的工作方式的示例。 下载 Skype for Business Server 2015 [调试工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)，然后再继续操作。

> [!IMPORTANT]
> 对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。 若要确定当前正在运行的方案，请使用 Windows PowerShell 和 [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario)。 通过使用 Windows PowerShell 和 [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario)，可以动态更改正在运行的方案。 可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。

若要使用 Skype for Business Server Management Shell 运行集中日志记录服务函数，必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色的成员。 若要返回此 cmdlet 分配给的所有 RBAC 角色的列表，包括你自己创建的任何自定义 RBAC 角色，请从 Skype for Business Server Management Shell 或Windows PowerShell提示符运行以下命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。 可以使用 Skype for Business Server Management Shell 发出Windows PowerShell命令。 使用Windows PowerShell时，可以定义用于日志记录会话的新方案。

如 [2015 Skype for Business集中日志记录服务中](centralized-logging-service.md)所述，方案的元素包括：

- **供应商** 如果你熟悉 OCSLogger，则提供程序是你选择告诉 OCSLogger 跟踪引擎应从中收集日志的组件。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果不熟悉 OCSLogger，则提供程序是集中日志记录服务可以从中收集日志的服务器角色特定组件。 有关提供程序配置的详细信息，请参阅 [2015 Skype for Business Server为集中日志记录服务配置提供程序](configure-providers.md)。

- **身份** 参数 -Identity 设置方案的范围和名称。 例如，可以设置“全局”范围，并使用“LyssServiceScenario”标识方案。 合并两者时，定义标识 (，例如“global/LyssServiceScenario”) 。

    （可选）可以使用 -Name 和 -Parent 参数。 定义 Name 参数可对方案进行唯一标识。 如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。

    > [!IMPORTANT]
    > 如果使用名称和父参数，则不能使用 **-Identity** 参数。

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario cmdlet 创建新的方案

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 若要为日志记录会话创建新的方案，请使用 [New-CsClsProvider](/powershell/module/skype/new-csclsprovider) 并定义方案的名称（即，对方案进行唯一标识的方式）。从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。

    对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。

    若要使用定义的选项创建方案，请键入：

   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    例如：

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    使用 -Name 和 -Parent 的备用格式：

   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 每个范围只能有两个方案。 但是，不限于一组数量的提供程序。 在此示例中，假设我们已创建了三个提供程序，并且你希望将这三个提供程序全部分配给要定义的方案。 提供程序变量名称为 LyssProvider、ABServerProvider 和 SIPStackProvider。 若要定义多个提供程序并将其分配给方案，请在 Skype for Business Server Management Shell 或Windows PowerShell命令提示符处键入以下内容：

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > 正如Windows PowerShell中所熟知的，使用`@{<variable>=<value1>, <value2>, <value>...}`哈希值表创建哈希表的约定称为“飞溅”。 有关在Windows PowerShell中展开的详细信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10))。

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 Set-CsClsScenario cmdlet 修改现有方案

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 每个范围只能有两个方案。 您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。 如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。 但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。 若要定义新方案，请执行以下 (，假设添加了名为“S4Provider”的已定义提供程序) ：

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    例如：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 Remove-CsClsScenario cmdlet 删除现有方案

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 若要删除之前已定义的方案，请键入：

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    例如，删除定义的方案 site:Redmond/LyssServiceScenario：

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** cmdlet 可删除指定的方案，但已捕获的跟踪信息仍将保留在日志中以供您搜索。

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>使用 ClsScenarioEdit.psm1 模块加载和卸载Edit-CsClsScenario cmdlet

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 模块作为单独的 Web 下载提供。 该模块是 Skype for Business Server 2015 调试工具的一部分。 默认情况下，调试工具安装在目录 C：\Program Files\Skype for Business Server 2015\Debugging Tools 中。

2. 在Windows PowerShell中，键入：

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功加载模块会将你返回到Windows PowerShell命令提示符。 若要确认模块已加载且Edit-CsClsScenario可用，请键入  `Get-Help Edit-CsClsScenario`。 您应看到 EditCsClsScenario 的语法的基本概要。

3. 若要卸载模块，请键入：

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > 成功卸载模块会将你返回到Windows PowerShell命令提示符。 若要确认模块已卸载，请键入  `Get-Help Edit-CsClsScenario`。 Windows PowerShell将尝试查找 cmdlet 的帮助并失败。

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块从方案中删除现有提供程序

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 在Windows PowerShell中，键入：

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功加载模块会将你返回到Windows PowerShell命令提示符。 若要确认模块已加载且Edit-CsClsScenario可用，请键入  `Get-Help Edit-CsClsScenario`。 您应看到 EditCsClsScenario 的语法的基本概要。

3. 若要从 AlwaysOn 方案中删除提供程序，请键入：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   例如：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   参数值的位置放置仅适用于 -Scenario 和 -Provider。 必须显式定义所有其他参数。

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块将提供程序添加到方案

1. "开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，**单击“Skype for Business 2015**”，然后单击 **“Skype for Business Server管理外壳**”。

2. 若要将提供程序添加到 AlwaysOn 方案，请键入：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    例如：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel 的类型可以是 Fatal、Error、Warning、Info、Verbose、Debug 或 All。 -Flags 可以是提供程序支持的任何标志，例如TF_COMPONENT，TF_DIAG。 -Flags 也可为 ALL 值

   还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
