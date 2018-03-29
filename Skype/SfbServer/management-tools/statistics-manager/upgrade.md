---
title: Skype for Business Server 2015 的升级统计信息管理器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要： 阅读本主题，了解如何升级统计管理器为 Skype 业务服务器 2015年。
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="a4b28-103">Skype for Business Server 2015 的升级统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="a4b28-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a4b28-104">**摘要：**阅读本主题，了解如何升级统计管理器为 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="a4b28-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a4b28-105">本主题介绍如何升级现有安装的统计信息管理器为 Skype 业务服务器--允许您查看 Skype 实时业务服务器运行状况和性能数据的强大工具。</span><span class="sxs-lookup"><span data-stu-id="a4b28-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="a4b28-106">可以跨数百个服务器每隔几秒钟轮询性能数据和统计数据管理器网站上可立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="a4b28-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="a4b28-107">有关统计数据管理器和版本 1.1 版中的新增功能的详细信息，请参阅[规划的业务服务器 2015年的 Skype 统计信息经理](plan.md)和[部署业务服务器 2015年的 Skype 统计管理](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b28-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="a4b28-108">有关 1.1 版中解决的已知问题的信息，请参阅 [1.1 版中解决的已知问题](upgrade.md#BKMK_Fixed)。</span><span class="sxs-lookup"><span data-stu-id="a4b28-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="a4b28-109">升级方法有两种：</span><span class="sxs-lookup"><span data-stu-id="a4b28-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="a4b28-110">**自动升级**。</span><span class="sxs-lookup"><span data-stu-id="a4b28-110">**Automated upgrade.**</span></span> <span data-ttu-id="a4b28-111">此方法使用一个自动化的脚本。</span><span class="sxs-lookup"><span data-stu-id="a4b28-111">This method uses an automated script.</span></span> <span data-ttu-id="a4b28-112">它是最简单的方法，并应适用于所有的升级方案。</span><span class="sxs-lookup"><span data-stu-id="a4b28-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="a4b28-113">**手动升级**。</span><span class="sxs-lookup"><span data-stu-id="a4b28-113">**Manual upgrade.**</span></span> <span data-ttu-id="a4b28-114">提供此方法是在不寻常的情况下，自动的升级失败的备份计划。</span><span class="sxs-lookup"><span data-stu-id="a4b28-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="a4b28-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="a4b28-115">Prerequisites</span></span>

<span data-ttu-id="a4b28-116">在升级之前，务必获得以下信息：</span><span class="sxs-lookup"><span data-stu-id="a4b28-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="a4b28-117">活动侦听器证书指纹</span><span class="sxs-lookup"><span data-stu-id="a4b28-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="a4b28-118">侦听器服务密码（在安装侦听器和每个代理时输入）</span><span class="sxs-lookup"><span data-stu-id="a4b28-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="a4b28-119">网站的 SSL 证书配置</span><span class="sxs-lookup"><span data-stu-id="a4b28-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="a4b28-120">自动升级</span><span class="sxs-lookup"><span data-stu-id="a4b28-120">Automated upgrade</span></span>

<span data-ttu-id="a4b28-121">脚本将收集您的当前证书信息和侦听器密码，请卸载产品的旧版本，然后安装产品的新版本。</span><span class="sxs-lookup"><span data-stu-id="a4b28-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="a4b28-122">服务器上安装的 Redis 实例将不受影响，因此缓存中存储的任何数据在升级过程中将会保留。</span><span class="sxs-lookup"><span data-stu-id="a4b28-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="a4b28-123">将 MSI 文件的新版本代理、 侦听器和更新 StatsMan.ps1 脚本的网站放到侦听程序计算机上的单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="a4b28-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="a4b28-124">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="a4b28-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a4b28-125">升级侦听器组件：</span><span class="sxs-lookup"><span data-stu-id="a4b28-125">Upgrade the Listener component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> <span data-ttu-id="a4b28-126">统计管理器服务密码将以明文形式在命令行上显示，因为它将传递到安装程序。</span><span class="sxs-lookup"><span data-stu-id="a4b28-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="a4b28-127">必要时请务必遮蔽显示器。</span><span class="sxs-lookup"><span data-stu-id="a4b28-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="a4b28-128">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="a4b28-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a4b28-129">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="a4b28-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="a4b28-130">如果侦听器服务正在运行，系统将提示你关闭该应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="a4b28-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="a4b28-131">允许应用程序关闭 （统计数据管理器侦听器服务将被停止）。</span><span class="sxs-lookup"><span data-stu-id="a4b28-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="a4b28-132">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="a4b28-132">Continue the install process.</span></span> <span data-ttu-id="a4b28-133">您应该会注意到服务密码和证书指纹已预先填充。</span><span class="sxs-lookup"><span data-stu-id="a4b28-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="a4b28-134">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="a4b28-134">If not, add the values you saved before continuing.</span></span>
    
3. <span data-ttu-id="a4b28-135">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="a4b28-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a4b28-136">升级网站组件：</span><span class="sxs-lookup"><span data-stu-id="a4b28-136">Upgrade the Website component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. <span data-ttu-id="a4b28-137">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="a4b28-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a4b28-138">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="a4b28-138">Answer Yes.</span></span>
    
2. <span data-ttu-id="a4b28-139">如果代理服务正在运行，系统将提示你关闭该应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="a4b28-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="a4b28-140">允许该应用程序关闭（StatsMan 代理服务将停止）。</span><span class="sxs-lookup"><span data-stu-id="a4b28-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
3. <span data-ttu-id="a4b28-141">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="a4b28-141">Continue the install process.</span></span> <span data-ttu-id="a4b28-142">您应该会注意到服务密码和证书指纹已预先填充。</span><span class="sxs-lookup"><span data-stu-id="a4b28-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="a4b28-143">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="a4b28-143">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="a4b28-144">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="a4b28-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a4b28-145">升级代理组件：</span><span class="sxs-lookup"><span data-stu-id="a4b28-145">Upgrade the Agent component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. <span data-ttu-id="a4b28-146">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="a4b28-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a4b28-147">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="a4b28-147">Answer Yes.</span></span>
    
2. <span data-ttu-id="a4b28-148">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="a4b28-148">Continue the install process.</span></span> <span data-ttu-id="a4b28-149">您应该会注意到网站端口已预先填充。</span><span class="sxs-lookup"><span data-stu-id="a4b28-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="a4b28-150">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="a4b28-150">If not, add the value you saved before continuing.</span></span>
    
3. <span data-ttu-id="a4b28-151">验证是否能够使用浏览器正常浏览该网站。</span><span class="sxs-lookup"><span data-stu-id="a4b28-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a4b28-152">代理升级时可使用 -NoPrompt 开关。</span><span class="sxs-lookup"><span data-stu-id="a4b28-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="a4b28-153">这将允许卸载/安装过程在无提示的情况下运行，让 PSExec 等工具能够在许多服务器上远程运行升级。</span><span class="sxs-lookup"><span data-stu-id="a4b28-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="a4b28-154">手动升级</span><span class="sxs-lookup"><span data-stu-id="a4b28-154">Manual upgrade</span></span>

<span data-ttu-id="a4b28-155">如果由于某些原因，自动升级失败，您始终可以执行手动升级，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4b28-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="a4b28-156">	在侦听器计算机上，通过“程序和功能”控制面板卸载侦听器、网站和代理（如果安装在此服务器上）。</span><span class="sxs-lookup"><span data-stu-id="a4b28-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="a4b28-157"> 保留安装的 Redis，以便在升级过程中维护缓存中的数据。</span><span class="sxs-lookup"><span data-stu-id="a4b28-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="a4b28-p119">	安装组件的新版本，包括在前面的步骤中出现提示时保存的值。有关安装组件的更多信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="a4b28-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="a4b28-160">1.1 版中解决的已知问题</span><span class="sxs-lookup"><span data-stu-id="a4b28-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="a4b28-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="a4b28-161"></span></span>

<span data-ttu-id="a4b28-162">1.1 版中解决了以下已知问题：</span><span class="sxs-lookup"><span data-stu-id="a4b28-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="a4b28-163">用户界面/服务器/代理的许多非常重要的可靠性和性能的改进</span><span class="sxs-lookup"><span data-stu-id="a4b28-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="a4b28-164">用户界面的主筛选器控件现在排序正确与不同的用例 （已领先人觉得某些服务器系统中时它们是不是）</span><span class="sxs-lookup"><span data-stu-id="a4b28-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="a4b28-165">服务器 - 服务器组件现在将安装在非英语服务器上。</span><span class="sxs-lookup"><span data-stu-id="a4b28-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="a4b28-166">服务器/代理 - 在某些情况下，代理和服务器组件无法安装并显示 .NET 错误，错误的原因是特定版本的 Net 4.0。</span><span class="sxs-lookup"><span data-stu-id="a4b28-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="a4b28-167">此问题已得到解决。</span><span class="sxs-lookup"><span data-stu-id="a4b28-167">This has been resolved.</span></span>
    
- <span data-ttu-id="a4b28-168">代理-扩展 StatsMan 代理程序添加事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="a4b28-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="a4b28-169">安装的服务器不在拓扑中时，代理不再崩溃，现在会在事件日志中记录此错误，同时记录许多其他可能的错误条件。</span><span class="sxs-lookup"><span data-stu-id="a4b28-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="a4b28-170">UI-当不使用客户端计算机连接到相同的工作组或域与统计信息管理器 Web 服务器时，使用 Chrome 浏览器的 Web 客户端将看到多个登录提示。</span><span class="sxs-lookup"><span data-stu-id="a4b28-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="a4b28-171">现在，每个会话只需要登录一次。</span><span class="sxs-lookup"><span data-stu-id="a4b28-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="a4b28-172">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="a4b28-172">For more information</span></span>
<span data-ttu-id="a4b28-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="a4b28-173"></span></span>

<span data-ttu-id="a4b28-174">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="a4b28-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="a4b28-175">为业务服务器 2015年计划为 Skype 统计信息经理</span><span class="sxs-lookup"><span data-stu-id="a4b28-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="a4b28-176">为业务服务器 2015年部署 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="a4b28-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="a4b28-177">解决业务服务器 2015年的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="a4b28-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="a4b28-178">Skype 业务服务器统计信息管理器日志</span><span class="sxs-lookup"><span data-stu-id="a4b28-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

