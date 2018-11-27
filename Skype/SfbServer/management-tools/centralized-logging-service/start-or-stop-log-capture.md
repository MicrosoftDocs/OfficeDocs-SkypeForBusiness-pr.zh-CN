---
title: 在 Skype for Business Server 2015 中启动或停止捕获 CLS 日志
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 摘要： 了解如何启动或停止正在 Skype 的集中日志记录服务日志捕获会话的业务服务器 2015年。
ms.openlocfilehash: d3dc2ca58964908bda0d8c2de845297bb0cb951b
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699857"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中启动或停止捕获 CLS 日志
 
**摘要：** 了解如何启动或停止正在 Skype 的集中日志记录服务日志捕获会话的业务服务器 2015年。
  
要捕获使用 the Centralized Logging Service 的跟踪日志，您发出命令开始日志记录在一个或多个计算机和池上。 此外问题参数定义哪些计算机或池，什么情况下 （如 AlwaysOn、 另一个预定义的方案或已创建的方案），运行哪些 Skype 跟踪的业务服务器组件 （例如，S4、 SipStack）。
  
若要捕获正确的信息，您必须使用正确的方案收集问题相关信息。 Centralized Logging Service 中，在一个方案是打开日志记录基于一服务器组件、 日志记录级别和标志，这更加高效和比不必在每台服务器上定义这些元素有用的概念。 您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。
  
默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。
  
The Centralized Logging Service 提供了两种方式发出命令。 主题大量具有已重点集中在使用通过 Skype Windows PowerShell 进行业务 Server 命令行管理程序。 使用数复杂的配置和命令的功能集中日志记录服务用于倾向于 Windows PowerShell。 由于通过业务 Server 命令行管理程序 Skype 的 Windows PowerShell 几乎普遍的 Skype 业务服务器中的所有功能，因此只有 Windows PowerShell 命令进行讨论。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用 Windows PowerShell 使用基本命令运行 Start-csclslogging

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 键入以下命令 the Centralized Logging Service 中开始日志记录方案：
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    例如，要启动 **AlwaysOn** 方案，可键入：
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn 方案没有默认持续时间。 除非您明确将其停止使用**Stop-csclslogging** cmdlet，将运行此方案。 有关详细信息，请参阅 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。 对于所有其他方案，默认持续时间为 4 小时。 
  
3. 按 Enter 运行命令。 
    
    > [!NOTE]
    > 可能需要一小段时间（30 到 60 秒）命令才运行完毕，并接收从您的部署中的计算机返回的状态。 
  
     ![运行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 要开始另一个方案，请使用**Start-csclslogging** cmdlet 与其他方案的名称运行，如下所示 （例如，方案**身份验证**）：
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > 在任意时间可以在任何给定计算机上运行总共两个方案。如果命令是全局范围的，则部署中的所有计算机将运行方案。要启动第三个方案，必须在您要运行新方案的计算机、池、站点或全局范围上停止日志记录。如果已启动全局范围，则可以在一个或多个计算机和池上停止一种方案或同时停止两种方案的日志记录。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用 Windows PowerShell 使用高级的命令运行 Start-csclslogging

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 也可以使用其他参数来管理日志记录命令。 您可以使用-持续时间调整的方案以运行的时间长度。 您还可以定义的计算机的计算机的完全限定域名 (Fqdn)，以逗号分隔列表，或者-池，以逗号分隔列表要运行登录的池的 Fqdn。
    
    您为池“pool01.contoso.net”上的 UserReplicator 方案启动了日志记录会话。 您还定义日志记录会话持续时间为 8 小时。 为此，请键入：
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    此方案成功执行后将返回类似如下的结果：
    
     ![运行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
注意，在此示例中，正在运行的方案是 AlwaysOn 和 UserReplicator。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>停止捕获集中日志记录服务日志
<a name="stop"> </a>

您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。 一般情况下，不需要在其中停止日志记录会话的很多情况。 例如，无需先停止日志记录就可以搜索日志和更改配置。 如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。 有关详细信息，请参阅 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。
  
> [!NOTE]
> 在确定了可以在给定部署、池或计算机上运行哪些方案后，您需要记住，在**每台计算机**上只能运行两个方案：AlwaysOn 和一个自定义方案。 如果您要记录某个池上的活动，应将一个池视为单一实体。 在大多数情况下，在池中的每台计算机上运行不同方案没有意义。 了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。 例如，如果您考虑 userreplicator，将很少值中有边缘服务器或边缘池上运行 UserReplicator。 
  
在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。尽管 AlwaysOn 方案会收集各类提供商的信息，在多种应用下均意义显著，但具体方案可能只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，那么您就可能存在问题、没有使用价值的数据，最终效果与根本没有运行该方案时无异。
  
若要使用适用于业务 Server 命令行管理程序 Skype 控制的集中日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员包含这两个组之一。 若要返回的已分配此 cmdlet 的所有 RBAC 角色的列表 （包括您自己创建任何自定义 RBAC 角色），请业务 Server 命令行管理程序或 Windows PowerShell 提示符从 Skype 运行以下命令：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 因此您可能想知道： 现在，已启用日志记录，其中日志保留？ 由于您可以访问使用发送到 CLS 代理的管理命令行管理程序查询日志中存储的信息，并且可以输出为若干种可能的文件格式的结果，其中每台服务器上 CLS 代理都将保留其记录不知道实际重要。  可以将日志文件保存到您指定和阅读并分析使用各种工具，包括**Snooper.exe**和可阅读一个文本文件，如**Notepad.exe**任何工具的位置。 Snooper.exe 是业务 Server 2015 调试工具 Skype 的一部分，并且可用作[Web 下载](https://go.microsoft.com/fwlink/p/?LinkId=285257)。

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>要停止当前正在运行 Centralized Logging Service 会话

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 查询 the Centralized Logging Service 以找出哪些方案当前正在运行通过键入以下命令：
    
   ```
   Show-CsClsLogging
   ```

   ![调用 Show-CsCl 后的 Windows PowerShell 控制台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。有关详细信息，请参阅 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)。
    
3. 若要使用特定方案停止当前正在运行的日志记录会话，请键入：
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   例如：
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   此命令将在 pool01.contoso.net 上使用 UserReplicatior 方案停止日志记录。
    
    > [!NOTE]
    > 在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。有关详细信息，请参阅 [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)。 
  
作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负载故障排除过程中执行该任务。
## <a name="see-also"></a>另请参阅
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)