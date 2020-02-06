---
title: 预配拓扑以在压力和性能方案中运行负载
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 拓扑更改或设置，以允许用户成功运行压力和性能工具。
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816161"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="efeb2-103">预配拓扑以在压力和性能方案中运行负载</span><span class="sxs-lookup"><span data-stu-id="efeb2-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="efeb2-104">Skype for Business Server 2015 拓扑更改或设置，以允许用户成功运行压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="efeb2-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="efeb2-105">你可能需要在你的环境中进行一些更改，具体取决于你的 Skype for business Server 2015 部署的现有设置和配置。</span><span class="sxs-lookup"><span data-stu-id="efeb2-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="efeb2-106">下面列出了这些更改：</span><span class="sxs-lookup"><span data-stu-id="efeb2-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="efeb2-107">将 Windows PowerShell 执行策略设置为 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="efeb2-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="efeb2-108">如果您不确定当前设置的内容，您可以打开 Skype for Business 服务器命令行管理程序并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="efeb2-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="efeb2-109">如果未返回值 "不受限制"，则需要运行以下下一步：</span><span class="sxs-lookup"><span data-stu-id="efeb2-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="efeb2-110">若要有效配置 Skype for Business 服务器，您需要：</span><span class="sxs-lookup"><span data-stu-id="efeb2-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="efeb2-111">熟悉 Skype for Business Server 2015 拓扑（如计算机名、服务实例、站点名称和策略）。</span><span class="sxs-lookup"><span data-stu-id="efeb2-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="efeb2-112">将某些创建的用户分配给组，如 "响应组查寻组" （例如，SIP Uri）。</span><span class="sxs-lookup"><span data-stu-id="efeb2-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="efeb2-113">若要从命令行运行脚本，可以使用：</span><span class="sxs-lookup"><span data-stu-id="efeb2-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="efeb2-114">通常，从该程序包运行脚本后，生成的跟踪将存储在文件中，该文件位于运行脚本的位置所在的同一路径中。</span><span class="sxs-lookup"><span data-stu-id="efeb2-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="efeb2-115">还存在命名格式， \<scriptname\>$h $ m $ s。</span><span class="sxs-lookup"><span data-stu-id="efeb2-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="efeb2-116">因此，如果你在 12:15 PM 运行 ArchivingPolicy，你将获得一个名为 ArchivingPolicy121500 的日志文件。</span><span class="sxs-lookup"><span data-stu-id="efeb2-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="efeb2-117">虽然我们为服务器配置提供了这些示例，但你可以在完成负载测试后修改配置并还原或回退它们。</span><span class="sxs-lookup"><span data-stu-id="efeb2-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

