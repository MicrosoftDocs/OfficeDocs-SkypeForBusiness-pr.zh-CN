---
title: 配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 摘要： 了解如何在 Skype 为业务服务器 2015年配置方案提供集中式日志记录服务。
ms.openlocfilehash: a609d7406f59702aeb906a21132eff5f861ce037
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序
 
**摘要：**了解如何在 Skype 为业务服务器 2015年配置方案提供集中式日志记录服务。
  
概念和集中式日志记录服务的提供商的配置是一种最重要的是抓住。 Theproviders 直接映射到业务服务器服务器角色中的组件的业务服务器跟踪模型 Skype 的 Skype。 提供程序定义了业务服务器 2015 将描摹的消息 （例如，致命错误或警告） 为收集，以及标志 （例如，TF_Connection 或 TF_Diag） 的类型 Skype 的组成部分。 提供程序是在每个 Skype 业务服务器服务器角色可跟踪组件。 通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。 可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。
  
若要运行使用 Skype 业务服务器管理外壳的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色的成员，包含这两个组之一。 若要返回列表中的所有已分配给 （包括您自己创建的任何自定义的 RBAC 角色），此 cmdlet 的基于角色的访问控制 (RBAC) 角色运行下面的命令从 Skype 业务服务器管理外壳程序或 Windows PowerShell提示：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。 有两种方法将集中式日志记录服务命令。 默认情况下，可使用位于目录 C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 中的 CLSController.exe。 或者，您可以使用业务服务器管理外壳的 Skype 发布 Windows PowerShell 命令。 通过使用 Windows PowerShell，可以定义新的提供程序，用于在您的日志记录会话，和完全控制其创建，它们的收集，以及在哪个级别，它们收集的数据。
  
> [!IMPORTANT]
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。 
  
而不是需要深挖到的提供程序的详细信息，集中式日志记录服务为您提供了一些已定义的方案。 提供的方案涵盖了绝大多数您可能会遇到的问题。 在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。 强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。 虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。 
  
引入[业务 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)中，在方案中定义的提供程序使用的关键要素包括：
  
- **提供程序**如果您熟悉 OCSLogger，提供程序告诉 OCSLogger 跟踪引擎应收集日志从您选择的组件。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您还不熟悉 OCSLogger，提供程序服务器角色从记录集中的记录服务可以收集的特定组件。 在集中式日志记录服务，CLSAgent 是集中式日志记录服务的正在执行的操作将跟踪您的提供程序配置中定义的组件的体系结构的一部分。
    
- **日志记录级别**OCSLogger 提供的选项可供选择数收集到的数据的详细程度。 此功能是不可或缺的组成部分集中式日志记录服务和方案，并由**类型**参数定义。 您可以选择以下选项：
    
  - **所有**收集跟踪定义的提供程序类型致命的消息、 错误、 警告、 详细，和调试信息记录到日志。
    
  - **致命**收集仅跟踪消息定义为"严重"。
    
  - **错误**收集仅跟踪消息定义为"错误"或"严重"。
    
  - **警告**收集跟踪消息将类型的"警告，""错误"和"致命"。
    
  - **信息**收集指示定义提供程序，加上严重的信息性消息、 错误和警告消息的跟踪消息。
    
  - **详细**收集所有跟踪消息的类型，错误，警告和详细的定义提供程序。
    
  - 这是本质上的相当于**调试**为全部的致命错误，错误，警告，信息、 详细和调试类型的收集跟踪定义提供程序。
    
- **标志**OCSLogger 提供的选项若要定义哪种类型的信息可以从跟踪文件检索每个提供程序选择标志。 可以根据提供程序选择以下标志：
    
  - **TF_Connection**提供与连接相关的日志条目。 这些日志包括与特定组件建立的连接的相关信息。 这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
  - **TF_Security**提供所有与安全相关的事件/日志条目。 例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
  - **TF_Diag**提供可用于诊断或排除组件故障的诊断事件。 例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
  - **TF_Protocol**提供如结合社区编解码器包和 SIP 消息的协议消息。
    
  - **TF_Component**启用登录指定的提供程序的一部分的组件。
    
  - **所有**设置提供程序可用的所有可用标志。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要查看有关现有的集中式日志记录服务方案提供的信息

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要查看现有提供程序的配置，请键入：
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    例如，若要查看有关全局会议助理的信息，请键入：
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    此命令显示具有关联的标志、设置和组件的提供程序的列表。 如果显示的信息是不足够或列表默认 Windows PowerShell 列表格式太长，您可以通过定义不同的输出方法来显示其他信息。 为此，请键入：
    
  ```
  Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
  ```

    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>若要定义新的集中式日志记录服务方案提供商

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
  ```
  $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
  ```

    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
  ```

-级别收集致死，错误、 警告和信息消息。 使用的标志是所有这些定义的 Lyss 提供者，包括 TF_Connection、 TF_Diag 和 TF_Protocol.After 定义变量 $LyssProvider，您可以使用它与**新建 CsClsScenario** cmdlet 来跟踪收集 Lyss 提供程序。 若要创建提供程序并将其分配给新的方案，请键入：

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

其中，$LyssProvider 是包含定义的方案使用**New CsClsProvider**创建的变量。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>若要更改现有的集中式日志记录服务方案提供商

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要更新或更改现有提供程序的配置，请键入：
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    然后，通过键入以下内容来更新方案以分配提供程序：
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。 可通过使用 Get-CsClsScenario 查看新方案。 有关详细信息，请参阅[获取 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。
> [!CAUTION]
> **新建 ClsCsProvider**不会检查以确定是否为有效的标志。 请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。 如果标志的拼写不正确，则提供程序无法返回预期日志信息。
  
若要将其他提供程序添加到此方案，请键入：

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

在使用定义的每个提供程序添加指令已定义使用**New CsClsProvider**过程。
### <a name="to-remove-a-scenario-provider"></a>删除方案提供程序

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。 若要删除提供商，必须使用替换指令**集 CsClsScenario**的提供程序参数。 完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。 例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF_CONNECTION 和 TF_DIAG。 您需要更改标志的"全部"。 若要更改提供程序，请键入：
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
  ```

  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
  ```

3. 若要完全删除方案及其关联的提供程序，请键入：
    
  ```
  Remove-CsClsScenario -Identity <scope and name of scenario>
  ```

    例如：
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
  ```

    > [!CAUTION]
    > 该 cmdlet**删除 CsClsScenario**不提示您进行确认。 方案将连同已分配给它的提供程序一起被删除。 可通过重新运行最初用于创建方案的命令来重新创建方案。 没有用于恢复已删除的方案或提供程序的过程。
  
当您删除一个方案通过**删除 CsClsScenario** cmdlet 时，您完全方案从范围中移除。 若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。
## <a name="see-also"></a>另请参阅

#### 

[获得 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[新 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[删除 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[一组 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[新 CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)

