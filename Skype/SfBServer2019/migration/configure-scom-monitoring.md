---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Microsoft Skype for Business Server 2019 后，必须完成一些任务来配置 Skype for business Server 2019，才能使用 System Center Operations Manager。
ms.openlocfilehash: aa782f2ef51e3397d465b1cd0f914783d371eded
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989587"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="6d43a-103">配置 SCOM 监控</span><span class="sxs-lookup"><span data-stu-id="6d43a-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="6d43a-104">迁移到 Skype for business Server 2019 后，您必须完成一些任务来配置 Skype for Business Server 2019，才能使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="6d43a-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="6d43a-105">将更新应用到选择的服务器以管理集中发现逻辑。</span><span class="sxs-lookup"><span data-stu-id="6d43a-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="6d43a-106">更新中央发现候选服务器注册表项。</span><span class="sxs-lookup"><span data-stu-id="6d43a-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="6d43a-107">将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现节点。</span><span class="sxs-lookup"><span data-stu-id="6d43a-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="6d43a-108">下面提供了有关执行其中每项任务的说明。</span><span class="sxs-lookup"><span data-stu-id="6d43a-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="6d43a-109">将更新应用到选择的服务器以管理集中发现逻辑。</span><span class="sxs-lookup"><span data-stu-id="6d43a-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="6d43a-110">选择安装了 System Center Operations Manager 代理文件的服务器，并将其配置为候选发现节点。</span><span class="sxs-lookup"><span data-stu-id="6d43a-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="6d43a-111">将更新应用到此服务器。</span><span class="sxs-lookup"><span data-stu-id="6d43a-111">Apply updates to this server.</span></span> <span data-ttu-id="6d43a-112">请参阅主题[应用更新](apply-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="6d43a-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="6d43a-113">更新中央发现候选服务器注册表项。</span><span class="sxs-lookup"><span data-stu-id="6d43a-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="6d43a-114">在选择了管理中心发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="6d43a-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="6d43a-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="6d43a-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="6d43a-116">编辑注册表时，如果注册表项已存在，则可能会遇到错误：命令失败。</span><span class="sxs-lookup"><span data-stu-id="6d43a-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="6d43a-117">如果遇到这种情况，您可以安全地忽略该错误。</span><span class="sxs-lookup"><span data-stu-id="6d43a-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="6d43a-118">将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="6d43a-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="6d43a-119">在已安装 System Center Operations Manager 控制台的计算机上，展开 "**管理包对象**"，然后选择 "**对象发现**"。</span><span class="sxs-lookup"><span data-stu-id="6d43a-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="6d43a-120">单击 "**更改范围**"</span><span class="sxs-lookup"><span data-stu-id="6d43a-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="6d43a-121">从 "**作用域管理包对象**" 页面中，选择 "**搜索候选**项"。</span><span class="sxs-lookup"><span data-stu-id="6d43a-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="6d43a-122">将 "**发现候选**项" 的有效值替换为前面过程中所选择的候选服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6d43a-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="6d43a-123">若要完成更改，请重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。</span><span class="sxs-lookup"><span data-stu-id="6d43a-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

