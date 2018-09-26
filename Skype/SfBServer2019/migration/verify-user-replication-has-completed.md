---
title: 确认用户复制已完成
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当运行 Move-csuser cmdlet，您可能会遇到故障，因为 Active Directory 域服务 (AD DS) 和业务服务器 2019年数据库 Skype 之间的用户信息不同步的因为不完整的初始复制。 成功完成业务服务器 2019年用户复制程序服务的初始同步的 Skype 所花的时间取决于承载在承载 for Business Skype Active Directory 林中的域控制器数服务器 2019年池。 业务 Server 2019 前端服务器的 Skype 首次启动时，发生此事件业务 Server 2019 用户复制服务初始同步进程的 Skype。 之后，同步然后基于用户复制程序间隔。 完成以下步骤以确认用户复制已完成之前运行 Move-csuser cmdlet。
ms.openlocfilehash: 43b2822303676d209dc14a3b2e06368a7d24e174
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027842"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="39efe-107">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="39efe-107">Verify user replication has completed</span></span>

<span data-ttu-id="39efe-108">当运行**Move-csuser** cmdlet，您可能会遇到故障，如果因为的初始复制不完整同步的 Active Directory 域服务 (AD DS) 和业务服务器 2019年数据库 Skype 之间的用户信息。</span><span class="sxs-lookup"><span data-stu-id="39efe-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="39efe-109">成功完成业务服务器 2019年用户复制程序服务的初始同步的 Skype 所花的时间取决于承载在承载 for Business Skype Active Directory 林中的域控制器数服务器 2019年池。</span><span class="sxs-lookup"><span data-stu-id="39efe-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="39efe-110">业务 Server 2019 前端服务器的 Skype 首次启动时，发生此事件业务 Server 2019 用户复制服务初始同步进程的 Skype。</span><span class="sxs-lookup"><span data-stu-id="39efe-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="39efe-111">之后，同步基于用户复制程序间隔。</span><span class="sxs-lookup"><span data-stu-id="39efe-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="39efe-112">完成以下步骤以确认用户复制已完成之前运行**Move-csuser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="39efe-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="39efe-113">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="39efe-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="39efe-114">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="39efe-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="39efe-115">单击**开始**菜单，然后单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="39efe-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="39efe-116">输入**eventvwr.exe**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39efe-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="39efe-117">在事件查看器中，单击**应用程序和服务日志**将其展开，，然后选择业务服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="39efe-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="39efe-118">在**操作**窗格中，单击**筛选当前日志**。</span><span class="sxs-lookup"><span data-stu-id="39efe-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="39efe-119">从**事件来源**列表中，单击**LS 用户复制程序**。</span><span class="sxs-lookup"><span data-stu-id="39efe-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="39efe-120">在**\<所有事件 Id\>**，输入**30024**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39efe-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="39efe-121">在筛选的事件列表中，在**常规**选项卡上，查找表明用户复制已成功完成项。</span><span class="sxs-lookup"><span data-stu-id="39efe-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

