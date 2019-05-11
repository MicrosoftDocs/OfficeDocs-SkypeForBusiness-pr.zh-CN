---
title: 为业务服务器部署已配对的前端池 Skype 中的灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 你可以决定使用配对的前端池来提供灾难恢复保护，但这并不是必需满足的要求。
ms.openlocfilehash: b281b8d0e9453de2f3faeab5abad88c846633f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894547"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="e888d-103">为业务服务器部署已配对的前端池 Skype 中的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="e888d-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="e888d-104">你可以决定使用配对的前端池来提供灾难恢复保护，但这并不是必需满足的要求。</span><span class="sxs-lookup"><span data-stu-id="e888d-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="e888d-105">您可以轻松部署已配对前端池使用拓扑生成器的灾难恢复拓扑。</span><span class="sxs-lookup"><span data-stu-id="e888d-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="e888d-106">部署配对前端池</span><span class="sxs-lookup"><span data-stu-id="e888d-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="e888d-107">如果是新池并且尚未定义，请使用拓扑生成器创建这些池。</span><span class="sxs-lookup"><span data-stu-id="e888d-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="e888d-108">在拓扑生成器中，右键单击两个池之一，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="e888d-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e888d-109">在左侧窗格中单击“**复原**”，然后在右侧窗格中选择“**关联的备份池**”。</span><span class="sxs-lookup"><span data-stu-id="e888d-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="e888d-p101">在“**关联的备份池**”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。</span><span class="sxs-lookup"><span data-stu-id="e888d-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="e888d-112">选择“**语音的自动故障转移和故障回复**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e888d-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="e888d-113">当你查看该池的详细信息时，此时关联的池显示在“**复原**”下的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="e888d-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="e888d-114">使用拓扑生成器发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="e888d-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="e888d-p102">如果尚未部署两个池，请立即部署它们，配置随即完成。你可以跳过此过程的最后两步。</span><span class="sxs-lookup"><span data-stu-id="e888d-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="e888d-117">但是，如果在定义配对关系之前已部署池，那么必须完成以下两个最终步骤。</span><span class="sxs-lookup"><span data-stu-id="e888d-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="e888d-118">在两个池的每个前端服务器上，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e888d-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="e888d-119">这将配置确保备份配对正常运行所需的其他服务。</span><span class="sxs-lookup"><span data-stu-id="e888d-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="e888d-120">从 Skype 的业务 Server 命令行管理程序命令提示符处，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e888d-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="e888d-121">使用以下 cmdlet 强制两个池的用户和会议数据相互同步：</span><span class="sxs-lookup"><span data-stu-id="e888d-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="e888d-p103">同步数据可能需要一些时间。你可以使用以下 cmdlet 检查同步状态。确保两个方向的状态均保持稳定。</span><span class="sxs-lookup"><span data-stu-id="e888d-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="e888d-125">**自动故障转移和故障回复语音**选项和拓扑生成器中的关联的时间间隔仅适用于 Lync Server 中引入的语音恢复能力功能。</span><span class="sxs-lookup"><span data-stu-id="e888d-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="e888d-126">选择此选项并不意味着会自动执行本文档中讨论的池故障转移。</span><span class="sxs-lookup"><span data-stu-id="e888d-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="e888d-127">池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e888d-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e888d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e888d-128">See also</span></span>

[<span data-ttu-id="e888d-129">为业务 Server 前端中 Skype 的最终池灾难恢复</span><span class="sxs-lookup"><span data-stu-id="e888d-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
