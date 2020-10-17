---
title: Lync Server 2013：执行和监视备份
description: Lync Server 2013：执行和监视备份。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557228"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="197fe-103">在 Lync Server 2013 中执行和监视备份</span><span class="sxs-lookup"><span data-stu-id="197fe-103">Performing and monitoring backups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="197fe-104">_**上次修改的主题：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="197fe-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="197fe-105">您的业务优先级应推动组织的备份和还原要求的规范。</span><span class="sxs-lookup"><span data-stu-id="197fe-105">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="197fe-106">在规划灾难时，执行服务器和数据的备份是第一条防御措施。</span><span class="sxs-lookup"><span data-stu-id="197fe-106">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="197fe-107">运行 Lync Server 2013 服务或服务器角色的计算机必须具有当前拓扑的副本、当前配置设置和当前策略，然后它们才能在其可配置的角色中运行。</span><span class="sxs-lookup"><span data-stu-id="197fe-107">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="197fe-108">Lync Server 负责确保将此信息传递给需要它的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="197fe-108">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="197fe-109">**CsConfiguration**和**CsConfiguration** Cmdlet 用于在中央管理存储升级期间备份和还原 Lync Server 拓扑、配置设置和策略。</span><span class="sxs-lookup"><span data-stu-id="197fe-109">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="197fe-110">**CsConfiguration** cmdlet 使您能够将数据导出到。ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="197fe-110">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="197fe-111">然后，您可以使用 **CsConfiguration** cmdlet 读取该。ZIP 文件，并将拓扑、配置设置和策略还原到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="197fe-111">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="197fe-112">之后，Lync Server 的复制服务会将还原的信息复制到其他运行 Lync Server 服务的计算机。</span><span class="sxs-lookup"><span data-stu-id="197fe-112">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="197fe-113">在位于外围网络中的计算机的初始配置过程中，还会使用导出和导入配置数据的功能 (例如，边缘服务器) 。</span><span class="sxs-lookup"><span data-stu-id="197fe-113">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="197fe-114">在外围网络中配置计算机时，必须首先使用 CsConfiguration cmdlet 执行手动复制：必须使用 **export-CsConfiguration** 导出配置数据，然后复制。ZIP 文件到外围网络中的计算机。</span><span class="sxs-lookup"><span data-stu-id="197fe-114">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="197fe-115">此后，您就可以使用 **Import-CsConfiguration** 和 LocalStore 参数导入该数据。</span><span class="sxs-lookup"><span data-stu-id="197fe-115">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="197fe-116">您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="197fe-116">You only have to do this one time.</span></span> <span data-ttu-id="197fe-117">之后，将自动执行复制。</span><span class="sxs-lookup"><span data-stu-id="197fe-117">After that, replication will occur automatically.</span></span>

<span data-ttu-id="197fe-118">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Export-CsConfiguration** cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="197fe-118">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="197fe-119">若要返回所有 RBAC 角色的列表，请将此 cmdlet 分配给 (，其中包括您自己) 创建的任何自定义 RBAC 角色，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="197fe-119">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="197fe-120">应按照 [sql 最佳实践](https://go.microsoft.com/fwlink/p/?linkid=290716)来备份所有 SQL 2012 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="197fe-120">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="197fe-121">应在尽可能模拟生产环境的实验室环境中执行对 Lync Server 2013 基础结构的灾难恢复计划的定期测试。</span><span class="sxs-lookup"><span data-stu-id="197fe-121">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="197fe-122">有关灾难恢复测试的详细信息，请参阅每月任务。</span><span class="sxs-lookup"><span data-stu-id="197fe-122">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="197fe-123">请注意，可以根据还原点和恢复点目标调整备份频率。</span><span class="sxs-lookup"><span data-stu-id="197fe-123">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="197fe-124">作为最佳实践，请在全天中定期拍摄定期快照。</span><span class="sxs-lookup"><span data-stu-id="197fe-124">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="197fe-125">通常情况下，每隔24小时执行一次完整备份。</span><span class="sxs-lookup"><span data-stu-id="197fe-125">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="197fe-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="197fe-126">See Also</span></span>


[<span data-ttu-id="197fe-127">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="197fe-127">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="197fe-128">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="197fe-128">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="197fe-129">SQL 最佳实践</span><span class="sxs-lookup"><span data-stu-id="197fe-129">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

