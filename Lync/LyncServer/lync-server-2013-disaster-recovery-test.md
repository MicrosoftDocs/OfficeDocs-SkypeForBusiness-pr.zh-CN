---
title: Lync Server 2013：灾难恢复测试
description: Lync Server 2013：灾难恢复测试。
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
ms.openlocfilehash: fa22abd37f656134c54381d63f29d3160ff85257
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557658"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="89f69-103">Lync Server 2013 中的灾难恢复测试</span><span class="sxs-lookup"><span data-stu-id="89f69-103">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f69-104">_**上次修改的主题：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="89f69-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="89f69-105">为 Lync Server 2013 池服务器执行系统恢复，以测试已记录的灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="89f69-105">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="89f69-106">此测试将模拟一台服务器的完全硬件故障，并将帮助确保资源、计划和数据可用于恢复。</span><span class="sxs-lookup"><span data-stu-id="89f69-106">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="89f69-107">尝试每月旋转测试的焦点，以便您的组织每次都测试不同的服务器或其他设备的故障。</span><span class="sxs-lookup"><span data-stu-id="89f69-107">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="89f69-108">请注意，组织执行灾难恢复测试的计划将有所不同。</span><span class="sxs-lookup"><span data-stu-id="89f69-108">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="89f69-109">不会忽略或忽略灾难恢复测试，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="89f69-109">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="89f69-110">将 Lync Server 2013 拓扑、策略和配置设置导出到文件中。</span><span class="sxs-lookup"><span data-stu-id="89f69-110">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="89f69-111">此外，还可以使用此文件在升级后将此信息还原到中央管理存储，或者在发生硬件故障或其他一些问题导致数据丢失的情况下。</span><span class="sxs-lookup"><span data-stu-id="89f69-111">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="89f69-112">将 Lync Server 2013 拓扑、策略和配置设置导入到中央管理存储或本地计算机，如以下命令所示：</span><span class="sxs-lookup"><span data-stu-id="89f69-112">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="89f69-113">若要备份 Lync Server 2013 数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="89f69-113">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="89f69-114">使用标准 SQL Server 备份过程将数据库转储到文件或磁带转储设备，从而备份 RTC 和 LCSLog 数据库。</span><span class="sxs-lookup"><span data-stu-id="89f69-114">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="89f69-115">使用第三方备份应用程序将数据备份到文件或磁带。</span><span class="sxs-lookup"><span data-stu-id="89f69-115">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="89f69-116">使用 Export-CsUserData cmdlet 可以创建整个 RTC 数据库的 XML 导出。</span><span class="sxs-lookup"><span data-stu-id="89f69-116">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="89f69-117">使用文件系统备份或第三方备份会议内容和合规性日志。</span><span class="sxs-lookup"><span data-stu-id="89f69-117">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="89f69-118">使用 Export-CsConfiguration 命令行工具备份 Lync Server 2013 设置。</span><span class="sxs-lookup"><span data-stu-id="89f69-118">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="89f69-119">故障转移过程中的第一步包括将用户从生产池强制移动到灾难恢复池。</span><span class="sxs-lookup"><span data-stu-id="89f69-119">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="89f69-120">这将是强制移动，因为生产池将不能接受用户重新定位。</span><span class="sxs-lookup"><span data-stu-id="89f69-120">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="89f69-121">除了 RTC SQL 数据库上的记录更新之外，Lync Server 2013 移动用户过程实际上也是对用户帐户对象上属性的更改。</span><span class="sxs-lookup"><span data-stu-id="89f69-121">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="89f69-122">可以通过以下两个过程来还原这些数据：</span><span class="sxs-lookup"><span data-stu-id="89f69-122">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="89f69-123">使用标准 SQL Server 还原过程或使用第三方备份/还原实用程序，可以从生产 SQL Server 从原始备份转储设备还原 RTC 数据库。</span><span class="sxs-lookup"><span data-stu-id="89f69-123">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="89f69-124">可以使用使用从生产 SQL Server 导出创建的 XML 文件的 DBIMPEXP.exe 实用程序还原用户联系人数据。</span><span class="sxs-lookup"><span data-stu-id="89f69-124">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="89f69-125">还原此数据后，用户可以有效地连接到灾难恢复 Lync Server 2013 池，并照常运行。</span><span class="sxs-lookup"><span data-stu-id="89f69-125">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="89f69-126">若要使用户能够连接到灾难恢复 Lync Server 2013 池，将需要进行 DNS 记录更改。</span><span class="sxs-lookup"><span data-stu-id="89f69-126">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="89f69-127">使用以下各项的自动配置和 DNS SRV 记录，客户端将引用生产 Lync Server 2013 池：</span><span class="sxs-lookup"><span data-stu-id="89f69-127">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="89f69-128">SRV： \_ sip。 \_eap-tls.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-128">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="89f69-129">/CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-129">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="89f69-130">CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-130">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="89f69-131">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-131">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="89f69-132">为了便于进行故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="89f69-132">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="89f69-133">CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-133">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="89f69-134">/DROCSPool.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-134">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="89f69-135">Sip.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-135">Sip.\<domain\></span></span>

  - <span data-ttu-id="89f69-136">AV.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-136">AV.\<domain\></span></span>

  - <span data-ttu-id="89f69-137">webconf.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-137">webconf.\<domain\></span></span>

  - <span data-ttu-id="89f69-138">OCSServices.\<domain\></span><span class="sxs-lookup"><span data-stu-id="89f69-138">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89f69-139">有关详细的管理和管理过程，请参阅 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">备份和还原 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="89f69-139">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89f69-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f69-140">See Also</span></span>


[<span data-ttu-id="89f69-141">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="89f69-141">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="89f69-142">Lync Server 2013 中的备份和高可用性 cmdlet</span><span class="sxs-lookup"><span data-stu-id="89f69-142">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="89f69-143">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="89f69-143">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="89f69-144">备份和还原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f69-144">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="89f69-145">管理 Lync Server 2013 灾难恢复、高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="89f69-145">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

