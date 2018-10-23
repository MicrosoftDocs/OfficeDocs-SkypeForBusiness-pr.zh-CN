---
title: 将响应组移至新池
TOCTitle: 将响应组移至新池
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205298(v=OCS.15)
ms:contentKeyID: 49314427
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将响应组移至新池

 

_**上一次修改主题：** 2012-11-01_

Lync Server 2013 引入了新的 new cmdlet 支持，用于将响应组从一个池移动到另一个池，即使完全限定域名 (FQDN) 不同时仍可移动。

使用以下过程中的步骤将响应组从一个前端池移动到另一个具有不同 FQDN 的前端池。

> [!NOTE]  
> 在共存环境中，您只能在 Lync Server 2013前端池之间移动响应组。



## 将响应组移动到具有不同 FQDN 的池

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  导出源池中的响应组。在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    若要在导出期间删除源池中的响应组，请包括 –RemoveExportedConfiguration 参数。例如：
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  将响应组导入目标池中，并将目标池作为新的所有者分配。在命令行中键入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    如果还想将响应组应用程序级设置从源池复制到目标池，请包含 –ReplaceExistingSettings 参数。每个池只能定义一组应用程序级设置。如果将应用程序级设置从源池复制到目标池，源池的设置将替换目标池的设置。如果未复制源池的应用程序级设置，目标池的现有设置将应用于导入的响应组。
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    
    > [!NOTE]  
    > 应用程序级设置包括默认保持音乐配置、默认保持音乐音频文件、代理回拨宽限期以及呼叫上下文配置。要查看这些配置，请运行 <strong>Get-CsRgsConfiguration</strong> cmdlet。有关此 cmdlet 的详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</a>。
    


4.  通过执行以下操作以显示导入的响应组配置来验证导入是否成功：
    
      - 验证是否所有工作流均已导入。在命令行中键入以下命令：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否所有队列均已导入。在命令行中键入以下命令：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否所有代理组均已导入。在命令行中键入以下命令：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 验证是否所有工作时间均已导入。在命令行中键入以下命令：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - 验证是否所有假日集均已导入。在命令行中键入以下命令：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  通过向某个响应组发起呼叫并确认已正确处理呼叫来确定已成功导入。

6.  请求作为正式代理组的成员的代理登录到目标池中其自己的代理组。

7.  如果您之前未从源池中删除响应组，则从源池中删除响应组。在命令行中键入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

