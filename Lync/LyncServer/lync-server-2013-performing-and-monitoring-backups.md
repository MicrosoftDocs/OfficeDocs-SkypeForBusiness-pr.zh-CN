---
title: 'Lync Server 2013: 执行和监视备份'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="40af4-102">在 Lync Server 2013 中执行和监视备份</span><span class="sxs-lookup"><span data-stu-id="40af4-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40af4-103">_**主题上次修改时间:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="40af4-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="40af4-104">你的业务优先级应推动你的组织的备份和还原要求的规范。</span><span class="sxs-lookup"><span data-stu-id="40af4-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="40af4-105">对服务器和数据执行备份是规划灾难的第一防线。</span><span class="sxs-lookup"><span data-stu-id="40af4-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="40af4-106">运行 Lync Server 2013 服务或服务器角色的计算机必须具有当前拓扑、当前配置设置和当前策略的副本, 然后它们才能在其已设定的角色中起作用。</span><span class="sxs-lookup"><span data-stu-id="40af4-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="40af4-107">Lync 服务器负责确保将此信息传递给需要它的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="40af4-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="40af4-108">**Export-CsConfiguration**和**Import CsConfiguration** Cmdlet 用于在中央管理存储升级期间备份和还原 Lync Server 拓扑、配置设置和策略。</span><span class="sxs-lookup"><span data-stu-id="40af4-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="40af4-109">**导出-CsConfiguration** cmdlet 使你能够将数据导出到。ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="40af4-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="40af4-110">然后, 你可以使用**CsConfiguration** cmdlet 进行读取。ZIP 文件, 并将拓扑、配置设置和策略还原到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="40af4-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="40af4-111">此后, Lync Server 的复制服务会将还原的信息复制到其他运行 Lync Server 服务的计算机。</span><span class="sxs-lookup"><span data-stu-id="40af4-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="40af4-112">在外围网络 (如 Edge 服务器) 中的计算机的初始配置期间还会使用导出和导入配置数据的功能。</span><span class="sxs-lookup"><span data-stu-id="40af4-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="40af4-113">在外围网络中配置计算机时, 必须首先使用 CsConfiguration cmdlet 执行手动复制: 必须通过使用**export-CsConfiguration**导出配置数据, 然后复制。将文件压缩到外围网络中的计算机。</span><span class="sxs-lookup"><span data-stu-id="40af4-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="40af4-114">之后, 你可以使用**import-CsConfiguration**和 LocalStore 参数导入数据。</span><span class="sxs-lookup"><span data-stu-id="40af4-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="40af4-115">您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="40af4-115">You only have to do this one time.</span></span> <span data-ttu-id="40af4-116">之后, 将自动执行复制。</span><span class="sxs-lookup"><span data-stu-id="40af4-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="40af4-117">哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行本地**CsConfiguration** Cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="40af4-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="40af4-118">若要返回所有 RBAC 角色的列表, 请将此 cmdlet 分配给 (包括你自己创建的任何自定义 RBAC 角色), 从 Windows PowerShell 提示中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="40af4-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="40af4-119">所有 SQL 2012 后端数据库应按[SQL 最佳做法](http://go.microsoft.com/fwlink/p/?linkid=290716)进行备份。</span><span class="sxs-lookup"><span data-stu-id="40af4-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="40af4-120">对于您的 Lync Server 2013 基础结构, 定期测试灾难恢复计划应在尽可能模拟生产环境的实验室环境中执行。</span><span class="sxs-lookup"><span data-stu-id="40af4-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="40af4-121">有关灾难恢复测试的详细信息, 请参阅每月任务。</span><span class="sxs-lookup"><span data-stu-id="40af4-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="40af4-122">请注意, 可以根据你的还原点和恢复点目标调整备份频率。</span><span class="sxs-lookup"><span data-stu-id="40af4-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="40af4-123">最佳做法是在一天内定期执行定期快照。</span><span class="sxs-lookup"><span data-stu-id="40af4-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="40af4-124">通常情况下, 每隔24小时执行完整备份。</span><span class="sxs-lookup"><span data-stu-id="40af4-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="40af4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40af4-125">See Also</span></span>


[<span data-ttu-id="40af4-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="40af4-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="40af4-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="40af4-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="40af4-128">SQL 最佳做法</span><span class="sxs-lookup"><span data-stu-id="40af4-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

