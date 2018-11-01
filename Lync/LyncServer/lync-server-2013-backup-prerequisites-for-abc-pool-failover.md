---
title: ABC 池故障转移的备份先决条件
TOCTitle: ABC 池故障转移的备份先决条件
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945634(v=OCS.15)
ms:contentKeyID: 52061041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ABC 池故障转移的备份先决条件

 

_**上一次修改主题：** 2013-03-26_

若要从使用 ABC 池故障转移过程中获得最大好处，您必须在灾难和故障转移发生之前执行某些备份：

  - 您必须定期使用 **Export-CsLISConfiguration** cmdlet 备份池 A 中的位置信息服务 (LIS) 配置数据。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - 您必须定期使用 **Export-CsRgsConfiguration** cmdlet 备份池 A 中的响应组配置数据。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    通常，建议您执行日常备份，但如果您要进行大量更改，那么您可能希望安排更为频繁的备份。您在发生灾难期间可能丢失的信息量取决于您的备份频率，以及更改频率和更改量。
    
    响应组应用程序只能为每个池存储一组应用程序级别设置。可通过 **Get-CsRgsConfiguration** cmdlet 访问这些设置。这些设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理回响宽限期和呼叫上下文配置。可通过使用 **ReplaceExistingSettings** 参数的 **Import-CsRgsConfiguration** cmdlet 将这些设置从一个池传输到另一个池，但此操作将覆盖目标池中的任何应用程序级别设置。
    
    > [!TIP]
    > 在单独的位置，保存已用于配置响应组应用程序的所有原始音频文件（即，任何录制或保持音乐文件）的备份副本。
    
    如果池中有已为呼叫寄存上载的任何自定义保持音乐文件，应将这些文件的副本保存在其他位置。这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，并且将在上载到池的文件毁坏、损坏或清除时丢失。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    > [!NOTE]  
    > 呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的保持音乐音频文件。可通过 <strong>Get-CsCpsConfiguration</strong> cmdlet 访问这些设置。因为呼叫寄存的灾难恢复机制依赖备份池的呼叫寄存应用程序，所以在灾难发生时不会备份或保留主池的设置。如果主池丢失，则无法恢复这些设置，并且在部署新池来替代主池时，将需要重新配置呼叫寄存设置和任何自定义的保持音乐音频文件。
    


  - 如果您配置任何通知作为未分配号码语音功能的一部分，建议您将在初始配置过程中使用的任何原始音频文件的副本保存在其他位置。如果您没有如此做，则可以在音频文件导入到的服务器或池的文件存储中获得所配置的音频文件的副本。这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，并且将在上载到池的文件毁坏、损坏或清除时丢失。若要从服务器或池的文件存储中复制用于配置未分配号码语音功能的所有音频文件，请使用：
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 如果池中有监控和存档数据库，则您应使用 SQL Server 管理工具备份它们。在 ABC 故障转移过程中，如果监控和存档数据库并置在池 A 中，则不会保留它们，因为这些数据库不是通过 Lync Server 备份服务进行备份的。

