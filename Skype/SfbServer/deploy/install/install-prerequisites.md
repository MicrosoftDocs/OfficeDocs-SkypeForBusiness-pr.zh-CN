---
title: Skype for Business Server 2015 的安装先决条件
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '摘要： 了解服务器和服务器角色的业务服务器 2015年安装 Skype 之前必须配置。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="86ad1-104">Skype for Business Server 2015 的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="86ad1-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86ad1-105">**摘要：**了解有关服务器和服务器角色的业务服务器 2015年安装 Skype 之前必须配置。</span><span class="sxs-lookup"><span data-stu-id="86ad1-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="86ad1-106">有关从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)业务服务器 2015年下载 Skype 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="86ad1-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="86ad1-107">安装必备软件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="86ad1-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="86ad1-108">这些要求基于服务器将在拓扑中承担的角色。</span><span class="sxs-lookup"><span data-stu-id="86ad1-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="86ad1-109">第 1 步至第 5 步可以按任意顺序执行。</span><span class="sxs-lookup"><span data-stu-id="86ad1-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="86ad1-110">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="86ad1-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="86ad1-111">安装必备软件是 8 个步骤中的第 1 步。</span><span class="sxs-lookup"><span data-stu-id="86ad1-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="86ad1-113">设置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="86ad1-113">Setup Windows Server</span></span>

