---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在运行 Get-csuser cmdlet 时，您可能会遇到故障，因为 Active Directory 域服务（AD DS）和 Skype for Business Server 2019 数据库之间的用户信息因初始复制不完整而不同步。 成功完成 Skype for business Server 2019 用户复制程序服务的初始同步所需的时间取决于托管在承载 Skype for Business Server 2019 池的 Active Directory 林中的域控制器数。 当第一次启动 Skype for business Server 2019 前端服务器时，将发生 Skype for Business Server 2019 用户复制程序服务初始同步过程。 此后，同步将基于用户复制程序间隔执行。 在运行 Move-CsUser cmdlet 之前，请先完成下列步骤以确认用户复制已完成。
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751644"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="9ec5c-107">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="9ec5c-107">Verify user replication has completed</span></span>

<span data-ttu-id="9ec5c-108">在运行**get-csuser** cmdlet 时，如果 Active Directory 域服务（AD DS）和 Skype For business Server 2019 数据库之间的用户信息因初始复制不完整而不同步，则可能会遇到故障。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="9ec5c-109">成功完成 Skype for business Server 2019 用户复制程序服务的初始同步所需的时间取决于托管在承载 Skype for Business Server 2019 池的 Active Directory 林中的域控制器数。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9ec5c-110">当第一次启动 Skype for business Server 2019 前端服务器时，将发生 Skype for Business Server 2019 用户复制程序服务初始同步过程。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="9ec5c-111">之后，同步基于用户复制程序间隔。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="9ec5c-112">完成以下步骤以验证用户复制是否已完成，然后再运行**get-csuser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="9ec5c-113">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="9ec5c-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="9ec5c-114">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9ec5c-115">单击“开始”\*\*\*\* 菜单，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="9ec5c-116">输入 **eventvwr.exe**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="9ec5c-117">在事件查看器中，单击 "**应用程序和服务日志**" 以展开它，然后选择 "Skype For business Server"。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="9ec5c-118">在“操作”\*\*\*\* 窗格中，单击“筛选当前日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="9ec5c-119">在“事件来源”\*\*\*\* 列表中，单击“LS 用户复制程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="9ec5c-120">在中 **\<All Event IDs\>** ，输入**30024**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="9ec5c-121">在 "筛选的事件" 列表中的 "**常规**" 选项卡上，查找指示用户复制已成功完成的条目。</span><span class="sxs-lookup"><span data-stu-id="9ec5c-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

