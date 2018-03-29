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
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="da973-103">在 Skype for Business Server 2015 中启动或停止捕获 CLS 日志</span><span class="sxs-lookup"><span data-stu-id="da973-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="da973-104">**摘要：**了解如何启动或停止的业务服务器 2015 Skype 在集中式日志记录服务日志捕获会话。</span><span class="sxs-lookup"><span data-stu-id="da973-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="da973-105">要捕获跟踪日志使用集中式日志记录服务，则发出一个命令以开始记录一个或多个计算机和池上。</span><span class="sxs-lookup"><span data-stu-id="da973-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="da973-106">此外颁发参数，以定义哪些计算机或池，什么样的方案 （如 AlwaysOn、 预定义的另一种情况或您已经创建了一个方案），运行什么 Skype 业务服务器组件 （例如，S4，SipStack） 跟踪。</span><span class="sxs-lookup"><span data-stu-id="da973-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="da973-107">若要捕获正确的信息，您必须使用正确的方案收集问题相关信息。</span><span class="sxs-lookup"><span data-stu-id="da973-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="da973-108">在集中式日志记录服务中，一个方案是启用日志记录基于集合的服务器组件、 日志记录级别和标志，这更有效且比无需在每台服务器上定义这些元素非常有用的概念。</span><span class="sxs-lookup"><span data-stu-id="da973-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="da973-109">您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。</span><span class="sxs-lookup"><span data-stu-id="da973-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="da973-p103">默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。</span><span class="sxs-lookup"><span data-stu-id="da973-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="da973-117">集中式日志记录服务提供了两种方式发出命令。</span><span class="sxs-lookup"><span data-stu-id="da973-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="da973-118">许多主题已被重点集中在使用 Windows PowerShell 通过 Skype 业务服务器管理外壳。</span><span class="sxs-lookup"><span data-stu-id="da973-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="da973-119">使用多个复杂的配置和命令的能力倾向于集中式日志记录服务使用的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="da973-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="da973-120">由于 Windows PowerShell 通过 Skype 的业务服务器管理外壳几乎到处都有为 Skype 业务服务器中的所有函数，讨论了只有 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="da973-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="da973-121">若要使用 Windows PowerShell 使用基本命令运行开始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="da973-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="da973-122">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="da973-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="da973-123">通过键入以下使用集中式日志记录服务启动日志记录方案：</span><span class="sxs-lookup"><span data-stu-id="da973-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
  ```
  Start-CsClsLogging -Scenario <name of scenario>
  ```

    <span data-ttu-id="da973-124">例如，要启动 **AlwaysOn** 方案，可键入：</span><span class="sxs-lookup"><span data-stu-id="da973-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
  ```
  Start-CsClsLogging -Scenario AlwaysOn
  ```

    > [!NOTE]
    > <span data-ttu-id="da973-125">AlwaysOn 方案没有默认持续时间。</span><span class="sxs-lookup"><span data-stu-id="da973-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="da973-126">这种情况下将运行直到其显式停止使用**Stop CsClsLogging** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da973-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="da973-127">有关详细信息，请参阅[Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="da973-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="da973-128">对于所有其他方案，默认持续时间为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="da973-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="da973-129">按 Enter 运行命令。</span><span class="sxs-lookup"><span data-stu-id="da973-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="da973-130">可能需要一小段时间（30 到 60 秒）命令才运行完毕，并接收从您的部署中的计算机返回的状态。</span><span class="sxs-lookup"><span data-stu-id="da973-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![运行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="da973-132">要开始另一种情况，使用**开始 CsClsLogging** cmdlet 与其他方案的名称，如下所示 （例如，方案**的身份验证**） 运行：</span><span class="sxs-lookup"><span data-stu-id="da973-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
  ```
  Start-CsClsLogging -Scenario Authentication
  ```

    > [!IMPORTANT]
    > <span data-ttu-id="da973-p106">在任意时间可以在任何给定计算机上运行总共两个方案。如果命令是全局范围的，则部署中的所有计算机将运行方案。要启动第三个方案，必须在您要运行新方案的计算机、池、站点或全局范围上停止日志记录。如果已启动全局范围，则可以在一个或多个计算机和池上停止一种方案或同时停止两种方案的日志记录。</span><span class="sxs-lookup"><span data-stu-id="da973-p106">You can have a total of two scenarios running on any given computer at any time. If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios. To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on. If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="da973-137">若要使用 Windows PowerShell 使用高级命令运行开始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="da973-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="da973-138">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="da973-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="da973-139">也可以使用其他参数来管理日志记录命令。</span><span class="sxs-lookup"><span data-stu-id="da973-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="da973-140">您可以使用的持续时间来调整该方案要运行的时间长度。</span><span class="sxs-lookup"><span data-stu-id="da973-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="da973-141">您还可以定义的计算机，计算机的完全合格的域名 (Fqdn) 用一个逗号分隔的列表，或者-池，一个逗号分隔列表要运行登录的池的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="da973-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="da973-142">首先，UserReplicator 方案的日志记录会话池"pool01.contoso.net"上。</span><span class="sxs-lookup"><span data-stu-id="da973-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="da973-143">您还定义日志记录会话持续时间为 8 小时。</span><span class="sxs-lookup"><span data-stu-id="da973-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="da973-144">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="da973-144">To do this, type:</span></span>
    
  ```
  Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"

  ```

    <span data-ttu-id="da973-145">此方案成功执行后将返回类似如下的结果：</span><span class="sxs-lookup"><span data-stu-id="da973-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![运行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="da973-147">注意，在此示例中，正在运行的方案是 AlwaysOn 和 UserReplicator。</span><span class="sxs-lookup"><span data-stu-id="da973-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="da973-148">停止捕获集中日志记录服务日志</span><span class="sxs-lookup"><span data-stu-id="da973-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="da973-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="da973-149"></span></span>

