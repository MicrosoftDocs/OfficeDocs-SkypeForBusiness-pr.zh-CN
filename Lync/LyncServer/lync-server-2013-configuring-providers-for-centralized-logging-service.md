---
title: Lync Server 2013：为集中日志记录服务配置提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dbb8c1a2e24290e4ab2805bed191e5f2dc86bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置集中日志记录服务的提供程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-19_

集中日志记录服务中*提供程序*的概念和配置是最重要的一项。 *提供程序*直接映射到 lync server 跟踪模型中的 lync server 服务器角色组件。 提供程序定义要跟踪的 Lync Server 2013 的组件、要收集的邮件的类型（例如，致命、错误或警告）以及标志（例如，TF\_CONNECTION 或 tf\_的诊断）。 提供程序是每个 Lync Server 服务器角色中的可跟踪组件。 通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。 可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。

若要使用 Lync Server 命令行管理程序运行集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含以下任一项的自定义 RBAC 角色：这两个组。 若要返回已将此 cmdlet 分配到的所有基于角色的访问控制（RBAC）角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。 有两种方法可以发出集中式日志记录服务命令。 默认情况\\下，您可以使用目录 C： Program Files\\Common Files\\the Microsoft Lync Server 2013\\CLSAgent 中的 CLSController。 或者，您可以使用 Lync Server 命令行管理程序发出 Windows PowerShell 命令。 重要区别在于，在命令行中使用 CLSController.exe 时，可供选择的可用方案是有限的，在这些方案中，提供程序已被定义且不可更改，但您可以定义日志级别。 通过使用 Windows PowerShell，可以定义在日志记录会话中使用的新提供程序，并能够完全控制自己的创建、收集的内容以及它们收集数据的级别。

<div class="">


> [!IMPORTANT]  
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。<BR>集中日志记录服务提供了许多已为您定义的方案，而不是要求您深入了解提供程序的详细信息。 提供的方案涵盖了绝大多数您可能会遇到的问题。 在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。 强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。 虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。



</div>

在[Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)中，定义在方案中使用的提供程序的关键元素包括：

  - **提供程序**   如果您熟悉 OCSLogger，则提供程序是您选择的组件，用于告诉 OCSLogger 跟踪引擎应从什么方面收集日志。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您不熟悉 OCSLogger，则提供程序是集中式日志记录服务可从中收集日志的特定于服务器角色的组件。 在集中日志记录服务的情况下，CLSAgent 是集中日志记录服务的体系结构部分，该组件将跟踪您在提供程序配置中定义的组件。

  - **日志记录级别**   OCSLogger 提供了选择所收集数据的多个详细信息级别的选项。 此功能是集中日志记录服务和方案不可或缺的一部分，由**Type**参数定义。 您可以选择以下选项：
    
      - **All**   为定义的提供程序收集类型为 "致命"、"错误"、"警告" 和 "信息" 的跟踪消息。
    
      - **致命**   仅收集指示定义的提供程序发生故障的跟踪消息。
    
      - **错误**   仅收集指示定义的提供程序的错误以及致命消息的跟踪消息。
    
      - **警告**   仅收集指示定义的提供程序的警告的跟踪消息，以及致命错误和错误消息。
    
      - **Info**   仅收集指示定义的提供程序的信息性消息的跟踪消息，以及致命错误和警告消息。
    
      - **详细**   收集定义的提供程序的所有类型为致命、错误、警告和信息的跟踪消息。

  - **Flags**   OCSLogger 提供了选择每个提供程序的标记的选项，这些提供程序定义了可从跟踪文件中检索的信息类型。 可以根据提供程序选择以下标志：
    
      - **TF\_connection**   提供与连接相关的日志条目。 这些日志包括与特定组件建立的连接的相关信息。 这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
      - **TF\_security**   提供了与安全性相关的所有事件/日志条目。 例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
      - **TF\_** diagnostics   提供了可用于诊断或排除组件故障的诊断事件。 例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
      - **TF\_协议**   提供了协议消息，如 SIP 和组合的社区编解码器包消息。
    
      - **TF\_组件**   可在指定为提供程序的一部分的组件上启用日志记录。
    
      - **All**   设置可用于提供程序的所有可用标志。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>查看有关现有集中日志记录服务方案提供程序的信息

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要查看现有提供程序的配置，请键入：
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    例如，若要查看有关全局会议助理的信息，请键入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    此命令显示具有关联的标志、设置和组件的提供程序的列表。 如果显示的信息不足，或者列表对默认 Windows PowerShell 列表格式来说太长，则可以通过定义不同的输出方法来显示其他信息。 为此，请键入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>定义新的集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level 收集重要消息、错误消息、警告消息和信息性消息。 使用的标志都是为 Lyss 提供程序定义的所有标志，并包括\_tf CONNECTION、\_tf 诊断和\_tf 协议。

在定义变量 $LyssProvider 之后，可将其与 **New-CsClsScenario** cmdlet 结合使用以从 Lyss 提供程序中收集跟踪信息。 若要创建提供程序并将其分配给新的方案，请键入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>更改现有的集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要更新或更改现有提供程序的配置，请键入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    然后，通过键入以下内容来更新方案以分配提供程序：
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。 可通过使用 Get-CsClsScenario 查看新方案。 有关详细信息，请参阅 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。

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

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。 若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。 完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。 例如，我们的提供商 LyssProvider 使用 WPP 作为日志类型进行定义，将 level 设置为 Debug，而 flags set 为\_tf CONNECTION 和\_tf settings。 您需要将标志更改为“All”。 若要更改提供程序，请键入：
    
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


[New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[新 New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[新 CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

