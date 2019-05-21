---
title: 在 Skype for Business 服务器中安装管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '摘要: 了解如何安装 Skype for Business 服务器安装所需的管理工具。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: b700180a18cf7fcac3cb0353ff302edd1ed78584
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306610"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="929f3-104">在 Skype for Business 服务器中安装管理工具</span><span class="sxs-lookup"><span data-stu-id="929f3-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="929f3-105">**摘要:** 了解如何安装 Skype for Business 服务器安装所需的管理工具。</span><span class="sxs-lookup"><span data-stu-id="929f3-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="929f3-106">从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="929f3-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="929f3-107">管理工具包括拓扑生成器和控制面板。</span><span class="sxs-lookup"><span data-stu-id="929f3-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="929f3-108">管理工具必须安装在拓扑中的至少一台服务器上, 或者在运行 Skype for business Server 支持的 Windows 操作系统版本的64位管理工作站中安装。</span><span class="sxs-lookup"><span data-stu-id="929f3-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="929f3-109">第 1 步至第 5 步可以按任意顺序执行。</span><span class="sxs-lookup"><span data-stu-id="929f3-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="929f3-110">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="929f3-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="929f3-111">安装管理工具是 8 个步骤中的第 3 步。</span><span class="sxs-lookup"><span data-stu-id="929f3-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="929f3-113">安装 Skype for Business 服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="929f3-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="929f3-114">Skype for business 服务器安装媒体提供灵活的体验。</span><span class="sxs-lookup"><span data-stu-id="929f3-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="929f3-115">当您首次运行 setup.exe 时, 安装的唯一工具是 Skype for Business 服务器部署向导和 Skype for business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="929f3-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="929f3-116">通过使用这两个工具 (称为核心组件), 可以继续安装过程, 但不提供整个 Skype for business 服务器环境的主要功能。</span><span class="sxs-lookup"><span data-stu-id="929f3-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="929f3-117">在您安装核心组件后，部署向导将自动启动。</span><span class="sxs-lookup"><span data-stu-id="929f3-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="929f3-118">"**安装管理工具**" 的 "部署向导" 部分安装了 skype For Business 服务器拓扑生成器和 skype For business 服务器 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="929f3-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="929f3-119">每个 Skype for Business 服务器环境必须至少有一台服务器安装了 "管理工具"。</span><span class="sxs-lookup"><span data-stu-id="929f3-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="929f3-120">观看视频，了解**安装管理工具**的步骤：</span><span class="sxs-lookup"><span data-stu-id="929f3-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="929f3-121">从部署向导安装 Skype for business 服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="929f3-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="929f3-122">插入 Skype for Business 服务器安装媒体。</span><span class="sxs-lookup"><span data-stu-id="929f3-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="929f3-123">如果安装未自动开始，请双击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="929f3-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="929f3-p106">安装媒体需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="929f3-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="929f3-127">通过使用 "智能设置" (Skype for Business 服务器中的一项新功能), 您可以连接到 Internet 以在安装过程中检查更新。</span><span class="sxs-lookup"><span data-stu-id="929f3-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="929f3-128">这能确保您在安装时获得最新产品更新，从而提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="929f3-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="929f3-129">单击“**安装**”开始安装。</span><span class="sxs-lookup"><span data-stu-id="929f3-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="929f3-130">仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="929f3-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="929f3-131">Skype for Business 服务器核心组件将安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="929f3-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="929f3-132">核心组件包含以下内容，如图所示。</span><span class="sxs-lookup"><span data-stu-id="929f3-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![“应用程序中的核心组件”屏幕。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="929f3-134">**Skype For Business 服务器部署向导**提供用于安装 Skype for Business Server 的各种组件的启动板的部署程序。</span><span class="sxs-lookup"><span data-stu-id="929f3-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="929f3-135">**Skype For Business 服务器命令行管理程序**允许管理 Skype for Business 服务器的预配置 PowerShell 程序。</span><span class="sxs-lookup"><span data-stu-id="929f3-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="929f3-136">核心组件安装完成后, Skype for Business 服务器部署向导将自动启动, 如图所示。</span><span class="sxs-lookup"><span data-stu-id="929f3-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="929f3-138">除了核心组件之外, 你还需要在环境中的至少一台服务器上安装 Skype for business Server 拓扑生成器和 Skype for business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="929f3-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="929f3-139">单击部署向导上的“**安装管理工具**”。</span><span class="sxs-lookup"><span data-stu-id="929f3-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="929f3-140">单击“**下一步**”开始安装。</span><span class="sxs-lookup"><span data-stu-id="929f3-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="929f3-p109">完成安装后，请单击“**完成**”。管理工具现已添加到服务器中，如图所示。</span><span class="sxs-lookup"><span data-stu-id="929f3-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business 服务器管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="929f3-144">**Skype For Business 服务器拓扑生成器**用于生成、部署和管理拓扑的程序。</span><span class="sxs-lookup"><span data-stu-id="929f3-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="929f3-145">**Skype for Business 服务器控制面板**用于管理安装的程序。</span><span class="sxs-lookup"><span data-stu-id="929f3-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

