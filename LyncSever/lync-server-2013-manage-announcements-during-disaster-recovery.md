---
title: Lync Server 2013：灾难恢复期间管理通知
TOCTitle: 灾难恢复期间管理通知
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49888594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中灾难恢复期间管理通知

 

_**上一次修改主题：** 2013-02-23_

Lync Server 2013 支持在中断期间对未分配号码的呼叫的通知。在中断期间还原通知功能是可选的。如果您选择在中断期间还原，则需要在备份池中重新创建通知配置。本节介绍在灾难恢复过程中选择还原通知时需要执行的操作。

本节适用于使用 通知应用程序的未分配号码范围。它不适用于使用 Exchange 统一消息 (UM) 自动助理的未分配号码范围。

## 在中断之前

无论您是否在中断期间选择使用通知，都应采用为 通知应用程序配置的任何自定义音频文件的单独副本。自定义通知不会作为 Lync Server 灾难恢复过程的一部分进行备份。如果您未采用这些文件的单独备份，并且上载到服务器或池的文件被损毁、损坏或擦除，则这些文件将会丢失。

如果您没有自定义音频文件的备份副本，并且原始音频文件不再可用，则可以通过在文件存储中查找最初在其中导入文件的服务器或池，来找到为 通知应用程序配置的音频文件。您可以从文件存储中复制为 通知应用程序配置的所有音频文件。

**从文件存储中复制音频文件**

1.  在该命令行处，运行：
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    例如：
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    其中，X-ApplicationServer-X 指的是池的应用程序服务器的服务 ID（例如，1-ApplicationServer-1"）


## 在中断期间

要在中断期间使用 通知应用程序，您需要通过执行本节中所述的任务，在备份池中重新创建通知配置。

> [!NOTE]  
> 建议在故障转移到备份池之后再执行这些任务，因为一执行步骤 2，备份池就会拥有未分配号码范围。



> [!NOTE]  
> 对于使用 Exchange UM 自动助理电话号码的号码范围，不需要这些步骤。



**在备份池中重新创建通知配置**

1.  通过执行以下操作重新创建在主池和备份池中部署的通知：
    
    1.  通过使用 **Import-CsAnnouncementFile** cmdlet 并为备份池指定 Parent 参数，将主池中使用的任何音频文件导入到备份池。
    
    2.  通过使用 **New-CsAnnouncement** cmdlet 并为备份池指定 Parent 参数，重新创建每个通知。
    
    > [!NOTE]  
    > 有关使用这些参数在备份池中创建通知的详细信息，请参阅 <a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</a>。
    


2.  在备份池中重新创建所有通知之后，将使用主池中通知的所有未分配号码范围重定向到备份池中重新创建的通知。
    
    针对使用主池中通知的每个未分配号码范围，运行以下内容：
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

## 中断之后

在主池可用的情况下，您需要将由于中断发生更改的未分配号码范围重定向到主池。

> [!NOTE]  
> 对于使用 Exchange UM 自动助理电话号码的号码范围，不需要这些步骤。



**还原主池中的通知**

1.  如果必须在恢复过程中重建主池，则需要通过导入音频文件并创建通知，来在主池中重新创建通知，这与在备份池中所执行的操作一样，所不同的是您需要为主池指定 Parent 参数。有关详细信息，请参阅本主题前面的“在中断期间”。

2.  针对由于中断发生更改的每个未分配号码范围，运行以下内容：
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  也可以选择删除在备份池中重新创建的通知。获取备份池 通知应用程序的通知列表。在命令行中运行：
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例如：
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    在结果列表中，查找要删除的通知并复制 GUID。针对要删除的每个通知，运行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


