---
title: 设置要在压力和性能的情况下运行负载的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 若要允许用户成功运行压力和性能工具业务服务器 2015年拓扑更改或资源调配 Skype。
ms.openlocfilehash: 446c8d8154992540ffd8bfe18b07af7c54e864fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906639"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="c1e82-103">设置要在压力和性能的情况下运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="c1e82-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="c1e82-104">若要允许用户成功运行压力和性能工具业务服务器 2015年拓扑更改或资源调配 Skype。</span><span class="sxs-lookup"><span data-stu-id="c1e82-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="c1e82-105">根据您现有的设置和配置的业务服务器 2015 Skype 的部署，您可能需要在您的环境中进行某些更改。</span><span class="sxs-lookup"><span data-stu-id="c1e82-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="c1e82-106">以下是这些更改的列表：</span><span class="sxs-lookup"><span data-stu-id="c1e82-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="c1e82-107">设置为无限制的 Windows PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="c1e82-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="c1e82-108">如果您不确定它是什么设置为当前，您可以打开 Skype 的业务 Server 命令行管理程序，并运行此命令：</span><span class="sxs-lookup"><span data-stu-id="c1e82-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="c1e82-109">如果不返回的值不受限制，您将需要运行此下一步：</span><span class="sxs-lookup"><span data-stu-id="c1e82-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="c1e82-110">若要有效地配置 Skype 业务服务器，您将需要：</span><span class="sxs-lookup"><span data-stu-id="c1e82-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="c1e82-111">熟悉您 Skype （如计算机名称、 服务实例、 站点名称和策略） 的业务服务器 2015年拓扑。</span><span class="sxs-lookup"><span data-stu-id="c1e82-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="c1e82-112">分配到组中，创建的用户的一些如响应组智能寻线 (例如，SIP Uri)。</span><span class="sxs-lookup"><span data-stu-id="c1e82-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="c1e82-113">若要从命令行运行脚本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="c1e82-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="c1e82-114">通常情况下，已从此数据包中运行的脚本后，生成跟踪将存储在文件中的相同路径中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="c1e82-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="c1e82-115">没有也命名格式\<scriptname\>$h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="c1e82-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="c1e82-116">因此，如果您在下午 12:15 运行 ArchivingPolicy.ps1，您将获取名为 ArchivingPolicy121500.txt 的日志文件。</span><span class="sxs-lookup"><span data-stu-id="c1e82-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="c1e82-117">虽然我们为您提供了服务器配置这些示例，这取决于您同时修改您的配置和还原或已完成运行负载测试后滚动它。</span><span class="sxs-lookup"><span data-stu-id="c1e82-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

