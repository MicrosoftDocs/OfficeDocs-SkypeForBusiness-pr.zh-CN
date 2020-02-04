---
title: Lync Server 2013：灾难恢复期间管理通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中灾难恢复期间管理通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

Lync Server 2013 支持在中断期间调用未分配的号码的公告。 在中断期间还原发布功能是可选的。 如果你选择在中断期间还原通知，则需要在备份池中重新创建你的通知配置。 本部分介绍了在灾难恢复期间选择还原公告时需要执行的操作。

本部分适用于使用公告应用程序的未分配号码范围。 本部分不适用于使用 Exchange 统一消息（UM）自动助理的未分配号码范围。

<div>

## <a name="before-an-outage"></a>停机前

无论您是否选择在中断期间使用公告，您都应该对您为公告应用程序配置的任何自定义音频文件执行单独的备份。 Lync Server 灾难恢复过程中不会备份自定义公告。 如果未对文件进行单独备份，并且上载到服务器或池中的文件已损坏、损坏或删除，则文件将丢失。

如果你没有自定义音频文件的备份副本，并且原始音频文件不再可用，你可以通过在你原来的服务器或池的文件存储中查找为公告应用程序配置的音频文件已导入文件。 你可以从文件存储中复制为公告应用程序配置的所有音频文件。

**从文件存储中复制音频文件**

1.  在命令行中运行：
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    例如：
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    其中 X-ApplicationServer 指池的应用服务器的服务 ID （例如，1-ApplicationServer-1）


</div>

<div>

## <a name="during-an-outage"></a>在中断期间

若要在中断期间使用公告应用程序，您需要执行本部分中所述的任务，在备份池中重新创建通知配置。

<div>


> [!NOTE]  
> 我们建议你在故障转移到备份池后执行这些任务，因为执行第2步后，备份池将获得未分配的数字范围的所有权。



</div>

<div>


> [!NOTE]  
> 对于使用 Exchange UM 自动助理电话号码的号码范围，不需要执行这些步骤。



</div>

**在备份池中重新创建公告配置**

1.  通过执行下列操作，重新创建在备份池中的主池中部署的公告：
    
    1.  通过使用**CsAnnouncementFile** cmdlet 并指定父参数的备份池，将主池中使用的任何音频文件导入到备份池中。
    
    2.  通过使用**CsAnnouncement** cmdlet 并指定父参数的备份池，重新创建每个公告。
    
    <div>
    

    > [!NOTE]  
    > 有关使用这些参数在备份池中创建公告的详细信息，请参阅<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建公告</A>。

    
    </div>

2.  在备份池中重新创建所有公告后，将主池中的 "公告" 中的所有未分配的号码范围重定向到 "备份" 池中的 "重新创建的公告"。
    
    对于使用主池中的公告的每个未分配号码范围，请运行以下操作：
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>停机后

当主池可用时，你需要将已更改的未分配数字范围重定向回主池。

<div>


> [!NOTE]  
> 对于使用 Exchange UM 自动助理电话号码的号码范围，不需要执行这些步骤。



</div>

**在主池中还原公告**

1.  如果在恢复期间必须重新生成主池，则需要在主池中重新创建公告，方法是导入音频文件并创建通知，就像在备份池中指定主池一样。参数. 有关详细信息，请参阅本主题前面部分的 "停机期间"。

2.  对于您为中断而更改的每个未分配的号码范围，请运行以下操作：
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  （可选）删除在备份池中重新创建的公告。 获取备份池公告应用程序的公告列表。 在命令行中运行：
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例如：
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    在生成的列表中，找到要删除和复制 Guid 的公告。 对于要删除的每个通知，请运行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

