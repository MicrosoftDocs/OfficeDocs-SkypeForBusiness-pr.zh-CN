---
title: 在 Skype for Business Server 中部署配对前端池进行灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可能决定使用配对的前端池来提供灾难恢复保护，但这不是一项要求。
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830602"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="78f9d-103">在 Skype for Business Server 中部署配对前端池进行灾难恢复</span><span class="sxs-lookup"><span data-stu-id="78f9d-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="78f9d-104">您可能决定使用配对的前端池来提供灾难恢复保护，但这不是一项要求。</span><span class="sxs-lookup"><span data-stu-id="78f9d-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="78f9d-105">您可以使用拓扑生成器轻松部署配对前端池的灾难恢复拓扑。</span><span class="sxs-lookup"><span data-stu-id="78f9d-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="78f9d-106">部署配对前端池</span><span class="sxs-lookup"><span data-stu-id="78f9d-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="78f9d-107">如果池是新的且尚未定义，则使用拓扑生成器创建池。</span><span class="sxs-lookup"><span data-stu-id="78f9d-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="78f9d-108">在拓扑生成器中，右键单击两个池之一，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="78f9d-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="78f9d-109">在左侧窗格中单击“复原”，然后在右侧窗格中选择“关联的备份池”。</span><span class="sxs-lookup"><span data-stu-id="78f9d-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="78f9d-p101">在“关联的备份池”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。</span><span class="sxs-lookup"><span data-stu-id="78f9d-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="78f9d-112">选择“语音的自动故障转移和故障回复”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="78f9d-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="78f9d-113">当您查看该池的详细信息时，关联的池现在显示在“复原”下的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="78f9d-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="78f9d-114">使用拓扑生成器发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="78f9d-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="78f9d-115">如果尚未部署两个池，请立即部署它们，配置随即完成。</span><span class="sxs-lookup"><span data-stu-id="78f9d-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="78f9d-116">可以跳过此过程的最后步骤。</span><span class="sxs-lookup"><span data-stu-id="78f9d-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="78f9d-117">但是，如果在定义配对关系之前已部署池，则必须完成以下最终步骤。</span><span class="sxs-lookup"><span data-stu-id="78f9d-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="78f9d-118">在两个池的每个前端服务器上，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="78f9d-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="78f9d-119">这将配置确保备份配对正常运行所需的其他服务。</span><span class="sxs-lookup"><span data-stu-id="78f9d-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="78f9d-120">一旦引导程序完成在两个池中每个前端服务器上安装备份配对所需的组件后，请确保重新应用之前在两个池中这些前端服务器上应用的任何现有累积更新，然后继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="78f9d-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="78f9d-121">在 Skype for Business Server 命令行管理程序 命令提示符下，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="78f9d-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="78f9d-122">通过以下 cmdlet 强制两个池的用户和会议数据相互同步：</span><span class="sxs-lookup"><span data-stu-id="78f9d-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="78f9d-123">同步数据可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="78f9d-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="78f9d-124">您可以使用以下 cmdlet 检查同步状态。</span><span class="sxs-lookup"><span data-stu-id="78f9d-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="78f9d-125">确保两个方向的状态都稳定。</span><span class="sxs-lookup"><span data-stu-id="78f9d-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="78f9d-126">" **语音的** 自动故障转移和故障回复"选项以及拓扑生成器中的关联时间间隔仅适用于 Lync Server 中引入的语音恢复功能。</span><span class="sxs-lookup"><span data-stu-id="78f9d-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="78f9d-127">选择此选项并不意味着本文档中讨论的池故障转移将自动执行。</span><span class="sxs-lookup"><span data-stu-id="78f9d-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="78f9d-128">池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78f9d-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78f9d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78f9d-129">See also</span></span>

[<span data-ttu-id="78f9d-130">Skype for Business Server 中的前端池灾难恢复</span><span class="sxs-lookup"><span data-stu-id="78f9d-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
