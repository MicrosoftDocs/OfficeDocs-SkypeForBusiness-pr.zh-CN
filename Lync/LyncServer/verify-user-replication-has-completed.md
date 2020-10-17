---
title: 确认用户复制已完成
description: 确认用户复制已完成。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555478"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="b9fa7-103">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="b9fa7-103">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9fa7-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="b9fa7-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="b9fa7-105">在运行 **get-csuser** cmdlet 时，您可能会遇到故障，因为 Active Directory 域服务 (AD DS) 和 Lync Server 2013 数据库之间的用户信息因初始复制不完整而无法同步。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-105">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="b9fa7-106">成功完成 Lync Server 2013 用户复制程序服务的初始同步所需的时间取决于托管在承载 Lync Server 2013 池的 Active Directory 林中的域控制器数。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-106">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="b9fa7-107">在首次启动 Lync Server 2013 前端服务器时，会发生 Lync Server 2013 用户复制程序服务初始同步过程。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-107">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="b9fa7-108">此后，同步将基于用户复制程序间隔执行。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-108">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="b9fa7-109">在运行 **Move-CsUser** cmdlet 之前，请先完成下列步骤以确认用户复制已完成。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-109">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="b9fa7-110">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="b9fa7-110">To verify user replication has completed</span></span>

1.  <span data-ttu-id="b9fa7-111">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b9fa7-112">单击“开始”\*\*\*\* 菜单，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-112">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="b9fa7-113">输入 **eventvwr.exe**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-113">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="b9fa7-114">在事件查看器中，单击“应用程序和服务日志”\*\*\*\* 将其展开，然后选择“Lync Server”。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-114">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="b9fa7-115">在“操作”\*\*\*\* 窗格中，单击“筛选当前日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-115">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="b9fa7-116">在“事件来源”\*\*\*\* 列表中，单击“LS 用户复制程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-116">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="b9fa7-117">在 **\<All Event IDs\>** 输入 **30024** ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-117">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="b9fa7-118">在筛选的事件列表中的“常规”\*\*\*\* 选项卡上，查找表明用户复制已成功完成的条目。</span><span class="sxs-lookup"><span data-stu-id="b9fa7-118">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

