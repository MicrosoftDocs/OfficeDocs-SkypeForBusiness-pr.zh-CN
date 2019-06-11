---
title: 'Lync Server 2013: 为集中式日志记录服务配置提供程序'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置集中式日志记录服务的提供商

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-03-19_

集中式日志记录服务中*提供商*的概念和配置是最重要的一项。 *供应商*直接映射到 lync server 跟踪模型中的 lync server 服务器角色组件。 该提供程序定义要跟踪的 Lync Server 2013 的组件、要收集的消息类型 (例如, 致命、错误或警告) 和标志 (例如 TF\_连接或 tf\_warning)。 提供程序是每个 Lync Server 服务器角色中的可跟踪组件。 通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。 可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。

若要使用 Lync Server Management Shell 运行集中式日志记录服务功能, 您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员, 或者是包含以下任一项的自定义 RBAC 角色这两个组。 若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Lync Server Management Shell 或 Windows PowerShell 提示中运行以下命令:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。 有两种方法可以发出集中式日志记录服务命令。 默认情况\\下, 在 "目录 C: 程序文件" 中, 您可以使用 CLSController 中的 "\\文件"\\, 这是 Microsoft\\Lync Server 2013 CLSAgent 的常见文件。 或者, 你可以使用 Lync Server Management Shell 颁发 Windows PowerShell 命令。 重要的区别在于, 在命令行中使用 CLSController 时, 有一个有限选择的方案, 其中提供程序已定义且不可更改, 但你可以定义日志级别。 通过使用 Windows PowerShell, 你可以定义要在日志记录会话中使用的新提供程序, 并对其创建、它们收集的内容以及它们收集数据的级别进行完全控制。

<div class="">


> [!IMPORTANT]  
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。<BR>集中式日志记录服务提供了许多已为你定义的方案, 而不是要求你深入了解提供程序的详细信息。 提供的方案涵盖了绝大多数您可能会遇到的问题。 在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。 强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。 虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。



</div>

在[Lync Server 2013 中介绍集中式日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md), 定义在方案中使用的提供程序的关键元素包括:

  - **提供程序**   如果你熟悉 OCSLogger, 则提供程序是你选择的组件, 用于告诉 OCSLogger 跟踪引擎应从中收集日志的内容。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您不熟悉 OCSLogger, 则提供商是集中式日志记录服务可以从中收集日志的服务器角色特定组件。 在集中式日志记录服务的情况下, CLSAgent 是集中日志记录服务的体系结构部分, 用于跟踪你在提供程序配置中定义的组件。

  - **日志记录级别**   OCSLogger 提供了为收集的数据选择多个级别的详细信息的选项。 此功能是集中式日志记录服务和方案的不可分割部分, 由**Type**参数定义。 您可以选择以下选项：
    
      - **All**   将收集已定义提供程序的日志中的 "严重"、"错误"、"警告" 和 "信息" 类型的跟踪消息。
    
      - **"严重**   " 仅收集指示已定义提供程序失败的跟踪消息。
    
      - **错误**   仅收集指示已定义的提供程序的错误的跟踪消息, 以及致命消息。
    
      - **警告**   仅收集指示已定义的提供程序的警告的跟踪消息, 以及致命错误和错误消息。
    
      - **Info**   仅收集指示已定义提供程序的信息性消息的跟踪消息, 以及致命错误和警告消息。
    
      - **详细**   收集已定义的提供程序的所有类型为严重、错误、警告和信息的跟踪消息。

  - **Flags**   OCSLogger 提供了选择每个提供商的标志的选项, 该选项定义了可以从跟踪文件中检索的信息类型。 可以根据提供程序选择以下标志：
    
      - **TF\_连接**   提供连接相关的日志条目。 这些日志包括与特定组件建立的连接的相关信息。 这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
      - **TF\_security**   提供与安全性相关的所有事件/日志条目。 例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
      - **TF\_** diagnostics   提供诊断事件, 可用于诊断组件或对其进行故障排除。 例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
      - **TF\_协议**   提供协议消息, 如 SIP 和组合的社区编解码器包消息。
    
      - **TF\_组件**   可对指定为提供程序一部分的组件进行日志记录。
    
      - **All**   设置提供程序可用的所有可用标志。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>查看有关现有集中式日志记录服务方案提供程序的信息

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  若要查看现有提供程序的配置，请键入：
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    例如，若要查看有关全局会议助理的信息，请键入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    此命令显示具有关联的标志、设置和组件的提供程序的列表。 如果显示的信息不够或列表对于默认 Windows PowerShell 列表格式太长, 则可以通过定义不同的输出方法来显示其他信息。 为此，请键入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>定义新的集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level 收集重要消息、错误消息、警告消息和信息性消息。 所使用的标志均为 Lyss 提供程序定义的所有标志, 并且包括\_tf CONNECTION、\_tf 诊断和\_tf 协议。

在定义变量 $LyssProvider 之后，可将其与 **New-CsClsScenario** cmdlet 结合使用以从 Lyss 提供程序中收集跟踪信息。 若要创建提供程序并将其分配给新的方案，请键入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>更改现有集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  若要更新或更改现有提供程序的配置，请键入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    然后，通过键入以下内容来更新方案以分配提供程序：
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。可通过使用 Get-CsClsScenario 查看新方案。有关详细信息，请参阅 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> 不会检查以确定标志是否有效。 请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。 如果标志的拼写不正确，则提供程序无法返回预期日志信息。



</div>

若要将其他提供程序添加到此方案，请键入：

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

其中，将通过已使用 **New-CsClsProvider** 过程定义的 Add 指令来定义每个提供程序。

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>删除方案提供程序

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。 若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。 完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。 例如, 我们的提供商 LyssProvider 定义为将 WPP 用作日志类型、设置为调试的级别以及标志集为 TF\_连接和 tf\_诊断。 您需要将标志更改为“All”。 若要更改提供程序，请键入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  若要完全删除方案及其关联的提供程序，请键入：
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    例如：
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > cmdlet <STRONG>Remove-CsClsScenario</STRONG> 不会提示您进行确认。 方案将连同已分配给它的提供程序一起被删除。 可通过重新运行最初用于创建方案的命令来重新创建方案。 没有用于恢复已删除的方案或提供程序的过程。

    
    </div>

在使用 **Remove-CsClsScenario** cmdlet 删除一个方案时，可以从作用域中完全删除此方案。 若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

