---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Microsoft Skype for Business Server 2019 之后，您必须完成几项任务才能配置的业务服务器 2019 以使用 System Center Operations Manager 的 Skype。
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887412"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="084ac-103">配置 SCOM 监控</span><span class="sxs-lookup"><span data-stu-id="084ac-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="084ac-104">迁移到 Skype for Business Server 2019 之后，您必须完成几项任务才能配置的业务服务器 2019 以使用 System Center Operations Manager 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="084ac-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="084ac-105">更新应用于选择用来管理中央发现逻辑的服务器。</span><span class="sxs-lookup"><span data-stu-id="084ac-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="084ac-106">更新中央发现候选服务器注册表项。</span><span class="sxs-lookup"><span data-stu-id="084ac-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="084ac-107">主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。</span><span class="sxs-lookup"><span data-stu-id="084ac-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="084ac-108">下面提供了有关执行上述各项任务的说明。</span><span class="sxs-lookup"><span data-stu-id="084ac-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="084ac-109">更新应用于选择用来管理中央发现逻辑的服务器。</span><span class="sxs-lookup"><span data-stu-id="084ac-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="084ac-110">选择具有 System Center Operations Manager 代理文件安装并配置为候选发现节点的服务器。</span><span class="sxs-lookup"><span data-stu-id="084ac-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="084ac-111">更新应用于该服务器。</span><span class="sxs-lookup"><span data-stu-id="084ac-111">Apply updates to this server.</span></span> <span data-ttu-id="084ac-112">请参阅主题[应用更新](apply-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="084ac-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="084ac-113">更新中央发现候选服务器注册表项。</span><span class="sxs-lookup"><span data-stu-id="084ac-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="084ac-114">在选择用来管理中央发现逻辑服务器上，打开 Windows PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="084ac-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="084ac-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="084ac-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="084ac-116">只要编辑注册表，可能会遇到错误的命令失败如果注册表项已存在。</span><span class="sxs-lookup"><span data-stu-id="084ac-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="084ac-117">如果您遇到此，您可以放心地忽略错误。</span><span class="sxs-lookup"><span data-stu-id="084ac-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="084ac-118">主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="084ac-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="084ac-119">在计算机上已安装 System Center Operations Manager 控制台，展开**管理包对象**，然后选择**对象发现**。</span><span class="sxs-lookup"><span data-stu-id="084ac-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="084ac-120">单击**更改范围**</span><span class="sxs-lookup"><span data-stu-id="084ac-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="084ac-121">从**范围管理包对象**页上，选择**LS 发现候选**。</span><span class="sxs-lookup"><span data-stu-id="084ac-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="084ac-122">重写**LS 发现候选有效值**为与前一过程中选定的候选服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="084ac-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="084ac-123">要完成所做的更改，重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。</span><span class="sxs-lookup"><span data-stu-id="084ac-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

