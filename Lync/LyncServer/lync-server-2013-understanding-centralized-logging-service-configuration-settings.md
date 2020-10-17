---
title: 了解集中日志记录服务配置设置
description: 了解集中日志记录服务配置设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f99dbffe15c4b3f0dc13d231c3a2732a8554397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542398"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e079f-103">了解 Lync Server 2013 中的集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="e079f-103">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e079f-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e079f-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e079f-105">集中日志记录服务配置为定义要收集的日志记录服务、它的收集方式、收集位置以及日志设置。</span><span class="sxs-lookup"><span data-stu-id="e079f-105">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="e079f-106">您可以全局定义这些设置 (即整个部署) 或网站 (即部署) 中的命名网站。</span><span class="sxs-lookup"><span data-stu-id="e079f-106">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="e079f-107">您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。</span><span class="sxs-lookup"><span data-stu-id="e079f-107">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e079f-108">显示当前的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="e079f-108">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e079f-109">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e079f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e079f-110">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="e079f-110">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="e079f-111">您可以缩小或扩展由定义 <CODE>-Identity</CODE> 和作用域（例如 "site： Redmond"）返回的配置设置的范围，以仅返回网站 Redmond 的 new-csclsconfiguration。</span><span class="sxs-lookup"><span data-stu-id="e079f-111">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="e079f-112">如果您需要有关配置的给定部分的详细信息，您可以通过管道将输出传送到另一个 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e079f-112">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="e079f-113">例如，若要获取有关站点 "Redmond" 的配置中定义的方案的详细信息，请键入： <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="e079f-113">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="e079f-114">![New-csclsconfiguration 中的示例输出。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "New-csclsconfiguration 中的示例输出。")</span><span class="sxs-lookup"><span data-stu-id="e079f-114">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="e079f-115">Cmdlet 中的结果显示集中日志记录服务的当前配置。</span><span class="sxs-lookup"><span data-stu-id="e079f-115">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e079f-116">配置设置</span><span class="sxs-lookup"><span data-stu-id="e079f-116">Configuration Setting</span></span></th>
    <th><span data-ttu-id="e079f-117">说明</span><span class="sxs-lookup"><span data-stu-id="e079f-117">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-118"><strong>标识</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-118"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p103">标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。</span><span class="sxs-lookup"><span data-stu-id="e079f-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-121"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-121"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-122">为此配置定义的所有方案的列表。</span><span class="sxs-lookup"><span data-stu-id="e079f-122">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-123"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-123"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-124">为此配置定义的搜索词。</span><span class="sxs-lookup"><span data-stu-id="e079f-124">Defined search terms for the configuration.</span></span> <span data-ttu-id="e079f-125">Office 365 或 Microsoft 365，不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="e079f-125">Office 365 or Microsoft 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-126"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-126"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-127">定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。</span><span class="sxs-lookup"><span data-stu-id="e079f-127">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="e079f-128">在此上下文中，网站是在拓扑生成器中定义的网站。</span><span class="sxs-lookup"><span data-stu-id="e079f-128">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-129"><strong>地区</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-129"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-130">定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。</span><span class="sxs-lookup"><span data-stu-id="e079f-130">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-131"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-131"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p106">定义了在计算机上写入日志文件的位置的路径。CLSAgent 将写入日志文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="e079f-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-135"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-135"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p107">该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。</span><span class="sxs-lookup"><span data-stu-id="e079f-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-138"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-138"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p108">在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。</span><span class="sxs-lookup"><span data-stu-id="e079f-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-141"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-141"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p109">搜索跟踪消息格式文件的位置。跟踪消息格式文件用于将二进制文件转换为用户可读的格式。</span><span class="sxs-lookup"><span data-stu-id="e079f-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-144"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-144"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-p110">定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。</span><span class="sxs-lookup"><span data-stu-id="e079f-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-149"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-149"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-150">您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。</span><span class="sxs-lookup"><span data-stu-id="e079f-150">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-151"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-151"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-152">已定义为保留缓存文件的最长时间（以天为单位）。</span><span class="sxs-lookup"><span data-stu-id="e079f-152">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-153"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-153"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-154">已定义为可由缓存文件使用的磁盘空间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e079f-154">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-155"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-155"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-156">已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。</span><span class="sxs-lookup"><span data-stu-id="e079f-156">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e079f-157"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-157"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-158">在 60 秒内可超出 ComponentThrottleLimit 的次数。</span><span class="sxs-lookup"><span data-stu-id="e079f-158">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e079f-159"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e079f-159"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="e079f-160">允许运行的 CLSAgent 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="e079f-160">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="e079f-161">此元素适用于 Office 365 或 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e079f-161">This element is intended for Office 365 or Microsoft 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e079f-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e079f-162">See Also</span></span>


[<span data-ttu-id="e079f-163">Lync Server 2013 中的集中日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="e079f-163">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="e079f-164">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e079f-164">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="e079f-165">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e079f-165">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="e079f-166">[新 New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e079f-166">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="e079f-167">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e079f-167">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

