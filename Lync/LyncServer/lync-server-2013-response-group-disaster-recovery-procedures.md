---
title: Lync Server 2013 响应组灾难恢复过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Lync Server 2013 中的响应组灾难恢复过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

在灾难恢复的故障转移阶段, 响应组位于多个池中: 在主池 (不可用) 和备份池中。 两个池中的响应组具有相同的名称和相同的所有者 (主池), 但它们具有不同的父池。 在这段时间内, 响应组 cmdlet 的工作方式略有不同。 请确保使用以下过程中指定的参数。 有关 cmdlet 在故障转移阶段的工作原理的详细信息, 请参阅 NextHop 博客文章 "Lync Server 2013: 在[http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)灾难恢复期间恢复响应组"。 此博客文章还适用于 Lync Server 2013 的已发布版本。

使用以下过程中的步骤为 Lync Server 响应组服务准备和执行灾难恢复。

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>故障转移和故障回复响应组

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  定期执行备份。 在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  在中断期间, 在故障转移到备份池后, 将响应组导入到备份池。 在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    如果要将备份池中的应用程序级设置替换为主池中的设置, 请包括-ReplaceExistingSettings 参数。 例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > 如果不替换备份池中的设置, 并且无法恢复主池, 则主池设置将丢失。 有关详细信息, 请参阅<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中规划响应组灾难恢复</A>。

    
    </div>

4.  通过显示导入的响应组来验证导入是否成功。 导入的响应组仍由主池拥有。 请执行下列操作：
    
      - 显示由主池拥有的备份池中的所有工作流, 并验证是否包含所有主池工作流。 在命令行中键入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - 显示由主池拥有的备份池中的所有队列, 并验证是否包含所有主池队列。 在命令行中键入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示由主池拥有的备份池中的所有代理组, 并验证是否包含所有主池代理组。 在命令行中键入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示由主池拥有的备份池中的所有工作时间, 并验证是否包括所有主池的工作时间。 在命令行中键入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示由主池拥有的备份池中的所有假日集, 并验证是否包含所有主池假日集。 在命令行中键入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    或者, 你可以显示备份池中的所有响应组, 包括由主池拥有的所有响应组以及由备份池拥有的所有响应组, 方法是使用– ShowAll 参数而不是-Owner 参数。 例如：
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > 你必须使用– ShowAll 参数或– Owner 参数。 如果不使用这两个参数中的任何一个, 则导入到备份池的响应组将不会在 cmdlet 返回的结果中列出。

    
    </div>

5.  通过在导入的响应组中拨打电话并验证是否正确处理了呼叫, 验证导入是否成功。

6.  请求代理是正式代理组的成员, 以登录到备份池中的代理组。

7.  照常管理和修改导入的响应组。
    
    <div>
    

    > [!IMPORTANT]  
    > 当响应组位于备份池中时, 你需要使用 Lync Server Management Shell 管理它们。 无法使用 Lync Server "控制面板" 管理导入到备份池中的响应组。

    
    </div>

8.  在还原主池并完成故障回复后, 请导出已导入到备份池中的主要池响应组。 在命令行中键入：
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  将响应组导入回主池。 在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > 如果你在恢复期间重新生成池, 而不是使用相同或不同的完全限定的域名 (FQDN), 则需要使用-OverwriteOwner 参数。 根据经验法则, 将响应组导入到主池时, 始终可以使用– OverwriteOwner 参数。

    
    </div>
    
    如果你部署了新池 (具有相同或不同的 FQDN) 来替换主池, 并且希望使用新池的备份池中的应用程序级别设置, 请包含-ReplaceExistingSettings 参数。 在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您不想将新池的应用程序级设置和默认的音乐保留音频文件替换为具有备份池中的设置, 则新池将使用默认的应用程序级设置。

    
    </div>

10. 通过显示导入的响应组配置来验证是否已成功导入到主池。 请执行下列操作：
    
      - 显示主池中的所有工作流, 并验证是否包含所有导入的工作流。 在命令行中键入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - 显示主池中的所有队列, 并验证是否包含所有导入的队列。 在命令行中键入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有代理组, 并验证是否包含所有导入的代理组。 在命令行中键入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有工作时间, 并验证是否包括所有导入的公司工时。 在命令行中键入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有假日集, 并验证是否包含所有导入的假日集。 在命令行中键入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. 通过在导入的响应组中拨打电话并验证是否正确处理了呼叫, 验证导入是否成功。

12. (可选) 从备份池中删除主池拥有的响应组。 在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > 此步骤将使用导出的配置创建一个新文件, 然后将其从备份池中删除。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

