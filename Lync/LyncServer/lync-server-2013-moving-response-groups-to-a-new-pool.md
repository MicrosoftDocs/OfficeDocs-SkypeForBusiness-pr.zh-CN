---
title: 'Lync Server 2013: 将响应组移动到新池'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>将响应组移动到 Lync Server 2013 中的新池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

Lync Server 2013 引入了新 cmdlet 支持, 用于将响应组从一个池移动到另一个池, 即使完全限定的域名 (FQDN) 不同也是如此。

使用以下过程中的步骤将响应组从一个前端池移动到另一个具有不同 FQDN 的前端池。

<div>


> [!NOTE]  
> 在共存环境中, 只能在 Lync Server 2013&nbsp;前端池之间移动响应组。



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>将响应组移动到具有不同 FQDN 的池

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  导出源池中的响应组。 在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    若要在导出期间从源池中删除响应组, 请包括-RemoveExportedConfiguration 参数。 例如：
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  将响应组导入目标池, 并将目标池分配为新所有者。 在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    如果你还希望将 "响应组" 应用程序级别的设置从源池中复制到目标池, 请包括-ReplaceExistingRgsSettings 参数。 你只能针对每个池定义一组应用程序级别设置。 如果将应用程序级别的设置从源池复制到目标池, 源池中的设置将替换目标池的设置。 如果不从源池中复制应用程序级别的设置, 则目标池中的现有设置将应用于导入的响应组。
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > 应用程序级设置包括默认的音乐保留配置、默认的音乐保留音频文件、代理 ringback 宽限期和调用上下文配置。 若要查看这些配置设置, 请运行<STRONG>CsRgsConfiguration</STRONG> cmdlet。 有关此 cmdlet 的详细信息, 请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">CsRgsConfiguration</A>。

    
    </div>

4.  通过执行以下操作来验证导入是否成功: 显示导入的响应组配置:
    
      - 验证导入了所有工作流。 在命令行中键入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否已导入所有队列。 在命令行中键入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否已导入所有代理组。 在命令行中键入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否已导入所有营业时间。 在命令行中键入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - 验证是否已导入所有假日集。 在命令行中键入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  通过将呼叫放到其中一个响应组并验证是否正确处理了呼叫, 验证导入是否成功。

6.  请求代理是正式代理组的成员, 以便登录到目标池中的代理组。

7.  如果以前没有从源池中删除响应组, 请从源池中删除响应组。 在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

