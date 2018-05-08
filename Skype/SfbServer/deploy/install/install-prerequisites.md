---
title: Skype for Business Server 2015 的安装先决条件
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要： 了解有关的服务器和服务器角色的业务服务器 2015年安装 Skype 之前必须配置。 下载免费试用版 Skype 业务服务器 2015 从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 6d11b83cf760b47072bca743b6fe3b5fac3794d9
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="c7ca6-104">Skype for Business Server 2015 的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="c7ca6-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7ca6-105">**摘要：**了解有关服务器和服务器角色，则必须配置为业务服务器 2015年安装 Skype。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="c7ca6-106">下载[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)中的业务服务器 2015 Skype 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="c7ca6-107">安装必备软件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="c7ca6-108">这些要求基于服务器将在拓扑中承担的角色。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="c7ca6-109">第 1 步至第 5 步可以按任意顺序执行。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="c7ca6-110">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="c7ca6-111">安装必备软件是 8 个步骤中的第 1 步。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="c7ca6-113">设置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="c7ca6-113">Setup Windows Server</span></span>

<span data-ttu-id="c7ca6-114">业务服务器 2015年的 Skype 需要 Windows Server 操作系统和大量的必备组件，才能安装。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="c7ca6-115">有关规划必备组件的详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="c7ca6-p105">此过程使用 Windows Server 2012 R2。如果您要使用其他版本的 Windows Server，该过程可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c7ca6-118">在开始之前，请确保 Windows Server 是使用 Windows Update 保持最新。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="c7ca6-120">观看视频，了解**安装必备组件**的步骤：</span><span class="sxs-lookup"><span data-stu-id="c7ca6-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="c7ca6-121">为前端服务器安装必要的角色和功能</span><span class="sxs-lookup"><span data-stu-id="c7ca6-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="c7ca6-122">打开服务器管理器，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="c7ca6-123">阅读“**开始之前**”页以熟悉如何在 Windows Server 中安装角色和功能，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="c7ca6-124">选择“**基于角色或基于功能的安装**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="c7ca6-125">选择的服务器要安装业务服务器 2015 Skype 并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="c7ca6-126">选择“**Web 服务器 (IIS)**”角色，在必要功能窗口弹出时，单击“**添加功能**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c7ca6-127">请确保将运行业务服务器 2015 Skype 的服务器上都[应业务服务器 2015年部署 Skype 之前安装的软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software)中列出的软件功能。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="c7ca6-128">下面是简短的列表：</span><span class="sxs-lookup"><span data-stu-id="c7ca6-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="c7ca6-129">.NET framework 功能</span><span class="sxs-lookup"><span data-stu-id="c7ca6-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="c7ca6-130">WCF 服务</span><span class="sxs-lookup"><span data-stu-id="c7ca6-130">WCF Services</span></span>
    
   - <span data-ttu-id="c7ca6-131">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="c7ca6-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c7ca6-p107">HTTP 激活需要其他功能。单击选择 HTTP 激活时弹出的警告对话框上的“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="c7ca6-134">媒体基础 （需要用于会议的前端服务器和 Standard Edition server。）</span><span class="sxs-lookup"><span data-stu-id="c7ca6-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="c7ca6-135">远程服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="c7ca6-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="c7ca6-136">角色管理工具</span><span class="sxs-lookup"><span data-stu-id="c7ca6-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="c7ca6-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="c7ca6-137">AD DS</span></span> 
    
   - <span data-ttu-id="c7ca6-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="c7ca6-138">AD LDS</span></span>
    
   - <span data-ttu-id="c7ca6-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="c7ca6-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="c7ca6-140">单击“**下一步**”继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="c7ca6-141">阅读有关 **Web 服务器角色 (IIS)** 的说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="c7ca6-142">选择以下 **Web 服务器 (IIS) 角色服务**。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="c7ca6-143">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="c7ca6-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="c7ca6-144">默认文档</span><span class="sxs-lookup"><span data-stu-id="c7ca6-144">Default Document</span></span>
    
   - <span data-ttu-id="c7ca6-145">目录浏览</span><span class="sxs-lookup"><span data-stu-id="c7ca6-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="c7ca6-146">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="c7ca6-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="c7ca6-147">静态内容</span><span class="sxs-lookup"><span data-stu-id="c7ca6-147">Static Content</span></span>
    
   - <span data-ttu-id="c7ca6-148">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="c7ca6-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="c7ca6-149">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="c7ca6-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="c7ca6-150">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="c7ca6-150">Logging Tools</span></span>
    
   - <span data-ttu-id="c7ca6-151">跟踪</span><span class="sxs-lookup"><span data-stu-id="c7ca6-151">Tracing</span></span>
    
   - <span data-ttu-id="c7ca6-152">性能</span><span class="sxs-lookup"><span data-stu-id="c7ca6-152">Performance</span></span>
    
   - <span data-ttu-id="c7ca6-153">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="c7ca6-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="c7ca6-154">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="c7ca6-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="c7ca6-155">安全性</span><span class="sxs-lookup"><span data-stu-id="c7ca6-155">Security</span></span>
    
   - <span data-ttu-id="c7ca6-156">请求筛选</span><span class="sxs-lookup"><span data-stu-id="c7ca6-156">Request Filtering</span></span>
    
   - <span data-ttu-id="c7ca6-157">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="c7ca6-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="c7ca6-158">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="c7ca6-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="c7ca6-159">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="c7ca6-159">Application Development</span></span>
    
   - <span data-ttu-id="c7ca6-160">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="c7ca6-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="c7ca6-161">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="c7ca6-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="c7ca6-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="c7ca6-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="c7ca6-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="c7ca6-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="c7ca6-164">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="c7ca6-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="c7ca6-165">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="c7ca6-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="c7ca6-166">管理工具</span><span class="sxs-lookup"><span data-stu-id="c7ca6-166">Management Tools</span></span>
    
   - <span data-ttu-id="c7ca6-167">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c7ca6-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="c7ca6-168">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="c7ca6-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="c7ca6-169">单击“**下一步**”继续执行向导。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="c7ca6-170">检查安装选择以确保选中了所有必要组件，然后单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c7ca6-171">Windows Server 2012 R2 不会默认安装必要功能的所有源文件。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="c7ca6-172">如果服务器未连接 Internet，您需要插入 Windows Server 2012 R2 媒体并选择“**指定备用源路径**”以安装必要功能。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="c7ca6-173">源文件位于 sources\sxs 目录中。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="c7ca6-174">例如，如果 Windows Server 2012 R2 媒体在驱动器 D 中，则您将路径设为 `d:\sources\sxs`。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="c7ca6-175">> 很重要，必须从 Windows Update 最新的更新。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="c7ca6-176">如果您没有连接到 Internet，您需要手动安装所有相关更新以及更新所需的必备软件。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="c7ca6-177">当出现对话框表示已完成安装时，您需要重新启动服务器以完成该流程。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="c7ca6-178">再次运行 **Windows Update** 以检查安装的角色和服务是否存在可用更新。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="c7ca6-179">如果您将使用 Skype 的业务 Server Control Panel 在此服务器上还必须安装 Silverlight 然后。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="c7ca6-180">若要安装 Silverlight，请参阅[Microsoft Silverlight](https://www.microsoft.com/silverlight/)。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="c7ca6-181">可通过运行以下 PowerShell 命令来安装必备组件。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="c7ca6-182">注意，该命令会按特定顺序查找源文件。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="c7ca6-183">如果您处于联机状态，该命令可访问 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="c7ca6-184">但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="c7ca6-185">有关使用 PowerShell 安装角色和功能的详细信息，请参阅[安装或卸载角色、 角色服务或功能](https://technet.microsoft.com/en-us/library/hh831809.aspx)和[安装 WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="c7ca6-186">在安装必备软件后，即使是使用 PowerShell 命令执行的，也不要忘记再次运行 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="c7ca6-187">执行前端服务器以外的角色（例如控制器、持久聊天或边缘角色）的服务器具备自己的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="c7ca6-188">有关每种服务器类型所需的确切先决条件的详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ca6-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

