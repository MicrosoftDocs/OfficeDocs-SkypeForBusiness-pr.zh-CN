---
title: Lync Server 2013：灾难恢复测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c6c3b7c3b5d78324fe9c674650dd94338baea4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="484e8-102">Lync Server 2013 中的灾难恢复测试</span><span class="sxs-lookup"><span data-stu-id="484e8-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="484e8-103">_**主题上次修改时间：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="484e8-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="484e8-104">为 Lync Server 2013 池服务器执行系统恢复，以测试已记录的灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="484e8-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="484e8-105">此测试将模拟一台服务器的完整硬件故障并帮助确保资源、规划和数据都可用于恢复。</span><span class="sxs-lookup"><span data-stu-id="484e8-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="484e8-106">请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。</span><span class="sxs-lookup"><span data-stu-id="484e8-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="484e8-p102">请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。</span><span class="sxs-lookup"><span data-stu-id="484e8-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="484e8-109">将 Lync Server 2013 拓扑、策略和配置设置导出到文件。</span><span class="sxs-lookup"><span data-stu-id="484e8-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="484e8-110">在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="484e8-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="484e8-111">将 Lync Server 2013 拓扑、策略和配置设置导入中央管理存储或本地计算机，如以下命令所示：</span><span class="sxs-lookup"><span data-stu-id="484e8-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="484e8-112">若要备份 Lync Server 2013 数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="484e8-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="484e8-113">通过使用标准 SQL Server 备份过程来备份 RTC 和 LCSLog 数据库，以将数据库转储到文件或磁带转储设备。</span><span class="sxs-lookup"><span data-stu-id="484e8-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="484e8-114">使用第三方备份应用程序将数据备份到文件或磁带。</span><span class="sxs-lookup"><span data-stu-id="484e8-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="484e8-115">使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。</span><span class="sxs-lookup"><span data-stu-id="484e8-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="484e8-116">使用文件系统备份或第三方来备份会议内容和合规性日志。</span><span class="sxs-lookup"><span data-stu-id="484e8-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="484e8-117">使用 Export-CsConfiguration 命令行工具备份 Lync Server 2013 设置。</span><span class="sxs-lookup"><span data-stu-id="484e8-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="484e8-118">故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。</span><span class="sxs-lookup"><span data-stu-id="484e8-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="484e8-119">之所以称为强制性移动是因为生产池并不接受用户重新定位。</span><span class="sxs-lookup"><span data-stu-id="484e8-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="484e8-120">由于 RTC SQL 数据库上的记录更新，Lync Server 2013 移动用户进程对用户帐户对象上的属性的更改很有效。</span><span class="sxs-lookup"><span data-stu-id="484e8-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="484e8-121">此数据可通过以下两个过程还原：</span><span class="sxs-lookup"><span data-stu-id="484e8-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="484e8-122">通过使用标准 SQL Server 还原过程或使用第三方备份/还原实用工具，可以从生产 SQL Server 中的原始备份转储设备还原 RTC 数据库。</span><span class="sxs-lookup"><span data-stu-id="484e8-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="484e8-123">可以使用根据生产 SQL Server 导出创建的 XML 文件通过 DBIMPEXP.exe 实用程序还原用户联系人数据。</span><span class="sxs-lookup"><span data-stu-id="484e8-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="484e8-124">还原此数据后，用户可以有效地连接到灾难恢复 Lync Server 2013 池，并照常运行。</span><span class="sxs-lookup"><span data-stu-id="484e8-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="484e8-125">若要使用户能够连接到灾难恢复 Lync Server 2013 池，则需要更改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="484e8-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="484e8-126">使用以下各项的自动配置和 DNS SRV 记录，客户端将引用生产 Lync 服务器2013池：</span><span class="sxs-lookup"><span data-stu-id="484e8-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="484e8-127">SRV： \_sip。\_tls。\<域\> /CNAME： SIP。\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="484e8-128">CNAME： SIP。\<域\> /cvc-pool-1。\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="484e8-129">为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="484e8-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="484e8-130">CNAME： SIP。\<域\> /DROCSPool。\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="484e8-131">Sip.\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="484e8-132">AV。\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-132">AV.\<domain\></span></span>

  - <span data-ttu-id="484e8-133">webconf.\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="484e8-134">OCSServices.\<域\></span><span class="sxs-lookup"><span data-stu-id="484e8-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="484e8-135">有关详细的管理和管理过程，请参阅<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">备份和还原 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="484e8-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="484e8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="484e8-136">See Also</span></span>


[<span data-ttu-id="484e8-137">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="484e8-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="484e8-138">Lync Server 2013 中的 "备份" 和 "高可用性" cmdlet</span><span class="sxs-lookup"><span data-stu-id="484e8-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="484e8-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="484e8-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="484e8-140">备份和还原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="484e8-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="484e8-141">管理 Lync Server 2013 灾难恢复、高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="484e8-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

