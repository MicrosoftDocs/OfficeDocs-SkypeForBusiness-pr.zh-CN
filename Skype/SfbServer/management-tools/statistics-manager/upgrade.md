---
title: 为业务服务器升级的 Skype 的统计信息管理器
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
description: 摘要： 阅读本主题可了解如何针对 Business Server 升级的 Skype 的统计信息管理器。
ms.openlocfilehash: 13bb4a13d05f7c877c5dd62a9c17466389d0e564
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283168"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="1430f-103">为业务服务器升级的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="1430f-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="1430f-104">**摘要：** 阅读本主题可了解如何升级统计信息管理器的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="1430f-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="1430f-105">本主题介绍如何将现有的安装的统计信息管理器的 Skype 升级业务 server — 使用户可以对业务服务器运行状况和性能数据实时查看 Skype 的强大工具。</span><span class="sxs-lookup"><span data-stu-id="1430f-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="1430f-106">可以跨服务器数百每隔几秒钟轮询性能数据，并立即统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="1430f-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="1430f-107">有关统计信息管理器和版本 2.0 中的新功能的详细信息，请参阅[规划用于统计信息管理器中的业务服务器 Skype](plan.md)和[Skype 业务服务器的部署统计信息管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="1430f-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="1430f-108">升级方法有两种：</span><span class="sxs-lookup"><span data-stu-id="1430f-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="1430f-109">**自动升级**。</span><span class="sxs-lookup"><span data-stu-id="1430f-109">**Automated upgrade.**</span></span> <span data-ttu-id="1430f-110">此方法使用自动的脚本。</span><span class="sxs-lookup"><span data-stu-id="1430f-110">This method uses an automated script.</span></span> <span data-ttu-id="1430f-111">它是最简单方法，并应适用于所有升级方案。</span><span class="sxs-lookup"><span data-stu-id="1430f-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="1430f-112">**手动升级**。</span><span class="sxs-lookup"><span data-stu-id="1430f-112">**Manual upgrade.**</span></span> <span data-ttu-id="1430f-113">此方法是作为备份计划自动的升级失败的例外情况下提供。</span><span class="sxs-lookup"><span data-stu-id="1430f-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="1430f-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="1430f-114">Prerequisites</span></span>

<span data-ttu-id="1430f-115">在升级之前，务必获得以下信息：</span><span class="sxs-lookup"><span data-stu-id="1430f-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="1430f-116">活动侦听器证书指纹</span><span class="sxs-lookup"><span data-stu-id="1430f-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="1430f-117">侦听器服务密码（在安装侦听器和每个代理时输入）</span><span class="sxs-lookup"><span data-stu-id="1430f-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="1430f-118">网站的 SSL 证书配置</span><span class="sxs-lookup"><span data-stu-id="1430f-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="1430f-119">自动升级</span><span class="sxs-lookup"><span data-stu-id="1430f-119">Automated upgrade</span></span>

