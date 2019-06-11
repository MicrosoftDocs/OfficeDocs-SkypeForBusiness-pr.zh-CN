---
title: 'Lync Server 2013: ABC 池故障转移的备份先决条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="dd03e-102">Lync Server 2013 中的 ABC 池故障转移的备份先决条件</span><span class="sxs-lookup"><span data-stu-id="dd03e-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd03e-103">_**主题上次修改时间:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="dd03e-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="dd03e-104">若要获取使用 ABC 池故障转移过程的最大好处, 必须在发生灾难和故障转移之前执行某些备份:</span><span class="sxs-lookup"><span data-stu-id="dd03e-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="dd03e-105">你必须通过使用**CsLISConfiguration** cmdlet 定期备份来自池 A 的位置信息服务 (.lis) 配置数据。</span><span class="sxs-lookup"><span data-stu-id="dd03e-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="dd03e-106">你必须使用**CsRgsConfiguration** cmdlet 定期备份池中 A 中的响应组配置数据。</span><span class="sxs-lookup"><span data-stu-id="dd03e-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="dd03e-107">一般情况下, 我们建议你执行每日备份, 但如果你有大量更改, 你可能希望计划更频繁的备份。</span><span class="sxs-lookup"><span data-stu-id="dd03e-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="dd03e-108">灾难发生时可能会丢失的信息量取决于备份的频率, 以及更改的频率和数量的情况。</span><span class="sxs-lookup"><span data-stu-id="dd03e-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="dd03e-109">响应组应用程序只能存储每个池的一组应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="dd03e-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="dd03e-110">可通过**CsRgsConfiguration** cmdlet 访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="dd03e-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="dd03e-111">这些设置包括默认的 "保留式音乐" 配置、默认的 "音乐暂停" 音频文件、代理的 "震铃" 的宽限期和 "呼叫上下文配置"。</span><span class="sxs-lookup"><span data-stu-id="dd03e-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="dd03e-112">通过使用**ReplaceExistingSettings**参数, 可以通过**Import CsRgsConfiguration** cmdlet 将这些设置从一个池传输到另一个池, 但此操作将替代目标中的任何应用程序级别设置池.</span><span class="sxs-lookup"><span data-stu-id="dd03e-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="dd03e-113">在单独位置, 保留已用于配置响应组应用程序 (即任何录制或音乐保留文件) 的所有原始音频文件的备份副本。</span><span class="sxs-lookup"><span data-stu-id="dd03e-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="dd03e-114">如果在池中为呼叫寄存上载了任何自定义的已保留音乐文件, 则应在其他位置保留这些文件的副本。</span><span class="sxs-lookup"><span data-stu-id="dd03e-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="dd03e-115">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份, 如果上载到该池的文件已损坏、损坏或清除, 这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="dd03e-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd03e-116">呼叫驻留应用程序只能存储一组设置和一个每个池的自定义音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="dd03e-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="dd03e-117">可通过<STRONG>CsCpsConfiguration</STRONG> cmdlet 访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="dd03e-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="dd03e-118">由于呼叫寄存的灾难恢复机制依赖于备份池的调用寄存应用程序, 因此如果发生灾难, 则不会备份或保留主池的设置。</span><span class="sxs-lookup"><span data-stu-id="dd03e-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="dd03e-119">如果主池丢失, 则无法恢复这些设置, 并且当部署新池来替换主池时, 将需要重新配置呼叫寄存设置和任何自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="dd03e-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="dd03e-120">如果将任何公告配置为 "未分配的号码" 语音功能的一部分, 我们建议您将初始配置期间使用的任何原始音频文件的副本保留在其他位置。</span><span class="sxs-lookup"><span data-stu-id="dd03e-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="dd03e-121">如果你不执行此操作, 则可以在导入音频文件的服务器或池的文件存储中获取已配置音频文件的副本。</span><span class="sxs-lookup"><span data-stu-id="dd03e-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="dd03e-122">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份, 如果上载到该池的文件已损坏、损坏或清除, 这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="dd03e-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="dd03e-123">若要从服务器或池的文件存储中复制用于配置 "未分配数字语音" 功能的所有音频文件, 请使用:</span><span class="sxs-lookup"><span data-stu-id="dd03e-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="dd03e-124">如果在池中监视和存档数据库, 则应使用 SQL Server 管理工具对其进行备份。</span><span class="sxs-lookup"><span data-stu-id="dd03e-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="dd03e-125">在 ABC 故障转移过程中, 如果在 pool A 中 collocated, 则不会保留监视和存档数据库, 因为这些数据库不是通过 Lync Server 备份服务进行备份的。</span><span class="sxs-lookup"><span data-stu-id="dd03e-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

