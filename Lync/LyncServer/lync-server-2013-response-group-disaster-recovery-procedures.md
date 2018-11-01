---
title: Lync Server 2013 响应组灾难恢复过程
TOCTitle: 响应组灾难恢复过程
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205186(v=OCS.15)
ms:contentKeyID: 49314000
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的响应组灾难恢复过程

 

_**上一次修改主题：** 2016-12-08_

在灾难恢复的故障转移阶段内，响应组位于多个池中：主池（无法使用）和备份池。这两个池中的响应组具有相同的名称和相同的所有者（主池），但是它们具有不同的父项。在这段时间内，响应组 cmdlet 的工作方式稍微有些不同。请务必使用以下过程中指定的参数。有关 cmdlet 在故障转移阶段的工作方式的详细信息，请参阅 NextHop 博客文章“Lync Server 2013：在灾难恢复期间恢复响应组”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)。此博客文章还适用于 Lync Server 2013 的发行版。

使用以下过程中的步骤为 Lync Server 响应组服务准备和执行灾难恢复。

## 对响应组进行故障转移和故障回复

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  定期执行备份。在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  在中断期间，在故障转移到备份池后，将响应组导入备份池。在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    如果您想要将备份池中的应用程序级别设置替换为主池中的设置，请包括 –ReplaceExistingSettings 参数。例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    > [!CAUTION]
    > 如果您未替换备份池中的设置，并且无法恢复主池，则主池设置将会丢失。有关详细信息，请参阅 <a href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中规划响应组灾难恢复</a>。


4.  通过显示导入的响应组来验证导入是否成功。导入的响应组仍归主池所有。请执行以下操作：
    
      - 显示备份池中归主池所有的全部工作流，并验证是否包含所有主池工作流。在命令行中键入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - 显示备份池中归主池所有的全部队列，并验证是否包含所有主池队列。在命令行中键入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示备份池中归主池所有的全部代理组，并验证是否包含所有主池代理组。在命令行中键入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示备份池中归主池所有的全部工作时间，并验证是否包含所有主池工作时间。在命令行中键入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 显示备份池中归主池所有的全部假日集，并验证是否包含所有主池假日集。在命令行中键入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    或者，您可以使用 –ShowAll 参数而不是 –Owner 参数来显示备份池中的所有响应组，包括主池所拥有的响应组和备份池所拥有的响应组。例如：
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    > [!IMPORTANT]
    > 您必须使用 –ShowAll 参数或 –Owner 参数。如果没有使用其中任一参数，则导入到备份池的响应组不会在 cmdlet 返回的结果中列出。


5.  通过呼叫导入的响应组并验证呼叫是否正确处理来验证导入是否成功。

6.  请求属于正式代理组的成员的代理登录到其在备份池中的代理组。

7.  像往常一样管理和修改导入的响应组。
    
    > [!IMPORTANT]
    > 响应组位于备份池中时，您需要使用 Lync Server 命令行管理程序来管理它们。您不能使用 Lync Server 控制面板来管理导入到备份池的响应组。


8.  在恢复主池并完成故障回复之后，导出已导入备份池的主池响应组。在命令行中键入：
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  将响应组重新导入到主池。在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    > [!NOTE]  
	> 如果在恢复期间重建池，则无论完全限定域名 (FQDN) 相同还是不同，您都需要使用 –OverwriteOwner 参数。根据经验法则，在将响应组导回到主池时，您可以始终使用 –OverwriteOwner 参数。
    
    
    如果您部署一个新池（具有相同或不同的 FQDN）来替换主池，并且想要针对新池使用备份池中的应用程序级别设置，请包括 –ReplaceExistingSettings 参数。在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    > [!IMPORTANT]
    > 如果您不想将新池的应用程序级别设置和默认保持音乐音频文件替换为备份池中的设置，则新池将使用默认应用程序级别设置。


10. 通过显示导入的响应组配置来验证导回至主池是否成功。请执行以下操作：
    
      - 显示主池中的所有工作流，并验证是否包含所有导入的工作流。在命令行中键入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - 显示主池中的所有队列，并验证是否包含所有导入的队列。在命令行中键入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有代理组，并验证是否包含所有导入的代理组。在命令行中键入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有工作时间，并验证是否包含所有导入的工作时间。在命令行中键入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 显示主池中的所有假日集，并验证是否包含所有导入的假日集。在命令行中键入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. 通过呼叫导入的响应组并验证呼叫是否正确处理来验证导入是否成功。

12. 或者，从备份池中删除主池拥有的响应组。在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    > [!NOTE]  
	> 此步骤将使用导出的配置创建新文件，然后将该文件从备份池中删除。
    

