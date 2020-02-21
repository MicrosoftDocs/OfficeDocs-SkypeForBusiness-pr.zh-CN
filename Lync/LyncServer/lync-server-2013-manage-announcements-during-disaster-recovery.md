---
title: Lync Server 2013：在灾难恢复期间管理通知
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
ms.openlocfilehash: 164c58859a6e92abfbb50b79c12b587c3b65c1a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="c0d3b-102">在 Lync Server 2013 中管理灾难恢复期间的通知</span><span class="sxs-lookup"><span data-stu-id="c0d3b-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d3b-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c0d3b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c0d3b-104">Lync Server 2013 支持在中断期间呼叫未分配号码的通知。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="c0d3b-105">在中断期间还原通知功能是可选的。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="c0d3b-106">如果您选择在中断期间还原，则需要在备份池中重新创建通知配置。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="c0d3b-107">本节介绍在灾难恢复过程中选择还原通知时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="c0d3b-108">本部分适用于使用通知应用程序的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="c0d3b-109">它不适用于使用 Exchange 统一消息 (UM) 自动助理的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="c0d3b-110">在中断之前</span><span class="sxs-lookup"><span data-stu-id="c0d3b-110">Before an Outage</span></span>

<span data-ttu-id="c0d3b-111">无论您是否选择在中断期间使用通知，您都应对您为通知应用程序配置的任何自定义音频文件进行单独备份。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="c0d3b-112">自定义通知不会作为 Lync Server 灾难恢复过程的一部分进行备份。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="c0d3b-113">如果您未采用这些文件的单独备份，并且上载到服务器或池的文件被损毁、损坏或擦除，则这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="c0d3b-114">如果您没有自定义的音频文件的备份副本，并且原始音频文件不再可用，则可以通过在您最初使用的服务器或池的文件存储中查找为通知应用程序配置的音频文件。导入了文件。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="c0d3b-115">您可以从文件存储中复制为通知应用程序配置的所有音频文件。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="c0d3b-116">**从文件存储中复制音频文件**</span><span class="sxs-lookup"><span data-stu-id="c0d3b-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="c0d3b-117">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="c0d3b-118">例如：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="c0d3b-119">其中，X-ApplicationServer-X 指的是池的应用程序服务器的服务 ID（例如，1-ApplicationServer-1"）</span><span class="sxs-lookup"><span data-stu-id="c0d3b-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="c0d3b-120">在中断期间</span><span class="sxs-lookup"><span data-stu-id="c0d3b-120">During an Outage</span></span>

<span data-ttu-id="c0d3b-121">若要在中断期间使用通知应用程序，您需要执行本节中所述的任务，在备份池中重新创建通知配置。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0d3b-122">建议在故障转移到备份池之后再执行这些任务，因为一执行步骤 2，备份池就会拥有未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c0d3b-123">对于使用 Exchange UM 自动助理电话号码的号码范围，不需要这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="c0d3b-124">**在备份池中重新创建通知配置**</span><span class="sxs-lookup"><span data-stu-id="c0d3b-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="c0d3b-125">通过执行以下操作重新创建在主池和备份池中部署的通知：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="c0d3b-126">通过使用 **Import-CsAnnouncementFile** cmdlet 并为备份池指定 Parent 参数，将主池中使用的任何音频文件导入到备份池。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="c0d3b-127">通过使用 **New-CsAnnouncement** cmdlet 并为备份池指定 Parent 参数，重新创建每个通知。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0d3b-128">有关使用这些参数在备份池中创建通知的详细信息，请参阅<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</A>。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="c0d3b-129">在备份池中重新创建所有通知之后，将使用主池中通知的所有未分配号码范围重定向到备份池中重新创建的通知。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="c0d3b-130">针对使用主池中通知的每个未分配号码范围，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="c0d3b-131">中断之后</span><span class="sxs-lookup"><span data-stu-id="c0d3b-131">After the Outage</span></span>

<span data-ttu-id="c0d3b-132">在主池可用的情况下，您需要将由于中断发生更改的未分配号码范围重定向到主池。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0d3b-133">对于使用 Exchange UM 自动助理电话号码的号码范围，不需要这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="c0d3b-134">**在主池中还原通知**</span><span class="sxs-lookup"><span data-stu-id="c0d3b-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="c0d3b-p105">如果必须在恢复过程中重建主池，则需要通过导入音频文件并创建通知，来在主池中重新创建通知，这与在备份池中所执行的操作一样，所不同的是您需要为主池指定 Parent 参数。有关详细信息，请参阅本主题前面的“在中断期间”。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="c0d3b-137">针对由于中断发生更改的每个未分配号码范围，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="c0d3b-138">也可以选择删除在备份池中重新创建的通知。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="c0d3b-139">获取备份池通知应用程序的通知列表。</span><span class="sxs-lookup"><span data-stu-id="c0d3b-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="c0d3b-140">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="c0d3b-141">例如：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="c0d3b-p107">在结果列表中，查找要删除的通知并复制 GUID。针对要删除的每个通知，运行：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="c0d3b-144">例如：</span><span class="sxs-lookup"><span data-stu-id="c0d3b-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

