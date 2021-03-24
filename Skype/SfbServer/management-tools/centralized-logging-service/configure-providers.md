---
title: Configure providers for Centralized Logging Service in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 摘要：了解如何为 Skype for Business Server 2015 中的集中日志记录服务配置方案提供程序。
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098848"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configure providers for Centralized Logging Service in Skype for Business Server 2015
 
**摘要：** 了解如何在 Skype for Business Server 2015 中为集中日志记录服务配置方案提供程序。
  
集中日志记录服务中的提供程序的概念和配置是必须掌握的最重要的概念之一。 这些角色直接映射到 Skype for Business Server 跟踪模型中的 Skype for Business Server 服务器角色组件。 提供商定义将跟踪的 Skype for Business Server 2015 的组件、要收集的消息类型 (例如，要收集的致命消息、错误或警告) 以及标志 (例如 TF_Connection 或 TF_Diag) 。 提供程序是每个 Skype for Business Server 服务器角色中的可跟踪组件。 通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。 可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。
  
若要使用 Skype for Business Server 命令行管理程序运行集中日志记录服务功能，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。 要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表 (包括您自己创建的任何自定义 RBAC 角色) ，请从 Skype for Business Server 命令行管理程序 或 Windows PowerShell 提示符运行以下命令：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。 有两种方法可以发出集中日志记录服务命令。 默认情况下，CLSController.exe位于目录 C：\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 中的文件。 或者，可以使用 Skype for Business Server 命令行管理程序发出Windows PowerShell命令。 通过使用Windows PowerShell，您可以定义用于日志记录会话的新提供程序，并完全控制其创建、收集内容以及收集数据的级别。
  
> [!IMPORTANT]
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。 
  
集中日志记录服务提供了许多已定义的方案，而无需深入了解提供程序的详细信息。 提供的方案涵盖了绝大多数您可能会遇到的问题。 在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。 强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。 虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。 
  
在 [Skype for Business 2015](centralized-logging-service.md)的集中日志记录服务中引入，定义用于方案的提供程序的关键元素包括：
  
- **提供程序** 如果您熟悉 OCSLogger，则提供程序是选择告知 OCSLogger 跟踪引擎应从哪些内容收集日志的组件。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您不熟悉 OCSLogger，则提供程序是集中日志记录服务可以从中收集日志的服务器角色特定组件。 对于集中日志记录服务，CLSAgent 是集中日志记录服务的体系结构部分，用于跟踪在提供程序配置中定义的组件。
    
- **日志记录级别** OCSLogger 提供了为收集的数据选择多个级别的详细信息的选项。 此功能是集中日志记录服务和方案的组成部分，由 **Type** 参数定义。 您可以选择以下选项：
    
  - **全部** 将类型为 fatal、error、warning、verbose 和 debug 的信息的跟踪消息收集到定义的提供程序的日志中。
    
  - **Fatal** 仅收集定义为"Fatal"的跟踪消息。
    
  - **错误** 仅收集定义为"Error"或"Fatal"的跟踪消息。
    
  - **警告** 仅收集类型为"Warning"、"Error"和"Fatal"的跟踪消息。
    
  - **信息** 仅收集指示定义的提供程序的信息性消息的跟踪消息，以及重要消息、错误消息和警告消息。
    
  - **Verbose** 收集定义提供程序的类型为 fatal、error、warning 和 verbose 的所有跟踪消息。
    
  - **调试** 这本质上是"全部"的等效项 - 为定义的提供程序收集类型为 Fatal、Error、Warning、Info、Verbose 和 Debug 的跟踪。
    
- **Flags** OCSLogger 提供了为定义了可以从跟踪文件中检索的信息类型的每个提供程序选择标志的选项。 可以根据提供程序选择以下标志：
    
  - **TF_Connection** 提供与连接相关的日志条目。 这些日志包括与特定组件建立的连接的相关信息。 这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
  - **TF_Security** 提供与安全相关的所有事件/日志条目。 例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
  - **TF_Diag** 提供可用于诊断组件或对组件进行故障排除的诊断事件。 例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
  - **TF_Protocol** 提供协议消息，如 SIP 消息和组合社区编解码器包消息。
    
  - **TF_Component** 在指定为提供程序一部分的组件上启用日志记录。
    
  - **全部** 设置提供程序可用的所有可用标志。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>查看有关现有集中日志记录服务方案提供程序的信息

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 若要查看现有提供程序的配置，请键入：
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    例如，若要查看有关全局会议助理的信息，请键入：
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    此命令显示具有关联的标志、设置和组件的提供程序的列表。 如果显示的信息不足或列表对于默认列表Windows PowerShell过长，则可以通过定义其他输出方法来显示其他信息。 为此，请键入：
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>定义新的集中日志记录服务方案提供程序

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Level 收集致命消息、错误消息、警告消息和信息消息。 使用的标志都是为 Lyss 提供程序定义的标志，包括 TF_Connection、TF_Diag 和 TF_Protocol。定义变量 $LyssProvider 后，您可以与 **New-CsClsScenario** cmdlet 一起使用它从 Lyss 提供程序收集跟踪。 若要创建提供程序并将其分配给新的方案，请键入：

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>更改现有的集中日志记录服务方案提供程序

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 若要更新或更改现有提供程序的配置，请键入：
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    然后，通过键入以下内容来更新方案以分配提供程序：
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。 可通过使用 Get-CsClsScenario 查看新方案。 有关详细信息，请参阅 [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)。
> [!CAUTION]
> **New-ClsCsProvider** 不会检查以确定标志是否有效。 请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。 如果标志的拼写不正确，则提供程序无法返回预期日志信息。
  
若要将其他提供程序添加到此方案，请键入：

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

其中，将通过已使用 **New-CsClsProvider** 过程定义的 Add 指令来定义每个提供程序。
### <a name="to-remove-a-scenario-provider"></a>删除方案提供程序

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。 若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。 完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。 例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF_CONNECTION 和 TF_DIAG。 您需要将标志更改为"All"。 若要更改提供程序，请键入：
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. 若要完全删除方案及其关联的提供程序，请键入：
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    例如：
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > cmdlet **Remove-CsClsScenario** 不会提示您进行确认。 方案将连同已分配给它的提供程序一起被删除。 可通过重新运行最初用于创建方案的命令来重新创建方案。 没有用于恢复已删除的方案或提供程序的过程。
  
在使用 **Remove-CsClsScenario** cmdlet 删除一个方案时，可以从作用域中完全删除此方案。 若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。
## <a name="see-also"></a>另请参阅

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)