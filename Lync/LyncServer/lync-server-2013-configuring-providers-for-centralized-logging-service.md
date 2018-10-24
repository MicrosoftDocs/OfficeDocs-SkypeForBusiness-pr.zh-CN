---
title: 为集中日志记录服务配置提供商
TOCTitle: 为集中日志记录服务配置提供商
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49888449
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为集中日志记录服务配置提供商

 

_**上一次修改主题：** 2014-03-19_

集中日志记录服务中的*提供程序* 的概念和配置是需要理解的最重要部分之一。*提供程序* 直接映射到 Lync Server 跟踪模型中的 Lync Server 服务器角色组件。提供程序定义了将跟踪的 Lync Server 2013 组件、要收集的消息类型（例如，严重、错误或警告）和标志（例如，TF\_Connection 或 TF\_Diag）。提供程序是每个 Lync Server 服务器角色中的可跟踪组件。通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。

若要使用 Lync Server 命令行管理程序运行集中日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员，或是包含这两个组之一的自定义 RBAC 角色。若要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色（包括您自己创建的任何自定义 RBAC 角色）的列表，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。可通过两种方式发出集中日志记录服务命令。默认情况下，可使用位于目录 C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent 中的 CLSController.exe。也可以使用 Lync Server 命令行管理程序发出 Windows PowerShell 命令。重要区别在于，在命令行中使用 CLSController.exe 时，可供选择的可用方案是有限的，在这些方案中，提供程序已被定义且不可更改，但您可以定义日志级别。通过使用 Windows PowerShell，可以定义在日志记录会话中使用的新提供程序，并对日志记录会话的创建、其收集的内容及其收集数据的级别进行完全控制。

> [!IMPORTANT]
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。<br />
> 集中日志记录服务提供了大量已为您定义的方案，这样您便无需深入了解提供程序的详细信息。提供的方案涵盖了绝大多数您可能会遇到的问题。在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。


如[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)中所述，用于定义在方案中使用的提供程序的关键元素为：

  - **提供程序**   如果您熟悉 OCSLogger，则提供程序为可供您选择用来告知 OCSLogger 跟踪引擎应从中收集日志的内容的组件。提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。如果您不熟悉 OCSLogger，则提供程序为集中日志记录服务可从中收集日志的特定于服务器角色的组件。对于集中日志记录服务，CLSAgent 是对您在提供程序配置中定义的组件进行跟踪的集中日志记录服务的组成部分。

  - **日志记录级别**   OCSLogger 提供了用于选择所收集数据的许多级别的详细信息的选项。此功能是集中日志记录服务和方案的必不可少的一部分，它是由 **Type** 参数定义的。您可以选择以下选项：
    
      - **All**   将类型为 fatal、error、warning 和 info 的跟踪消息收集到定义的提供程序的日志中。
    
      - **Fatal**   仅收集指示定义的提供程序失败的跟踪消息。
    
      - **Error**   仅收集指示定义的提供程序的错误的跟踪消息以及重要消息。
    
      - **Warning**   仅收集指示定义的提供程序的警告的跟踪消息以及重要消息和错误消息。
    
      - **Info**   仅收集指示定义的提供程序的信息性消息的跟踪消息以及重要消息、错误消息和警告消息。
    
      - **Verbose**   收集定义的提供程序的类型为 fatal、error、warning 和 info 的所有跟踪消息。

  - **标志**   OCSLogger 提供了用于为每个定义了可从跟踪文件中检索的信息类型的提供程序选择标志的选项。可以根据提供程序选择以下标志：
    
      - **TF\_Connection**   提供与连接相关的日志条目。这些日志包括与特定组件建立的连接的相关信息。这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
      - **TF\_Security**   提供与安全性相关的所有事件/日志条目。例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
      - **TF\_Diag**   提供可用于诊断组件或对组件进行故障排除的诊断事件。例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
      - **TF\_Protocol**   提供协议消息，例如 SIP 和 CCCP 消息。
    
      - **TF\_Component**   在指定为提供程序的一部分的组件上启用日志记录。
    
      - **All**   设置适用于提供程序的所有可用标志。

## 查看有关现有集中日志记录服务方案提供程序的信息

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  若要查看现有提供程序的配置，请键入：
    
        Get-CsClsScenario -Identity <scope and scenario name>
    
    例如，若要查看有关全局会议助理的信息，请键入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    此命令显示具有关联的标志、设置和组件的提供程序的列表。如果显示的信息不足或列表对于默认的 Windows PowerShell 列表格式过长，您可以通过定义其他输出方法来显示附加信息。为此，请键入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。

## 定义新的集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level 收集重要消息、错误消息、警告消息和信息性消息。使用的标志都是为 Lyss 提供程序定义的标志，它们包括 TF\_Connection、TF\_Diag 和 TF\_Protocol。

在定义变量 $LyssProvider 之后，可将其与 **New-CsClsScenario** cmdlet 结合使用以从 Lyss 提供程序中收集跟踪信息。若要创建提供程序并将其分配给新的方案，请键入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。

## 更改现有集中日志记录服务方案提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  若要更新或更改现有提供程序的配置，请键入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    然后，通过键入以下内容来更新方案以分配提供程序：
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。可通过使用 Get-CsClsScenario 查看新方案。有关详细信息，请参阅 [Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)。

> [!WARNING]
> <strong>New-ClsCsProvider</strong> 不会检查以确定标志是否有效。请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。如果标志的拼写不正确，则提供程序无法返回预期日志信息。


若要将其他提供程序添加到此方案，请键入：

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

其中，将通过已使用 **New-CsClsProvider** 过程定义的 Add 指令来定义每个提供程序。

## 删除方案提供程序

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF\_CONNECTION 和 TF\_DIAG。您需要将标志更改为“All”。若要更改提供程序，请键入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

       &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  若要完全删除方案及其关联的提供程序，请键入：
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    例如：
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    > [!WARNING]
    > cmdlet <strong>Remove-CsClsScenario</strong> 不会提示您进行确认。方案将连同已分配给它的提供程序一起被删除。可通过重新运行最初用于创建方案的命令来重新创建方案。没有用于恢复已删除的方案或提供程序的过程。


在使用 **Remove-CsClsScenario** cmdlet 删除一个方案时，可以从作用域中完全删除此方案。若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。

## 另请参阅

#### 其他资源

[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider)

