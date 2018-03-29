---
title: 在 Skype for Business Server 2015 中安装管理工具
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '摘要： 了解如何安装业务服务器 2015 Skype 安装所需的管理工具。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="55c8a-104">在 Skype for Business Server 2015 中安装管理工具</span><span class="sxs-lookup"><span data-stu-id="55c8a-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55c8a-105">**摘要：**了解如何安装业务服务器 2015 Skype 安装所需的管理工具。</span><span class="sxs-lookup"><span data-stu-id="55c8a-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="55c8a-106">有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="55c8a-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="55c8a-107">管理工具包括拓扑生成器和控制面板。</span><span class="sxs-lookup"><span data-stu-id="55c8a-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="55c8a-108">管理工具必须安装在至少一台服务器拓扑中运行业务服务器为 Skype 支持的 Windows 操作系统版本的 64 位管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="55c8a-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="55c8a-109">您可以按照任意顺序完成第 1 步至第 5 步。</span><span class="sxs-lookup"><span data-stu-id="55c8a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="55c8a-110">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="55c8a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="55c8a-111">安装管理工具是 8 个步骤中的第 3 步。</span><span class="sxs-lookup"><span data-stu-id="55c8a-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="55c8a-113">为业务服务器 2015年管理工具安装 Skype</span><span class="sxs-lookup"><span data-stu-id="55c8a-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="55c8a-114">Skype 的业务服务器 2015年的安装媒体提供了灵活的体验。</span><span class="sxs-lookup"><span data-stu-id="55c8a-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="55c8a-115">第一次运行 Setup.exe 时，安装的唯一工具是 Skype 业务服务器部署向导和 Skype 的业务服务器管理程序。</span><span class="sxs-lookup"><span data-stu-id="55c8a-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="55c8a-116">通过使用这两种工具，称为核心组件，您可以继续安装过程中，但它们不提供业务服务器环境总体 Skype 的主要功能。</span><span class="sxs-lookup"><span data-stu-id="55c8a-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="55c8a-117">在您安装核心组件后，部署向导将自动启动。</span><span class="sxs-lookup"><span data-stu-id="55c8a-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="55c8a-118">部署向导**安装管理工具**的标题为的一节安装 Skype 业务服务器控件面板业务服务器拓扑生成器和 Skype。</span><span class="sxs-lookup"><span data-stu-id="55c8a-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="55c8a-119">每一个 Skype 业务服务器环境必须有至少一台服务器安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="55c8a-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="55c8a-120">观看视频，了解**安装管理工具**的步骤：</span><span class="sxs-lookup"><span data-stu-id="55c8a-120">Watch the video steps for **Install administrative tools**:</span></span>
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="55c8a-123">安装 Skype 业务服务器 2015年从部署向导的管理工具</span><span class="sxs-lookup"><span data-stu-id="55c8a-123">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="55c8a-124">插入 Skype 业务服务器 2015年安装媒体。</span><span class="sxs-lookup"><span data-stu-id="55c8a-124">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="55c8a-125">如果安装未自动开始，请双击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="55c8a-125">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="55c8a-p107">安装媒体需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="55c8a-p107">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="55c8a-129">通过使用智能安装程序中的业务服务器 2015，Skype 的新增功能您可以连接到互联网，以在安装过程中检查有更新。</span><span class="sxs-lookup"><span data-stu-id="55c8a-129">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="55c8a-130">这能确保您在安装时获得最新产品更新，从而提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="55c8a-130">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="55c8a-131">单击“**安装**”开始安装。</span><span class="sxs-lookup"><span data-stu-id="55c8a-131">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="55c8a-132">仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="55c8a-132">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="55c8a-133">将在服务器上安装 Skype 业务服务器 2015年核心组件。</span><span class="sxs-lookup"><span data-stu-id="55c8a-133">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="55c8a-134">核心组件包含以下内容，如图所示。</span><span class="sxs-lookup"><span data-stu-id="55c8a-134">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![“应用程序中的核心组件”屏幕。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="55c8a-136">**Skype 业务服务器 2015年部署向导**部署程序的业务服务器 2015年安装 Skype 的各种组件提供启动键盘。</span><span class="sxs-lookup"><span data-stu-id="55c8a-136">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="55c8a-137">**Skype 的业务服务器 2015年管理外壳程序**允许管理业务服务器 2015年的 Skype 的预配置的 PowerShell 程序。</span><span class="sxs-lookup"><span data-stu-id="55c8a-137">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="55c8a-138">核心组件安装完成后，Skype 业务服务器 2015年部署向导将自动启动，如图中所示。</span><span class="sxs-lookup"><span data-stu-id="55c8a-138">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Skype for Business Server 2015 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="55c8a-140">除了核心组件，也需要安装 Skype 业务服务器 2015年拓扑生成器和 Skype 业务服务器 2015年控制面板在环境中的至少一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="55c8a-140">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="55c8a-141">单击部署向导上的“**安装管理工具**”。</span><span class="sxs-lookup"><span data-stu-id="55c8a-141">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="55c8a-142">单击“**下一步**”开始安装。</span><span class="sxs-lookup"><span data-stu-id="55c8a-142">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="55c8a-p110">完成安装后，请单击“**完成**”。管理工具现已添加到服务器中，如图所示。</span><span class="sxs-lookup"><span data-stu-id="55c8a-p110">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 2015 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="55c8a-146">**Skype 业务服务器 2015年拓扑生成器**一种程序，用于生成、 部署和管理拓扑。</span><span class="sxs-lookup"><span data-stu-id="55c8a-146">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="55c8a-147">**Skype 的业务服务器 2015年控制面板**用来管理安装程序。</span><span class="sxs-lookup"><span data-stu-id="55c8a-147">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

