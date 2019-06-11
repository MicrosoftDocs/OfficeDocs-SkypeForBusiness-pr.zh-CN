---
title: Lync Server 2013：灾难恢复期间管理通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="87821-102">在 Lync Server 2013 中灾难恢复期间管理通知</span><span class="sxs-lookup"><span data-stu-id="87821-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87821-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="87821-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="87821-104">Lync Server 2013 支持在中断期间调用未分配的号码的公告。</span><span class="sxs-lookup"><span data-stu-id="87821-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="87821-105">在中断期间还原发布功能是可选的。</span><span class="sxs-lookup"><span data-stu-id="87821-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="87821-106">如果你选择在中断期间还原通知, 则需要在备份池中重新创建你的通知配置。</span><span class="sxs-lookup"><span data-stu-id="87821-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="87821-107">本部分介绍了在灾难恢复期间选择还原公告时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="87821-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="87821-108">本部分适用于使用公告应用程序的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="87821-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="87821-109">本部分不适用于使用 Exchange 统一消息 (UM) 自动助理的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="87821-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="87821-110">停机前</span><span class="sxs-lookup"><span data-stu-id="87821-110">Before an Outage</span></span>

<span data-ttu-id="87821-111">无论您是否选择在中断期间使用公告, 您都应该对您为公告应用程序配置的任何自定义音频文件执行单独的备份。</span><span class="sxs-lookup"><span data-stu-id="87821-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="87821-112">Lync Server 灾难恢复过程中不会备份自定义公告。</span><span class="sxs-lookup"><span data-stu-id="87821-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="87821-113">如果未对文件进行单独备份, 并且上载到服务器或池中的文件已损坏、损坏或删除, 则文件将丢失。</span><span class="sxs-lookup"><span data-stu-id="87821-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="87821-114">如果你没有自定义音频文件的备份副本, 并且原始音频文件不再可用, 你可以通过在你原来的服务器或池的文件存储中查找为公告应用程序配置的音频文件已导入文件。</span><span class="sxs-lookup"><span data-stu-id="87821-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="87821-115">你可以从文件存储中复制为公告应用程序配置的所有音频文件。</span><span class="sxs-lookup"><span data-stu-id="87821-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="87821-116">**从文件存储中复制音频文件**</span><span class="sxs-lookup"><span data-stu-id="87821-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="87821-117">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="87821-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="87821-118">例如：</span><span class="sxs-lookup"><span data-stu-id="87821-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="87821-119">其中 X-ApplicationServer 指池的应用服务器的服务 ID (例如, 1-ApplicationServer-1)</span><span class="sxs-lookup"><span data-stu-id="87821-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="87821-120">在中断期间</span><span class="sxs-lookup"><span data-stu-id="87821-120">During an Outage</span></span>

<span data-ttu-id="87821-121">若要在中断期间使用公告应用程序, 您需要执行本部分中所述的任务, 在备份池中重新创建通知配置。</span><span class="sxs-lookup"><span data-stu-id="87821-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87821-122">我们建议你在故障转移到备份池后执行这些任务, 因为执行第2步后, 备份池将获得未分配的数字范围的所有权。</span><span class="sxs-lookup"><span data-stu-id="87821-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="87821-123">对于使用 Exchange UM 自动助理电话号码的号码范围, 不需要执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="87821-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="87821-124">**在备份池中重新创建公告配置**</span><span class="sxs-lookup"><span data-stu-id="87821-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="87821-125">通过执行下列操作, 重新创建在备份池中的主池中部署的公告:</span><span class="sxs-lookup"><span data-stu-id="87821-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="87821-126">通过使用**CsAnnouncementFile** cmdlet 并指定父参数的备份池, 将主池中使用的任何音频文件导入到备份池中。</span><span class="sxs-lookup"><span data-stu-id="87821-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="87821-127">通过使用**CsAnnouncement** cmdlet 并指定父参数的备份池, 重新创建每个公告。</span><span class="sxs-lookup"><span data-stu-id="87821-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87821-128">有关使用这些参数在备份池中创建公告的详细信息, 请参阅<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建公告</A>。</span><span class="sxs-lookup"><span data-stu-id="87821-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="87821-129">在备份池中重新创建所有公告后, 将主池中的 "公告" 中的所有未分配的号码范围重定向到 "备份" 池中的 "重新创建的公告"。</span><span class="sxs-lookup"><span data-stu-id="87821-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="87821-130">对于使用主池中的公告的每个未分配号码范围, 请运行以下操作:</span><span class="sxs-lookup"><span data-stu-id="87821-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="87821-131">停机后</span><span class="sxs-lookup"><span data-stu-id="87821-131">After the Outage</span></span>

<span data-ttu-id="87821-132">当主池可用时, 你需要将已更改的未分配数字范围重定向回主池。</span><span class="sxs-lookup"><span data-stu-id="87821-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87821-133">对于使用 Exchange UM 自动助理电话号码的号码范围, 不需要执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="87821-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="87821-134">**在主池中还原公告**</span><span class="sxs-lookup"><span data-stu-id="87821-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="87821-135">如果在恢复期间必须重新生成主池, 则需要在主池中重新创建公告, 方法是导入音频文件并创建通知, 就像在备份池中指定主池一样。参数.</span><span class="sxs-lookup"><span data-stu-id="87821-135">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter.</span></span> <span data-ttu-id="87821-136">有关详细信息, 请参阅本主题前面部分的 "停机期间"。</span><span class="sxs-lookup"><span data-stu-id="87821-136">For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="87821-137">对于您为中断而更改的每个未分配的号码范围, 请运行以下操作:</span><span class="sxs-lookup"><span data-stu-id="87821-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="87821-138">(可选) 删除在备份池中重新创建的公告。</span><span class="sxs-lookup"><span data-stu-id="87821-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="87821-139">获取备份池公告应用程序的公告列表。</span><span class="sxs-lookup"><span data-stu-id="87821-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="87821-140">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="87821-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="87821-141">例如：</span><span class="sxs-lookup"><span data-stu-id="87821-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="87821-142">在生成的列表中, 找到要删除和复制 Guid 的公告。</span><span class="sxs-lookup"><span data-stu-id="87821-142">In the resulting list, locate the announcements you want to remove and copy the GUIDs.</span></span> <span data-ttu-id="87821-143">对于要删除的每个通知, 请运行:</span><span class="sxs-lookup"><span data-stu-id="87821-143">For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="87821-144">例如：</span><span class="sxs-lookup"><span data-stu-id="87821-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

