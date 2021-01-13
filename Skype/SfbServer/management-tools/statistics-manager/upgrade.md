---
title: 更新 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：阅读本主题，了解如何升级 Skype for Business Server 的统计信息管理器。
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821762"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="1c618-103">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="1c618-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="1c618-104">**摘要：** 阅读本主题，了解如何升级 Skype for Business Server 的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="1c618-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="1c618-105">本主题介绍如何升级 Skype for Business Server 统计信息管理器的现有安装，这是一个功能强大的工具，可让你实时查看 Skype for Business Server 运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="1c618-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="1c618-106">您可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="1c618-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="1c618-107">有关统计信息管理器和 2.0 版中的新功能，请参阅 Plan [for Statistics Manager for Skype for Business Server](plan.md) and Deploy Statistics Manager for Skype for Business [Server。](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="1c618-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="1c618-108">有两种升级方法：</span><span class="sxs-lookup"><span data-stu-id="1c618-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="1c618-109">**自动升级。**</span><span class="sxs-lookup"><span data-stu-id="1c618-109">**Automated upgrade.**</span></span> <span data-ttu-id="1c618-110">此方法使用自动化脚本。</span><span class="sxs-lookup"><span data-stu-id="1c618-110">This method uses an automated script.</span></span> <span data-ttu-id="1c618-111">这是最简单的方法，应适用于所有升级方案。</span><span class="sxs-lookup"><span data-stu-id="1c618-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="1c618-112">**手动升级。**</span><span class="sxs-lookup"><span data-stu-id="1c618-112">**Manual upgrade.**</span></span> <span data-ttu-id="1c618-113">此方法在自动升级失败这一异常情况下作为备份计划提供。</span><span class="sxs-lookup"><span data-stu-id="1c618-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="1c618-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="1c618-114">Prerequisites</span></span>

<span data-ttu-id="1c618-115">在升级之前，请确保你拥有以下信息：</span><span class="sxs-lookup"><span data-stu-id="1c618-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="1c618-116">活动侦听器证书指纹</span><span class="sxs-lookup"><span data-stu-id="1c618-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="1c618-117">侦听器服务密码 (侦听器和每个代理安装时输入) </span><span class="sxs-lookup"><span data-stu-id="1c618-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="1c618-118">网站的 SSL 证书配置</span><span class="sxs-lookup"><span data-stu-id="1c618-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="1c618-119">自动升级</span><span class="sxs-lookup"><span data-stu-id="1c618-119">Automated upgrade</span></span>

<span data-ttu-id="1c618-120">该脚本将收集当前证书信息和侦听器密码，卸载产品的旧版本，然后安装产品的新版本。</span><span class="sxs-lookup"><span data-stu-id="1c618-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="1c618-121">不会触摸服务器上安装的 Redis 实例，因此缓存中存储的任何数据都将在升级过程中保留。</span><span class="sxs-lookup"><span data-stu-id="1c618-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="1c618-122">将新版本的代理、侦听器和网站的 MSI 文件以及 Update-StatsMan.ps1 脚本放在侦听器计算机的单个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1c618-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="1c618-123">打开管理 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="1c618-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1c618-124">升级侦听器组件：</span><span class="sxs-lookup"><span data-stu-id="1c618-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="1c618-125">统计信息管理器服务密码在传递到安装程序时，将在命令行上以纯文本显示。</span><span class="sxs-lookup"><span data-stu-id="1c618-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="1c618-126">请务必根据需要保护监视器。</span><span class="sxs-lookup"><span data-stu-id="1c618-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="1c618-127">运行脚本时，应提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1c618-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1c618-128">回答是。</span><span class="sxs-lookup"><span data-stu-id="1c618-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="1c618-129">如果侦听器服务正在运行，系统将提示您关闭应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1c618-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="1c618-130">允许应用程序关闭 (将停止统计信息管理器侦听器服务) 。</span><span class="sxs-lookup"><span data-stu-id="1c618-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="1c618-131">继续安装过程。</span><span class="sxs-lookup"><span data-stu-id="1c618-131">Continue the install process.</span></span> <span data-ttu-id="1c618-132">您应该注意到服务密码和证书指纹已预填充。</span><span class="sxs-lookup"><span data-stu-id="1c618-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="1c618-133">如果没有，请添加您保存的值，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1c618-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="1c618-134">打开管理 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="1c618-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1c618-135">升级网站组件：</span><span class="sxs-lookup"><span data-stu-id="1c618-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="1c618-136">运行脚本时，应提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1c618-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1c618-137">回答是。</span><span class="sxs-lookup"><span data-stu-id="1c618-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="1c618-138">如果代理服务正在运行，系统将提示您关闭应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1c618-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="1c618-139">允许应用程序关闭 (StatsMan 代理服务将停止) 。</span><span class="sxs-lookup"><span data-stu-id="1c618-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="1c618-140">继续安装过程。</span><span class="sxs-lookup"><span data-stu-id="1c618-140">Continue the install process.</span></span> <span data-ttu-id="1c618-141">您应该注意到服务密码和证书指纹已预填充。</span><span class="sxs-lookup"><span data-stu-id="1c618-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="1c618-142">如果没有，请添加您保存的值，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1c618-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="1c618-143">打开管理 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="1c618-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1c618-144">升级代理组件：</span><span class="sxs-lookup"><span data-stu-id="1c618-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="1c618-145">运行脚本时，应提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1c618-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1c618-146">回答是。</span><span class="sxs-lookup"><span data-stu-id="1c618-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="1c618-147">继续安装过程。</span><span class="sxs-lookup"><span data-stu-id="1c618-147">Continue the install process.</span></span> <span data-ttu-id="1c618-148">您应注意到网站端口已预填充。</span><span class="sxs-lookup"><span data-stu-id="1c618-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="1c618-149">如果没有，请添加您保存的值，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1c618-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="1c618-150">使用浏览器验证网站是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="1c618-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1c618-151">代理升级可以与 -NoPrompt 开关一起使用。</span><span class="sxs-lookup"><span data-stu-id="1c618-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="1c618-152">这将允许卸载/安装过程以静默方式运行，从而允许 PSExec 等工具在大量服务器上远程运行升级。</span><span class="sxs-lookup"><span data-stu-id="1c618-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="1c618-153">手动升级</span><span class="sxs-lookup"><span data-stu-id="1c618-153">Manual upgrade</span></span>

<span data-ttu-id="1c618-154">如果由于某种原因，自动升级失败，则始终可以按如下方式执行手动升级：</span><span class="sxs-lookup"><span data-stu-id="1c618-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="1c618-155">在侦听器计算机上，如果侦听器、网站和代理 (通过"程序和功能"控制面板) 安装在此服务器上，请卸载它。</span><span class="sxs-lookup"><span data-stu-id="1c618-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="1c618-156">保留 Redis 安装，以便缓存中的数据随后在升级过程中得到维护。</span><span class="sxs-lookup"><span data-stu-id="1c618-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="1c618-157">安装组件的新版本，包括在系统提示时保存的值。</span><span class="sxs-lookup"><span data-stu-id="1c618-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="1c618-158">有关安装组件的信息，请参阅部署 [统计信息管理器](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="1c618-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="1c618-159">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="1c618-159">For more information</span></span>
<span data-ttu-id="1c618-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="1c618-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="1c618-161">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1c618-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="1c618-162">Skype for Business Server 的统计信息管理器规划</span><span class="sxs-lookup"><span data-stu-id="1c618-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="1c618-163">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="1c618-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="1c618-164">对 Skype for Business Server 的统计信息管理器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="1c618-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
