---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 运行 Move-csuser cmdlet 时, 你可能会遇到故障, 因为 Active Directory 域服务 (AD DS) 和 Skype for business Server 2019 数据库之间的用户信息不同步, 因为初始复制不完整。 成功完成 Skype for business Server 2019 用户复制器服务的初始同步所需的时间取决于托管 Skype for business 的 Active Directory 林中托管的域控制器的数量服务器2019池。 Skype for Business Server 2019 用户复制器服务在第一次启动 Skype for business 服务器2019前端服务器时, 将发生初始同步过程。 之后, 同步将基于用户复制程序间隔。 在运行 Move-csuser cmdlet 之前, 请完成以下步骤以验证用户复制已完成。
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280644"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="eab69-107">确认用户复制已完成</span><span class="sxs-lookup"><span data-stu-id="eab69-107">Verify user replication has completed</span></span>

<span data-ttu-id="eab69-108">运行**move-csuser** cmdlet 时, 如果 Active Directory 域服务 (AD DS) 和 Skype For business Server 2019 数据库之间的用户信息不同步, 则你可能会遇到故障, 因为初始复制不完整。</span><span class="sxs-lookup"><span data-stu-id="eab69-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="eab69-109">成功完成 Skype for business Server 2019 用户复制器服务的初始同步所需的时间取决于托管 Skype for business 的 Active Directory 林中托管的域控制器的数量服务器2019池。</span><span class="sxs-lookup"><span data-stu-id="eab69-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="eab69-110">Skype for Business Server 2019 用户复制器服务在第一次启动 Skype for business 服务器2019前端服务器时, 将发生初始同步过程。</span><span class="sxs-lookup"><span data-stu-id="eab69-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="eab69-111">之后, 同步基于用户复制程序间隔。</span><span class="sxs-lookup"><span data-stu-id="eab69-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="eab69-112">完成以下步骤以在运行**move-csuser** cmdlet 之前验证用户复制是否已完成。</span><span class="sxs-lookup"><span data-stu-id="eab69-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="eab69-113">验证用户复制是否已完成</span><span class="sxs-lookup"><span data-stu-id="eab69-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="eab69-114">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="eab69-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="eab69-115">单击 "**开始**" 菜单, 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="eab69-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="eab69-116">输入**eventvwr.exe**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="eab69-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="eab69-117">在事件查看器中, 单击 "**应用程序和服务日志**" 以将其展开, 然后选择 "Skype For business 服务器"。</span><span class="sxs-lookup"><span data-stu-id="eab69-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="eab69-118">在 "**操作**" 窗格中, 单击 "**筛选当前日志**"。</span><span class="sxs-lookup"><span data-stu-id="eab69-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="eab69-119">从 "**事件源**" 列表中, 单击 "**用户复制**"。</span><span class="sxs-lookup"><span data-stu-id="eab69-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="eab69-120">在\*\* \<所有事件 id\>\*\* 中, 输入**30024**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="eab69-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="eab69-121">在 "筛选的事件" 列表中的 "**常规**" 选项卡上, 查找指示用户复制已成功完成的条目。</span><span class="sxs-lookup"><span data-stu-id="eab69-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

