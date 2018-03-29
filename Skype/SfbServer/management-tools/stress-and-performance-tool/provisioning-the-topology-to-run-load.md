---
title: 资源调配压力和性能的情况下运行负载的拓扑
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 若要允许用户成功地运行压力和性能工具的业务服务器 2015年拓扑的更改或设置 Skype。
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="f9e7f-103">资源调配压力和性能的情况下运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="f9e7f-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="f9e7f-104">若要允许用户成功地运行压力和性能工具的业务服务器 2015年拓扑的更改或设置 Skype。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="f9e7f-105">这取决于您的现有设置和部署的 Skype 业务服务器 2015年的配置，可能需要在您的环境中进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="f9e7f-106">下面是列出的那些更改：</span><span class="sxs-lookup"><span data-stu-id="f9e7f-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="f9e7f-107">Windows PowerShell 执行策略设置为无限制。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="f9e7f-108">如果你不知道它是什么设置为当前，您可以为业务服务器管理外壳程序打开 Skype 和运行此命令：</span><span class="sxs-lookup"><span data-stu-id="f9e7f-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
  ```
  Get-ExecutionPolicy
  ```

  <span data-ttu-id="f9e7f-109">如果未返回的值不受限制，您需要运行这下一步：</span><span class="sxs-lookup"><span data-stu-id="f9e7f-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. <span data-ttu-id="f9e7f-110">有效地配置 Skype 业务服务器，您需要：</span><span class="sxs-lookup"><span data-stu-id="f9e7f-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="f9e7f-111">熟悉您 Skype 业务服务器 2015年拓扑 （例如计算机名称，服务实例、 站点名称和策略）。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="f9e7f-112">分配的部分创建组，用户如响应组查寻组 (例如，SIP Uri)。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="f9e7f-113">若要从命令行运行脚本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="f9e7f-113">To run a script from command line, you can use:</span></span>
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. <span data-ttu-id="f9e7f-114">通常情况下，已经从该包中运行脚本后，生成跟踪都存储在一个文件的同一路径中运行该脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="f9e7f-115">没有命名的格式以及\<scriptname\>$h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="f9e7f-116">因此如果您运行 ArchivingPolicy.ps1 在下午 12:15 时，您将获得名为 ArchivingPolicy121500.txt 日志文件。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="f9e7f-117">同时我们为您的服务器配置中提供了这些示例，这取决于您要同时修改您的配置和恢复，或者将其滑运行负载测试完后。</span><span class="sxs-lookup"><span data-stu-id="f9e7f-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