<span data-ttu-id="86ad1-114">Skype 的业务服务器 2015年要求 Windows 服务器操作系统和多个系统必备组件才能安装。</span><span class="sxs-lookup"><span data-stu-id="86ad1-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="86ad1-115">有关规划系统必备组件的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86ad1-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="86ad1-p105">此过程使用 Windows Server 2012 R2。如果您要使用其他版本的 Windows Server，该过程可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="86ad1-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="86ad1-118">在开始之前，请确保 Windows 服务器是通过 Windows 更新保持最新。</span><span class="sxs-lookup"><span data-stu-id="86ad1-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="86ad1-120">观看视频，了解**安装必备组件**的步骤：</span><span class="sxs-lookup"><span data-stu-id="86ad1-120">Watch the video steps for **install prerequisites**:</span></span>
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="86ad1-123">为前端服务器安装必要的角色和功能</span><span class="sxs-lookup"><span data-stu-id="86ad1-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="86ad1-124">打开服务器管理器，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="86ad1-125">阅读“**开始之前**”页以熟悉如何在 Windows Server 中安装角色和功能，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="86ad1-126">选择“**基于角色或基于功能的安装**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="86ad1-127">选择的服务器要安装 Skype 业务服务器 2015，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="86ad1-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="86ad1-128">选择“**Web 服务器 (IIS)**”角色，在必要功能窗口弹出时，单击“**添加功能**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="86ad1-129">确保软件功能[，应安装之前的业务服务器 2015年部署 Skype 软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software)中列出将运行业务服务器 2015 Skype 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="86ad1-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="86ad1-130">下面是一个简短的列表：</span><span class="sxs-lookup"><span data-stu-id="86ad1-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="86ad1-131">.NET Framework 功能</span><span class="sxs-lookup"><span data-stu-id="86ad1-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="86ad1-132">WCF 服务</span><span class="sxs-lookup"><span data-stu-id="86ad1-132">WCF Services</span></span>
    
   - <span data-ttu-id="86ad1-133">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="86ad1-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86ad1-p108">HTTP 激活需要其他功能。单击选择 HTTP 激活时弹出的警告对话框上的“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="86ad1-136">媒体基础 （所必需的前端服务器和标准版用于会议的服务器）。</span><span class="sxs-lookup"><span data-stu-id="86ad1-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="86ad1-137">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="86ad1-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="86ad1-138">角色管理工具</span><span class="sxs-lookup"><span data-stu-id="86ad1-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="86ad1-139">AD DS</span><span class="sxs-lookup"><span data-stu-id="86ad1-139">AD DS</span></span> 
    
   - <span data-ttu-id="86ad1-140">AD LDS</span><span class="sxs-lookup"><span data-stu-id="86ad1-140">AD LDS</span></span>
    
   - <span data-ttu-id="86ad1-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="86ad1-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="86ad1-142">单击“**下一步**”继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="86ad1-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="86ad1-143">阅读有关 **Web 服务器角色 (IIS)** 的说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="86ad1-144">选择以下 **Web 服务器 (IIS) 角色服务**。</span><span class="sxs-lookup"><span data-stu-id="86ad1-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="86ad1-145">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="86ad1-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="86ad1-146">默认文档</span><span class="sxs-lookup"><span data-stu-id="86ad1-146">Default Document</span></span>
    
   - <span data-ttu-id="86ad1-147">目录浏览</span><span class="sxs-lookup"><span data-stu-id="86ad1-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="86ad1-148">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="86ad1-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="86ad1-149">静态内容</span><span class="sxs-lookup"><span data-stu-id="86ad1-149">Static Content</span></span>
    
   - <span data-ttu-id="86ad1-150">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="86ad1-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="86ad1-151">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="86ad1-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="86ad1-152">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="86ad1-152">Logging Tools</span></span>
    
   - <span data-ttu-id="86ad1-153">跟踪</span><span class="sxs-lookup"><span data-stu-id="86ad1-153">Tracing</span></span>
    
   - <span data-ttu-id="86ad1-154">性能</span><span class="sxs-lookup"><span data-stu-id="86ad1-154">Performance</span></span>
    
   - <span data-ttu-id="86ad1-155">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="86ad1-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="86ad1-156">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="86ad1-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="86ad1-157">安全性</span><span class="sxs-lookup"><span data-stu-id="86ad1-157">Security</span></span>
    
   - <span data-ttu-id="86ad1-158">请求筛选</span><span class="sxs-lookup"><span data-stu-id="86ad1-158">Request Filtering</span></span>
    
   - <span data-ttu-id="86ad1-159">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="86ad1-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="86ad1-160">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="86ad1-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="86ad1-161">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="86ad1-161">Application Development</span></span>
    
   - <span data-ttu-id="86ad1-162">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="86ad1-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="86ad1-163">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="86ad1-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="86ad1-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="86ad1-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="86ad1-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="86ad1-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="86ad1-166">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="86ad1-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="86ad1-167">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="86ad1-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="86ad1-168">管理工具</span><span class="sxs-lookup"><span data-stu-id="86ad1-168">Management Tools</span></span>
    
   - <span data-ttu-id="86ad1-169">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="86ad1-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="86ad1-170">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="86ad1-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="86ad1-171">单击“**下一步**”继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="86ad1-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="86ad1-172">检查安装选择以确保选中了所有必要组件，然后单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="86ad1-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="86ad1-173">Windows Server 2012 R2 不会默认安装必要功能的所有源文件。</span><span class="sxs-lookup"><span data-stu-id="86ad1-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="86ad1-174">如果服务器未连接 Internet，您需要插入 Windows Server 2012 R2 媒体并选择“**指定备用源路径**”以安装必要功能。</span><span class="sxs-lookup"><span data-stu-id="86ad1-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="86ad1-175">源文件位于 sources\sxs 目录中。</span><span class="sxs-lookup"><span data-stu-id="86ad1-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="86ad1-176">例如，如果 Windows Server 2012 R2 媒体在驱动器 D 中，则您将路径设为 `d:\sources\sxs`。</span><span class="sxs-lookup"><span data-stu-id="86ad1-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="86ad1-177">> 很重要，必须从 Windows 更新最新的更新。</span><span class="sxs-lookup"><span data-stu-id="86ad1-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="86ad1-178">如果您没有连接到 Internet，您需要手动安装所有相关更新以及更新所需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="86ad1-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="86ad1-179">当出现对话框表示已完成安装时，您需要重新启动服务器以完成该流程。</span><span class="sxs-lookup"><span data-stu-id="86ad1-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="86ad1-180">再次运行 **Windows Update** 以检查安装的角色和服务是否存在可用更新。</span><span class="sxs-lookup"><span data-stu-id="86ad1-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="86ad1-181">如果您将使用 Skype 业务服务器控件面板在此服务器上，然后还必须安装 Silverlight。</span><span class="sxs-lookup"><span data-stu-id="86ad1-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="86ad1-182">若要安装 Silverlight，请参阅[Microsoft Silverlight](https://www.microsoft.com/silverlight/)。</span><span class="sxs-lookup"><span data-stu-id="86ad1-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="86ad1-183">可通过运行以下 PowerShell 命令来安装必备组件。</span><span class="sxs-lookup"><span data-stu-id="86ad1-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="86ad1-184">注意，该命令会按特定顺序查找源文件。</span><span class="sxs-lookup"><span data-stu-id="86ad1-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="86ad1-185">如果您处于联机状态，该命令可访问 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="86ad1-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="86ad1-186">但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。</span><span class="sxs-lookup"><span data-stu-id="86ad1-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="86ad1-187">有关使用 PowerShell 安装角色和功能的详细信息，请参阅[安装或卸载角色、 角色服务或功能](https://technet.microsoft.com/en-us/library/hh831809.aspx)，并[安装 WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="86ad1-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="86ad1-188">在安装必备软件后，即使是使用 PowerShell 命令执行的，也不要忘记再次运行 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="86ad1-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="86ad1-189">执行前端服务器以外的角色（例如控制器、持久聊天或边缘角色）的服务器具备自己的先决条件。</span><span class="sxs-lookup"><span data-stu-id="86ad1-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="86ad1-190">每个服务器类型所需的精确系统必备组件的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86ad1-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

