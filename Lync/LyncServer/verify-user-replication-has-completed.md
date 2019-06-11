---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="4b4a8-102">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="4b4a8-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b4a8-103">_**主题上次修改时间:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="4b4a8-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="4b4a8-104">运行**move-csuser** cmdlet 时, 你可能会遇到故障, 因为 Active Directory 域服务 (AD DS) 和 Lync Server 2013 数据库之间的用户信息不同步, 因为初始复制不完整。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="4b4a8-105">成功完成 Lync Server 2013 用户复制器服务的初始同步所需的时间取决于托管在托管 Lync Server 2013 池的 Active Directory 林中托管的域控制器的数量。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="4b4a8-106">Lync Server 2013 用户复制程序服务初始同步过程在 Lync Server 2013 前端服务器首次启动时出现。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="4b4a8-107">之后, 同步将基于用户复制程序间隔。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="4b4a8-108">在运行**move-csuser** cmdlet 之前, 请完成以下步骤以验证用户复制已完成。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="4b4a8-109">验证用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="4b4a8-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="4b4a8-110">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4b4a8-111">单击 "**开始**" 菜单, 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="4b4a8-112">输入**eventvwr.exe** , 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="4b4a8-113">在事件查看器中, 单击 "**应用程序和服务日志**" 以将其展开, 然后选择 "Lync Server"。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="4b4a8-114">在 "**操作**" 窗格中, 单击 "**筛选当前日志**"。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="4b4a8-115">从 "**事件源**" 列表中, 单击 "**用户复制**"。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="4b4a8-116">在\*\* \<所有事件 id\> **中输入**30024\*\* , 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="4b4a8-117">在 "筛选的事件" 列表的 "**常规**" 选项卡上, 查找指示 "用户复制已成功完成" 的条目。</span><span class="sxs-lookup"><span data-stu-id="4b4a8-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

