---
title: Lync Server 2013：配置集中日志记录服务的方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a39bcd23516970edf1c4694a8eff1ecb682eda1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置集中日志记录服务的方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

方案定义了范围（即全局、站点、池或计算机）以及要在集中日志记录服务中使用的提供程序。 通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。 通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。 如果发现需要修改某个方案以满足故障排除和日志记录需求，Lync Server 2013 调试工具会为您提供一个名为*ClsController*的 Windows PowerShell 模块，其中包含名为*Edit-new-csclsscenario*的函数。 此模块的用途是编辑命名的方案的属性。 本主题提供了此模块的工作方式的示例。 从以下链接下载 Lync Server 2013 调试工具：[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> 对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。 若要确定当前正在运行的方案，请使用 Windows PowerShell 和<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">new-csclsscenario</A>。 通过使用 Windows PowerShell 和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">new-csclsscenario</A>，您可以动态更改正在运行的方案。 可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。



</div>

若要使用 Lync Server 命令行管理程序运行集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含以下任一项的自定义 RBAC 角色：这两个组。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表，包括您自己创建的任何自定义 RBAC 角色，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。 有两种方法可以发出集中式日志记录服务命令。 默认情况\\下，您可以使用目录 C： Program Files\\Common Files\\the Microsoft Lync Server 2013\\CLSAgent 中的 CLSController。 或者，您可以使用 Lync Server 命令行管理程序发出 Windows PowerShell 命令。 重要区别在于，在命令行上使用 CLSController.exe 时，可供选择的可用方案是有限的。 使用 Windows PowerShell 时，可以定义在日志记录会话中使用的新方案。

如[Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)中所述，方案的元素为：

  - **提供程序**   如果您熟悉 OCSLogger，则提供程序是您选择的组件，用于告诉 OCSLogger 跟踪引擎应从什么方面收集日志。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您不熟悉 OCSLogger，则提供程序是集中式日志记录服务可从中收集日志的特定于服务器角色的组件。 有关提供程序配置的详细信息，请参阅[在 Lync Server 2013 中配置集中日志记录服务的提供程序](lync-server-2013-configuring-providers-for-centralized-logging-service.md)。

  - **Identity**   参数– identity 设置方案的范围和名称。 例如，您可以设置“全局”范围并使用“LyssServiceScenario”标识方案。 在将二者组合在一起时，可以定义 Identity（例如“global/LyssServiceScenario”）。
    
    （可选）可以使用 –Name 和 –Parent 参数。定义 Name 参数可对方案进行唯一标识。如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果使用 Name 和 Parent 参数，则无法使用 <STRONG>–Identity</STRONG> 参数。

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario cmdlet 创建新的方案

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要为日志记录会话创建新的方案，请使用 [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) 并定义方案的名称（即，对方案进行唯一标识的方式）。 从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。 然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。
    
    对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。
    
    若要使用定义的选项创建方案，请键入：
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    例如：
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    使用 –Name 和 –Parent 的备用格式：
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  每个范围只能有两个方案。 但是，不限于设置的提供程序数。 在此示例中，假定我们已创建三个提供程序，并且您希望将所有这三个提供程序分配给所定义的方案。 提供程序变量名称为 LyssProvider、ABServerProvider 和 SIPStackProvider。 若要定义多个提供程序并将其分配给某个方案，请在 Lync Server 命令行管理程序或 Windows PowerShell 命令提示符处键入以下内容：
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > 在 Windows PowerShell 中，创建使用<CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE>的值的哈希表的约定称为 "<EM>展开</EM>"。 有关 Windows PowerShell 中的展开的详细信息<A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>，请参阅。

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 Set-CsClsScenario cmdlet 修改现有方案

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  每个范围只能有两个方案。您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。若要定义新的方案，请执行下列命令（即，假定添加一个名为“S4Provider”的已定义的提供程序）：
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    例如：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 Remove-CsClsScenario cmdlet 删除现有方案

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要删除之前已定义的方案，请键入：
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    例如，删除定义的方案 site:Redmond/LyssServiceScenario：
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

**Remove-CsClsScenario** cmdlet 可删除指定的方案，但已捕获的跟踪信息仍将保留在日志中以供您搜索。

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>使用 ClsController.psm1 模块加载和卸载 Edit-CsClsScenario cmdlet

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。
    
    <div>
    

    > [!IMPORTANT]  
    > ClsController.psm1 模块是作为单独的 Web 下载提供的。 模块是 Lync Server 2013 调试工具的一部分。 默认情况下，调试工具将安装到目录 C:\Program Files\Lync Server 2013\Debugging Tools 中。

    
    </div>

2.  在 Windows PowerShell 中，键入：
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > 成功加载该模块后，将返回到 Windows PowerShell 命令提示符。 若要确认模块已加载并且 New-csclsscenario 可用，请键入<CODE>Get-Help Edit-CsClsScenario</CODE>。 您应看到 EditCsClsScenario 的语法的基本概要。

    
    </div>

3.  若要卸载模块，请键入：
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > 成功卸载该模块后，将返回到 Windows PowerShell 命令提示符。 若要确认模块已卸载，请键入<CODE>Get-Help Edit-CsClsScenario</CODE>。 Windows PowerShell 将尝试查找 cmdlet 的帮助并失败。

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块从方案中删除现有提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要从 AlwaysOn 方案中删除提供程序，请键入：
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    例如：
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    参数值的定位放置仅适用于 –Scenario 和 –Provider。必须显式定义所有其他参数。

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模块将提供程序添加到方案

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要将提供程序添加到 AlwaysOn 方案，请键入：
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    例如：
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel 可以是 "致命"、"错误"、"警告"、"信息"、"详细"、"调试" 或 "全部"。 – Flags 可以是提供程序支持的任何标志，如 TF\_COMPONENT、tf\_诊断。 –Flags 的值可以为 ALL
    
    还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

