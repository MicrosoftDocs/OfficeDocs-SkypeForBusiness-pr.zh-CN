---
title: 管理计算机、站点和全局集中日志记录服务配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="f9a5b-102">在 Lync Server 2013 中管理计算机、站点和全局集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9a5b-103">_**主题上次修改时间：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="f9a5b-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f9a5b-104">集中式日志记录服务可以在包含单个计算机的范围（即计算机池）所在的范围内运行（即，定义的网站（如网站 Redmond），其中包含你的部署中的计算机和池的集合，或者在全局范围内、部署中的所有计算机和池）。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="f9a5b-105">若要使用 Lync Server 命令行管理器配置集中式日志记录服务范围，你必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含以下项的自定义 RBAC 角色这两个组中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f9a5b-106">若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表（包括你自己创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="f9a5b-107">例如：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="f9a5b-108">Windows PowerShell 通过使用 CLSController 提供了更多选项和其他不可用的配置选项。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="f9a5b-109">CLSController 提供了一种快速、简洁的方法来运行命令，但仅限于可用于 CLSController 的命令集。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="f9a5b-110">Windows PowerShell 不仅限于 CLSController 的命令处理器可用的命令，并提供了更多的命令集和更丰富的选项集。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="f9a5b-111">例如，CLSController 将为你提供-计算机和-池的范围选项。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="f9a5b-112">使用 Windows PowerShell，你可以在大多数命令中指示计算机或池，并且当你定义新方案时（CLSController 具有的用户不能更改的有限数量的方案），你可以定义一个网站或全局范围。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="f9a5b-113">Windows PowerShell 的这一强大功能允许你定义网站或全局范围的方案，但将实际日志记录限制到计算机或池。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="f9a5b-114">可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="f9a5b-115">Windows PowerShell 提供了一种丰富的方法来配置和定义方案，并以一种有意义的方式重复使用这些方案来解决你的故障排除方案。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="f9a5b-116">尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="f9a5b-117">与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、网站或全局级别的管理范围，以及无法动态配置的有限命令集的许多其他限制。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="f9a5b-118">虽然 CLSController 提供快速执行的方法，但 Windows PowerShell 提供了一种方法来扩展集中式日志记录服务功能，而不是 CLSController 的可能性。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="f9a5b-p104">可以使用 –Computers 参数在 [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))、[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) 和 [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) 命令执行期间定义单个计算机的作用域。–Computers 参数接受目标计算机的以逗号分隔的完全限定域名 (FQDN) 的列表。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-p104">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter. The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f9a5b-121">还可以定义–Pools 和您要对其运行日志记录命令的以逗号分隔的池的列表。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="f9a5b-122">站点和全局范围在**新**的、**集的**和**删除**集中的日志记录服务 cmdlet 中定义。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="f9a5b-123">以下示例演示了如何设置站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f9a5b-124">显示的命令可能包含其他章节中涵盖的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="f9a5b-125">示例命令旨在演示如何使用 <STRONG>–Identity</STRONG> 参数定义作用域，还包含了其他参数来保证完整性和指定作用域。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="f9a5b-126">有关 <STRONG>Set-CsClsConfiguration</STRONG> cmdlet 的详细信息，请参阅操作文档中的 <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="f9a5b-127">检索当前集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="f9a5b-128">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-129">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="f9a5b-130">使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** cmdlet 创建新配置或更新现有配置。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="f9a5b-131">当运行 **Get-CsClsConfiguration** 时，它将显示类似于下面的屏幕快照的信息，其中，部署当前具有默认的全局配置，但未定义站点配置：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="f9a5b-132">![来自 Get-CsClsConfiguration 的示例输出。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "来自 Get-CsClsConfiguration 的示例输出。")</span><span class="sxs-lookup"><span data-stu-id="f9a5b-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="f9a5b-133">从计算机本地应用商店检索当前集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="f9a5b-134">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-135">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="f9a5b-136">使用**CsClsConfiguration**未指定任何参数的第一个示例时，该命令将引用数据的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="f9a5b-137">如果你指定参数-LocalStore，该命令将引用计算机 LocalStore，而不是中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="f9a5b-138">检索当前定义的方案的列表</span><span class="sxs-lookup"><span data-stu-id="f9a5b-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="f9a5b-139">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-140">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="f9a5b-141">例如，检索在全局作用域定义的方案：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="f9a5b-142">cmdlet **Get-CsClsConfiguration** 始终显示作为给定作用域的配置的一部分的方案。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="f9a5b-143">在大多数情况下，不会显示所有方案，而会截断它们。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="f9a5b-144">此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="f9a5b-145">使用 Windows PowerShell 更新集中日志记录服务的全局范围</span><span class="sxs-lookup"><span data-stu-id="f9a5b-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="f9a5b-146">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-147">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="f9a5b-148">例如：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="f9a5b-p109">该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="f9a5b-151">使用 Windows PowerShell 更新集中日志记录服务的网站范围</span><span class="sxs-lookup"><span data-stu-id="f9a5b-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="f9a5b-152">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-153">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="f9a5b-154">例如：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f9a5b-p110">如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="f9a5b-p111">该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="f9a5b-159">创建新的集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="f9a5b-160">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-161">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f9a5b-162">利用 New-CsClsConfiguration，可以访问大量可选配置设置。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="f9a5b-163">有关配置选项的详细信息，请参阅<A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">CsClsConfiguration</A>和<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">了解 Lync Server 2013 中的集中日志记录服务配置设置</A>。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="f9a5b-164">例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="f9a5b-165">你应该仔细规划新配置的创建以及如何为集中式日志记录服务定义新属性。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="f9a5b-166">您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="f9a5b-167">您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="f9a5b-168">删除现有的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="f9a5b-169">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9a5b-170">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="f9a5b-171">例如，若要删除你创建的集中日志记录服务配置以增加日志文件滚动更新时间，请增加滚动更新日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9a5b-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f9a5b-172">这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="f9a5b-173">如果选择删除站点级配置，站点将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="f9a5b-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9a5b-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9a5b-174">See Also</span></span>


[<span data-ttu-id="f9a5b-175">Lync Server 2013 中的集中式日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="f9a5b-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="f9a5b-176">在 Lync Server 2013 中管理集中式日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="f9a5b-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="f9a5b-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9a5b-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="f9a5b-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9a5b-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="f9a5b-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9a5b-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="f9a5b-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9a5b-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

