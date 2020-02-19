---
title: Lync Server 2013： ABC 池故障转移的备份先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a23e93741400efe4744e9219a19ca2c0217a33e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="cd907-102">Lync Server 2013 中的 ABC 池故障转移的备份先决条件</span><span class="sxs-lookup"><span data-stu-id="cd907-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd907-103">_**上次修改的主题：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="cd907-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="cd907-104">若要获取使用 ABC 池故障转移过程的最大好处，必须在发生灾难和故障转移之前执行某些备份：</span><span class="sxs-lookup"><span data-stu-id="cd907-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="cd907-105">您必须使用**CsLISConfiguration** cmdlet 定期备份池 A 中的位置信息服务（.lis）配置数据。</span><span class="sxs-lookup"><span data-stu-id="cd907-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="cd907-106">您必须使用**CsRgsConfiguration** cmdlet 定期备份 pool A 中的响应组配置数据。</span><span class="sxs-lookup"><span data-stu-id="cd907-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="cd907-107">通常，建议您执行日常备份，但如果您要进行大量更改，那么您可能希望安排更为频繁的备份。</span><span class="sxs-lookup"><span data-stu-id="cd907-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="cd907-108">灾难发生时可以丢失的信息量取决于备份的频率，以及更改的频率和数量的情况。</span><span class="sxs-lookup"><span data-stu-id="cd907-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="cd907-109">响应组应用程序只能为每个池存储一组应用程序级别的设置。</span><span class="sxs-lookup"><span data-stu-id="cd907-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="cd907-110">可以通过**CsRgsConfiguration** cmdlet 访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="cd907-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="cd907-111">这些设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理的电话拨入式宽限期和呼叫上下文配置。</span><span class="sxs-lookup"><span data-stu-id="cd907-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="cd907-112">通过使用**ReplaceExistingSettings**参数，可以通过**CsRgsConfiguration** cmdlet 将这些设置从一个池传输到另一个池，但此操作将替代目标池中的任何应用程序级设置。</span><span class="sxs-lookup"><span data-stu-id="cd907-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="cd907-113">在一个单独的位置，保留已用于配置响应组应用程序的所有原始音频文件的备份副本（即任何录制或保留音乐的文件）。</span><span class="sxs-lookup"><span data-stu-id="cd907-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="cd907-114">如果已为池中的呼叫寄存上载了任何自定义的已保留音乐文件，则应在其他位置保留这些文件的副本。</span><span class="sxs-lookup"><span data-stu-id="cd907-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="cd907-115">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="cd907-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd907-116">呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="cd907-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="cd907-117">可以通过<STRONG>CsCpsConfiguration</STRONG> cmdlet 访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="cd907-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="cd907-118">由于呼叫寄存的灾难恢复机制依赖于备份池的呼叫寄存应用程序，因此在发生灾难时不会备份或保留主池的设置。</span><span class="sxs-lookup"><span data-stu-id="cd907-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="cd907-119">如果主池丢失，则无法恢复这些设置，并且在部署新池以替换主池时，将需要重新配置呼叫寄存设置和任何自定义的保持音乐音频文件。</span><span class="sxs-lookup"><span data-stu-id="cd907-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="cd907-120">如果将任何公告配置为 "未分配号码语音" 功能的一部分，我们建议您将在初始配置期间使用的任何原始音频文件的副本保留在另一个位置。</span><span class="sxs-lookup"><span data-stu-id="cd907-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="cd907-121">如果不执行此操作，则可以在导入音频文件的服务器或池的文件存储中获取已配置的音频文件的副本。</span><span class="sxs-lookup"><span data-stu-id="cd907-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="cd907-122">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，这些文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="cd907-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="cd907-123">若要从服务器或池的文件存储中复制用于配置未分配号码语音功能的所有音频文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="cd907-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="cd907-124">如果您已监视和存档池中的数据库，则应使用 SQL Server 管理工具对其进行备份。</span><span class="sxs-lookup"><span data-stu-id="cd907-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="cd907-125">在 ABC 故障转移过程中，如果监视和存档数据库在池 A 中并置，则不会保留这些数据库，因为这些数据库不是通过 Lync Server 备份服务备份的。</span><span class="sxs-lookup"><span data-stu-id="cd907-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

