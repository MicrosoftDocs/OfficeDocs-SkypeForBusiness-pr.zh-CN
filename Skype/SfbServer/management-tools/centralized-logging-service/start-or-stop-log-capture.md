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
description: 摘要： 了解如何启动或停止的业务服务器 2015 Skype 在集中式日志记录服务日志捕获会话。
ms.openlocfilehash: 81db8c521f96306e118ebe5fe8053ff6e849dd54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中启动或停止捕获 CLS 日志
 
**摘要：**了解如何启动或停止的业务服务器 2015 Skype 在集中式日志记录服务日志捕获会话。
  
要捕获跟踪日志使用集中式日志记录服务，则发出一个命令以开始记录一个或多个计算机和池上。 此外颁发参数，以定义哪些计算机或池，什么样的方案 （如 AlwaysOn、 预定义的另一种情况或您已经创建了一个方案），运行什么 Skype 业务服务器组件 （例如，S4，SipStack） 跟踪。
  
若要捕获正确的信息，您必须使用正确的方案收集问题相关信息。 在集中式日志记录服务中，一个方案是启用日志记录基于集合的服务器组件、 日志记录级别和标志，这更有效且比无需在每台服务器上定义这些元素非常有用的概念。 您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。
  
默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。
  
集中式日志记录服务提供了两种方式发出命令。 许多主题已被重点集中在使用 Windows PowerShell 通过 Skype 业务服务器管理外壳。 使用多个复杂的配置和命令的能力倾向于集中式日志记录服务使用的 Windows PowerShell。 由于 Windows PowerShell 通过 Skype 的业务服务器管理外壳几乎到处都有为 Skype 业务服务器中的所有函数，讨论了只有 Windows PowerShell 命令。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>若要使用 Windows PowerShell 使用基本命令运行开始 CsClsLogging

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 通过键入以下使用集中式日志记录服务启动日志记录方案：
    
  ```
  Start-CsClsLogging -Scenario <name of scenario>
  ```

    例如，要启动 **AlwaysOn** 方案，可键入：
    
  ```
  Start-CsClsLogging -Scenario AlwaysOn
  ```

    > [!NOTE]
    > AlwaysOn 方案没有默认持续时间。 这种情况下将运行直到其显式停止使用**Stop CsClsLogging** cmdlet。 有关详细信息，请参阅[Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。 对于所有其他方案，默认持续时间为 4 小时。 
  
3. 按 Enter 运行命令。 
    
    > [!NOTE]
    > 可能需要一小段时间（30 到 60 秒）命令才运行完毕，并接收从您的部署中的计算机返回的状态。 
  
     ![运行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 要开始另一种情况，使用**开始 CsClsLogging** cmdlet 与其他方案的名称，如下所示 （例如，方案**的身份验证**） 运行：
    
  ```
  Start-CsClsLogging -Scenario Authentication
  ```

    > [!IMPORTANT]
    > 在任意时间可以在任何给定计算机上运行总共两个方案。如果命令是全局范围的，则部署中的所有计算机将运行方案。要启动第三个方案，必须在您要运行新方案的计算机、池、站点或全局范围上停止日志记录。如果已启动全局范围，则可以在一个或多个计算机和池上停止一种方案或同时停止两种方案的日志记录。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>若要使用 Windows PowerShell 使用高级命令运行开始 CsClsLogging

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 也可以使用其他参数来管理日志记录命令。 您可以使用的持续时间来调整该方案要运行的时间长度。 您还可以定义的计算机，计算机的完全合格的域名 (Fqdn) 用一个逗号分隔的列表，或者-池，一个逗号分隔列表要运行登录的池的 Fqdn。
    
    首先，UserReplicator 方案的日志记录会话池"pool01.contoso.net"上。 您还定义日志记录会话持续时间为 8 小时。 为此，请键入：
    
  ```
  Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"

  ```

    此方案成功执行后将返回类似如下的结果：
    
     ![运行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
注意，在此示例中，正在运行的方案是 AlwaysOn 和 UserReplicator。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>停止捕获集中日志记录服务日志
<a name="stop"> </a>

您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。 通常情况下，没有很多情况下，您将需要停止日志记录会话。 例如，无需先停止日志记录就可以搜索日志和更改配置。 如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。 有关详细信息，请参阅[Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。
  
> [!NOTE]
> 在确定了可以在给定部署、池或计算机上运行哪些方案后，您需要记住，在**每台计算机**上只能运行两个方案：AlwaysOn 和一个自定义方案。 如果您要记录某个池上的活动，应将一个池视为单一实体。 在大多数情况下，在池中的每台计算机上运行不同方案没有意义。 了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。 例如，如果您考虑 UserReplicator 方案，会有极小值边缘池边缘服务器上运行 UserReplicator。 
  
在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。尽管 AlwaysOn 方案会收集各类提供商的信息，在多种应用下均意义显著，但具体方案可能只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，那么您就可能存在问题、没有使用价值的数据，最终效果与根本没有运行该方案时无异。
  
若要通过 Skype 业务服务器管理外壳程序控制的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色成员包含这两个组之一。 若要返回所有已分配此 cmdlet 的 RBAC 角色的列表 （包括您自己创建的任何自定义的 RBAC 角色），请为业务服务器管理外壳程序或 Windows PowerShell 提示从 Skype 运行下面的命令：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>若要停止当前正在运行的集中式日志记录服务会话

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 查询集中式日志记录服务以查明哪些方案当前运行，通过键入以下：
    
  ```
  Show-CsClsLogging
  ```

  ![调用 Show-CsCl 后的 Windows PowerShell 控制台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
  Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。 有关详细信息，请参阅[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)。
    
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
    > 在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。 您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。 有关详细信息，请参阅[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)。 
  
作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负载故障排除过程中执行该任务。
## <a name="see-also"></a>另请参阅
<a name="stop"> </a>

#### 

[企业 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)

