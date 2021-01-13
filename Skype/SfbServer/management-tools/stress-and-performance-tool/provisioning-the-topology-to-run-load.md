---
title: 设置拓扑以在压力和性能方案中运行负载
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 拓扑更改或设置以允许用户成功运行压力和性能工具。
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814932"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="16490-103">设置拓扑以在压力和性能方案中运行负载</span><span class="sxs-lookup"><span data-stu-id="16490-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="16490-104">Skype for Business Server 2015 拓扑更改或设置以允许用户成功运行压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="16490-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="16490-105">根据 Skype for Business Server 2015 部署的现有设置和配置，可能需要在你的环境中进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="16490-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="16490-106">下面是这些更改的列表：</span><span class="sxs-lookup"><span data-stu-id="16490-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="16490-107">将Windows PowerShell策略设置为"无限制"。</span><span class="sxs-lookup"><span data-stu-id="16490-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="16490-108">如果不确定当前设置什么，可以打开 Skype for Business Server 命令行管理程序 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="16490-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="16490-109">如果未返回 Unrestricted 值，则下一步将需要运行此值：</span><span class="sxs-lookup"><span data-stu-id="16490-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="16490-110">要有效地配置 Skype for Business Server，你需要：</span><span class="sxs-lookup"><span data-stu-id="16490-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="16490-111">熟悉 Skype for Business Server 2015 拓扑 (例如计算机名称、服务实例、站点名称和策略) 。</span><span class="sxs-lookup"><span data-stu-id="16490-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="16490-112">将创建的一些用户分配给组，例如响应组 (例如 SIP URI) 。</span><span class="sxs-lookup"><span data-stu-id="16490-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="16490-113">若要从命令行运行脚本，可以使用：</span><span class="sxs-lookup"><span data-stu-id="16490-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="16490-114">通常，在此包中运行脚本后，生成的跟踪将存储在运行该脚本的同一路径的文件中。</span><span class="sxs-lookup"><span data-stu-id="16490-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="16490-115">还有一种命名格式 \<scriptname\> ，$h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="16490-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="16490-116">因此，如果你在 12ArchivingPolicy.ps1 12：15 运行该日志文件，你将ArchivingPolicy121500.txt。</span><span class="sxs-lookup"><span data-stu-id="16490-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="16490-117">尽管我们已为服务器配置提供了这些示例，但由你负责修改配置，在运行完负载测试后还原或回滚配置。</span><span class="sxs-lookup"><span data-stu-id="16490-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