<span data-ttu-id="1430f-120">脚本将收集您的当前证书信息和侦听器密码，请卸载产品的旧版本，然后安装产品的新版本。</span><span class="sxs-lookup"><span data-stu-id="1430f-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="1430f-121">服务器上安装的 Redis 实例将不受影响，因此缓存中存储的任何数据在升级过程中将会保留。</span><span class="sxs-lookup"><span data-stu-id="1430f-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="1430f-122">将代理侦听器，以及更新 StatsMan.ps1 脚本的网站的新版本的 MSI 文件放入侦听器计算机上的单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="1430f-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="1430f-123">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="1430f-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1430f-124">升级侦听器组件：</span><span class="sxs-lookup"><span data-stu-id="1430f-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="1430f-125">它将传递到安装程序将以明文形式命令行上显示统计信息管理器服务的密码。</span><span class="sxs-lookup"><span data-stu-id="1430f-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="1430f-126">必要时请务必遮蔽显示器。</span><span class="sxs-lookup"><span data-stu-id="1430f-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="1430f-127">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1430f-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1430f-128">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="1430f-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="1430f-129">如果侦听器服务正在运行，系统将提示你关闭该应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1430f-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="1430f-130">允许应用程序关闭 （统计信息管理器侦听器服务将停止）。</span><span class="sxs-lookup"><span data-stu-id="1430f-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="1430f-131">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="1430f-131">Continue the install process.</span></span> <span data-ttu-id="1430f-132">您应该会注意到服务密码和证书指纹已预先填充。</span><span class="sxs-lookup"><span data-stu-id="1430f-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="1430f-133">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="1430f-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="1430f-134">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="1430f-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1430f-135">升级网站组件：</span><span class="sxs-lookup"><span data-stu-id="1430f-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="1430f-136">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1430f-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1430f-137">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="1430f-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="1430f-138">如果代理服务正在运行，系统将提示你关闭该应用程序，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="1430f-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="1430f-139">允许该应用程序关闭（StatsMan 代理服务将停止）。</span><span class="sxs-lookup"><span data-stu-id="1430f-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="1430f-140">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="1430f-140">Continue the install process.</span></span> <span data-ttu-id="1430f-141">您应该会注意到服务密码和证书指纹已预先填充。</span><span class="sxs-lookup"><span data-stu-id="1430f-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="1430f-142">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="1430f-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="1430f-143">打开 PowerShell 管理窗口。</span><span class="sxs-lookup"><span data-stu-id="1430f-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="1430f-144">升级代理组件：</span><span class="sxs-lookup"><span data-stu-id="1430f-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="1430f-145">在运行脚本时，系统将提示您卸载产品的旧版本。</span><span class="sxs-lookup"><span data-stu-id="1430f-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="1430f-146">请单击“是”。</span><span class="sxs-lookup"><span data-stu-id="1430f-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="1430f-147">继续执行安装过程。</span><span class="sxs-lookup"><span data-stu-id="1430f-147">Continue the install process.</span></span> <span data-ttu-id="1430f-148">您应该会注意到网站端口已预先填充。</span><span class="sxs-lookup"><span data-stu-id="1430f-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="1430f-149">如果不是，请添加您保存的值，然后继续。</span><span class="sxs-lookup"><span data-stu-id="1430f-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="1430f-150">验证是否能够使用浏览器正常浏览该网站。</span><span class="sxs-lookup"><span data-stu-id="1430f-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1430f-151">代理升级时可使用 -NoPrompt 开关。</span><span class="sxs-lookup"><span data-stu-id="1430f-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="1430f-152">这将允许卸载/安装过程在无提示的情况下运行，让 PSExec 等工具能够在许多服务器上远程运行升级。</span><span class="sxs-lookup"><span data-stu-id="1430f-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="1430f-153">手动升级</span><span class="sxs-lookup"><span data-stu-id="1430f-153">Manual upgrade</span></span>

<span data-ttu-id="1430f-154">如果由于某些原因，自动升级失败，您始终可以执行手动升级，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1430f-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="1430f-155">	在侦听器计算机上，通过“程序和功能”控制面板卸载侦听器、网站和代理（如果安装在此服务器上）。</span><span class="sxs-lookup"><span data-stu-id="1430f-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="1430f-156"> 保留安装的 Redis，以便在升级过程中维护缓存中的数据。</span><span class="sxs-lookup"><span data-stu-id="1430f-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="1430f-p118">	安装组件的新版本，包括在前面的步骤中出现提示时保存的值。有关安装组件的更多信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="1430f-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="1430f-159">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="1430f-159">For more information</span></span>
<span data-ttu-id="1430f-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="1430f-160"></span></span>

<span data-ttu-id="1430f-161">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="1430f-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="1430f-162">规划业务 Server 为统计信息管理器中的 Skype</span><span class="sxs-lookup"><span data-stu-id="1430f-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="1430f-163">为业务 Server 部署的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="1430f-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="1430f-164">解决的 Skype 的统计信息管理器的企业服务器</span><span class="sxs-lookup"><span data-stu-id="1430f-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="1430f-165">Skype for Business Server 统计信息管理器博客</span><span class="sxs-lookup"><span data-stu-id="1430f-165">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

