---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bed57b6e24db0ba6f75e323fe311aa4aaf262c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="35eff-102">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="35eff-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35eff-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="35eff-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="35eff-104">在运行**CsLegacyUser** cmdlet 时，您可能会由于初始复制不完整而导致 Active Directory 域服务（AD DS）和 Lync Server 2013 数据库之间的用户信息出现故障。</span><span class="sxs-lookup"><span data-stu-id="35eff-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="35eff-105">成功完成 Lync Server 2013 用户复制程序服务的初始同步所需的时间取决于托管在承载 Lync Server 2013 池的 Active Directory 林中的域控制器数。</span><span class="sxs-lookup"><span data-stu-id="35eff-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="35eff-106">在首次启动 Lync Server 2013 前端服务器时，会发生 Lync Server 2013 用户复制程序服务初始同步过程。</span><span class="sxs-lookup"><span data-stu-id="35eff-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="35eff-107">此后，同步将基于用户复制程序间隔执行。</span><span class="sxs-lookup"><span data-stu-id="35eff-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="35eff-108">在运行 **Move-CsLegacyUser** cmdlet 之前，请先完成下列步骤以确认用户复制已完成。</span><span class="sxs-lookup"><span data-stu-id="35eff-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="35eff-109">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="35eff-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="35eff-110">在 Lync Server 2013 前端服务器中，单击 "**开始**" 菜单，然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="35eff-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="35eff-111">输入 **eventvwr.exe**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="35eff-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="35eff-112">在事件查看器中，单击“应用程序和服务日志”\*\*\*\* 将其展开，然后选择“Lync Server”。</span><span class="sxs-lookup"><span data-stu-id="35eff-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="35eff-113">在“操作”\*\*\*\* 窗格中，单击“筛选当前日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="35eff-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="35eff-114">在“事件来源”\*\*\*\* 列表中，单击“LS 用户复制程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="35eff-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="35eff-115">在 **\<All Event IDs\>** 输入**30024** ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="35eff-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="35eff-116">在筛选的事件列表中的“常规”\*\*\*\* 选项卡上，查找表明用户复制已成功完成的条目。</span><span class="sxs-lookup"><span data-stu-id="35eff-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