<span data-ttu-id="da973-150">您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="da973-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="da973-151">通常情况下，没有很多情况下，您将需要停止日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="da973-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="da973-152">例如，无需先停止日志记录就可以搜索日志和更改配置。</span><span class="sxs-lookup"><span data-stu-id="da973-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="da973-153">如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="da973-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="da973-154">有关详细信息，请参阅[Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="da973-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da973-155">在确定了可以在给定部署、池或计算机上运行哪些方案后，您需要记住，在**每台计算机**上只能运行两个方案：AlwaysOn 和一个自定义方案。</span><span class="sxs-lookup"><span data-stu-id="da973-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="da973-156">如果您要记录某个池上的活动，应将一个池视为单一实体。</span><span class="sxs-lookup"><span data-stu-id="da973-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="da973-157">在大多数情况下，在池中的每台计算机上运行不同方案没有意义。</span><span class="sxs-lookup"><span data-stu-id="da973-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="da973-158">了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。</span><span class="sxs-lookup"><span data-stu-id="da973-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="da973-159">例如，如果您考虑 UserReplicator 方案，会有极小值边缘池边缘服务器上运行 UserReplicator。</span><span class="sxs-lookup"><span data-stu-id="da973-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="da973-p111">在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。尽管 AlwaysOn 方案会收集各类提供商的信息，在多种应用下均意义显著，但具体方案可能只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，那么您就可能存在问题、没有使用价值的数据，最终效果与根本没有运行该方案时无异。</span><span class="sxs-lookup"><span data-stu-id="da973-p111">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="da973-164">若要通过 Skype 业务服务器管理外壳程序控制的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色成员包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="da973-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="da973-165">若要返回所有已分配此 cmdlet 的 RBAC 角色的列表 （包括您自己创建的任何自定义的 RBAC 角色），请为业务服务器管理外壳程序或 Windows PowerShell 提示从 Skype 运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="da973-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="da973-166">例如：</span><span class="sxs-lookup"><span data-stu-id="da973-166">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="da973-167">若要停止当前正在运行的集中式日志记录服务会话</span><span class="sxs-lookup"><span data-stu-id="da973-167">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="da973-168">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="da973-168">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="da973-169">查询集中式日志记录服务以查明哪些方案当前运行，通过键入以下：</span><span class="sxs-lookup"><span data-stu-id="da973-169">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
  ```
  Show-CsClsLogging
  ```

  ![调用 Show-CsCl 后的 Windows PowerShell 控制台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
  <span data-ttu-id="da973-171">Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。</span><span class="sxs-lookup"><span data-stu-id="da973-171">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="da973-172">有关详细信息，请参阅[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="da973-172">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="da973-173">若要使用特定方案停止当前正在运行的日志记录会话，请键入：</span><span class="sxs-lookup"><span data-stu-id="da973-173">To stop a currently running logging session with a specific scenario, type:</span></span>
    
  ```
  Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
  ```
  <span data-ttu-id="da973-174">例如：</span><span class="sxs-lookup"><span data-stu-id="da973-174">For example:</span></span>
    
  ```
  Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
  ```

  <span data-ttu-id="da973-175">此命令将在 pool01.contoso.net 上使用 UserReplicatior 方案停止日志记录。</span><span class="sxs-lookup"><span data-stu-id="da973-175">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da973-176">在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。</span><span class="sxs-lookup"><span data-stu-id="da973-176">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="da973-177">您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。</span><span class="sxs-lookup"><span data-stu-id="da973-177">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="da973-178">有关详细信息，请参阅[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="da973-178">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="da973-p115">作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负载故障排除过程中执行该任务。</span><span class="sxs-lookup"><span data-stu-id="da973-p115">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="da973-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da973-182">See also</span></span>
<span data-ttu-id="da973-183"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="da973-183"></span></span>

#### 

[<span data-ttu-id="da973-184">企业 2015年的 Skype 在集中式日志记录服务</span><span class="sxs-lookup"><span data-stu-id="da973-184">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

