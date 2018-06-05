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
description: 摘要： 了解如何配置方案提供程序 the Centralized Logging Service 中 Skype 业务服务器 2015年。
ms.openlocfilehash: bea50b6c1ea2fa805e407db4f6dd3fcfb761b4ef
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504346"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序
 
**摘要：** 了解如何配置方案提供程序 the Centralized Logging Service 中 Skype 业务服务器 2015年。
  
概念和 Centralized Logging Service 中的提供程序的配置是最重要的是抓住之一。 Theproviders 直接映射到业务 Server 服务器角色组件中的业务服务器跟踪模型 Skype 的 Skype。 提供程序定义 Skype 的组件业务服务器 2015 将跟踪消息 （如 fatal、 error 或 warning） 收集，和 （例如，TF_Connection 或 TF_Diag） 的标记的类型。 提供程序是中为 Business Server 服务器角色的每个 Skype 的可跟踪组件。 通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。 可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。
  
若要运行的业务 Server 命令行管理程序中使用 Skype 的集中日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员的包含这两个组之一。 若要返回的所有列表已分配给 （包括您自己创建任何自定义 RBAC 角色），此 cmdlet 的基于角色的访问控制 (RBAC) 角色运行以下命令从 Skype 业务 Server 命令行管理程序或 Windows PowerShell提示：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。 有两种方法来发出 Centralized Logging Service 命令。 默认情况下，可使用位于目录 C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 中的 CLSController.exe。 或者，您可以使用的业务 Server 命令行管理程序 Skype 发出 Windows PowerShell 命令。 使用 Windows PowerShell，您可以定义新提供程序使用在您的日志记录会话，并具有完全控制其创建，它们收集和层面上它们收集数据。
  
> [!IMPORTANT]
> 如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。 
  
而不是要求您深细化提供程序的详细信息，the Centralized Logging Service 为您提供了大量已定义的方案。 提供的方案涵盖了绝大多数您可能会遇到的问题。 在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。 强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。 虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。 
  
在[中的业务 2015 Skype Centralized Logging Service](centralized-logging-service.md)中引入的方案中定义的提供程序使用的关键要素包括：
  
- **提供程序**如果您熟悉 OCSLogger，提供程序选择以告知 OCSLogger 跟踪引擎应从中收集日志的组件。 提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。 如果您不熟悉 OCSLogger，提供程序服务器角色中的特定组件的 the Centralized Logging Service 可以收集日志。 Centralized Logging Service 中，对于 clsagent 的通信是 the Centralized Logging Service 的执行操作的跟踪提供程序配置中定义的组件的体系结构的一部分。
    
- **日志记录级别**OCSLogger 提供的选项可供选择的收集的数据的详细信息的级别数。 此功能是组成部分的集中日志记录服务和方案，并由**Type**参数定义。 您可以选择以下选项：
    
  - **所有**收集跟踪消息的类型为 fatal、 错误、 警告、 verbose 和和调试信息写入日志中定义的提供程序。
    
  - **致命**收集定义为"Fatal。"的跟踪消息
    
  - **错误**收集定义为"错误"或"致命错误。"的跟踪消息
    
  - **警告**仅收集的跟踪消息类型的"Warning，""错误"和"致命"。
    
  - **信息**收集指示定义的提供程序，以及致命的信息性消息、 错误和警告消息的跟踪消息。
    
  - **Verbose**收集类型，错误，警告和详细定义的提供程序的所有跟踪的消息。
    
  - **调试**这是本质上是等效的全部-类型致命错误 Error、 Warning、 Info、 Verbose 和 Debug 收集跟踪定义的提供程序。
    
- **标志**OCSLogger 提供的选项选择定义什么类型的信息，则无法从跟踪文件检索每个提供程序的标志。 可以根据提供程序选择以下标志：
    
  - **TF_Connection**提供连接相关的日志条目。 这些日志包括与特定组件建立的连接的相关信息。 这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。
    
  - **TF_Security**提供与安全相关的所有事件/日志条目。 例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。
    
  - **TF_Diag**提供可用于诊断或解决组件的诊断事件。 例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。
    
  - **TF_Protocol**提供协议消息，例如 SIP 和组合社区编解码器包消息。
    
  - **TF_Component**启用日志记录对指定为提供程序的一部分的组件。
    
  - **所有**设置提供程序可用的所有可用标志。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要查看有关现有 Centralized Logging Service 方案提供程序的信息

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要查看现有提供程序的配置，请键入：
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    例如，若要查看有关全局会议助理的信息，请键入：
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    此命令显示具有关联的标志、设置和组件的提供程序的列表。 如果显示的信息不足或列表的默认 Windows PowerShell 的列表格式太长，则可以通过定义不同的输出方法显示的其他信息。 为此，请键入：
    
  ```
  Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
  ```

    此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>若要定义新的集中日志记录服务方案提供程序

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：
    
  ```
  $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
  ```

    例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
  ```

-级别收集致命，错误、 警告和信息的邮件。 使用的标志是所有这些定义 Lyss 提供程序和包括 TF_Connection、 TF_Diag 和定义变量 $LyssProvider TF_Protocol.After，您可以使用它使用**New-csclsscenario** cmdlet 收集跟踪从 Lyss 提供程序。 若要创建提供程序并将其分配给新的方案，请键入：

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

其中 $LyssProvider 是包含使用**New-csclsprovider**创建的定义的方案的变量。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>若要更改现有 Centralized Logging Service 方案提供程序

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 若要更新或更改现有提供程序的配置，请键入：
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    然后，通过键入以下内容来更新方案以分配提供程序：
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。 可通过使用 Get-CsClsScenario 查看新方案。 有关详细信息，请参阅[Get-csclsscenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。
> [!CAUTION]
> **新建 ClsCsProvider**不检查以确定是否有效标志。 请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。 如果标志的拼写不正确，则提供程序无法返回预期日志信息。
  
若要将其他提供程序添加到此方案，请键入：

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

其中每个提供程序定义的 Add 指令已定义使用**New-csclsprovider**过程。
### <a name="to-remove-a-scenario-provider"></a>删除方案提供程序

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。 要删除提供程序，必须使用**Set-csclsscenario**的提供程序参数替换指令。 完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。 例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF_CONNECTION 和 TF_DIAG。 您需要更改的标记为"All"。 若要更改提供程序，请键入：
    
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
    > **Remove-csclsscenario** cmdlet 不会提示您进行确认。 方案将连同已分配给它的提供程序一起被删除。 可通过重新运行最初用于创建方案的命令来重新创建方案。 没有用于恢复已删除的方案或提供程序的过程。
  
使用**Remove-csclsscenario** cmdlet 删除方案时，您将完全作用域中删除方案。 若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。
## <a name="see-also"></a>另请参阅

[Get-csclsscenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-csclsscenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-csclsscenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-csclsprovider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)