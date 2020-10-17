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
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>了解 Lync Server 2013 中的集中日志记录服务配置设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

集中日志记录服务配置为定义要收集的日志记录服务、它的收集方式、收集位置以及日志设置。 您可以全局定义这些设置 (即整个部署) 或网站 (即部署) 中的命名网站。 您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>显示当前的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > 您可以缩小或扩展由定义 <CODE>-Identity</CODE> 和作用域（例如 "site： Redmond"）返回的配置设置的范围，以仅返回网站 Redmond 的 new-csclsconfiguration。 如果您需要有关配置的给定部分的详细信息，您可以通过管道将输出传送到另一个 Windows PowerShell cmdlet。 例如，若要获取有关站点 "Redmond" 的配置中定义的方案的详细信息，请键入： <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![New-csclsconfiguration 中的示例输出。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "New-csclsconfiguration 中的示例输出。")
    
    Cmdlet 中的结果显示集中日志记录服务的当前配置。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>配置设置</th>
    <th>说明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>标识</strong></p></td>
    <td><p>标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>为此配置定义的所有方案的列表。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>为此配置定义的搜索词。 Office 365 或 Microsoft 365，不是本地部署。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。 在此上下文中，网站是在拓扑生成器中定义的网站。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>地区</strong></p></td>
    <td><p>定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>定义了在计算机上写入日志文件的位置的路径。CLSAgent 将写入日志文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>搜索跟踪消息格式文件的位置。跟踪消息格式文件用于将二进制文件转换为用户可读的格式。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>已定义为保留缓存文件的最长时间（以天为单位）。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>已定义为可由缓存文件使用的磁盘空间的百分比。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>在 60 秒内可超出 ComponentThrottleLimit 的次数。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>允许运行的 CLSAgent 的最低版本。 此元素适用于 Office 365 或 Microsoft 365。</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[新 New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

