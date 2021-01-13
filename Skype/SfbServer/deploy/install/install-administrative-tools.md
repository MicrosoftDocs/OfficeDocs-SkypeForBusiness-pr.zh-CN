---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要：了解如何安装安装 Skype for Business Server 所需的管理工具。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812102"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="caa5a-104">在 Skype for Business Server 中安装管理工具</span><span class="sxs-lookup"><span data-stu-id="caa5a-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="caa5a-105">**摘要：** 了解如何安装安装 Skype for Business Server 所需的管理工具。</span><span class="sxs-lookup"><span data-stu-id="caa5a-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="caa5a-106">从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 位置为：</span><span class="sxs-lookup"><span data-stu-id="caa5a-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="caa5a-107">管理工具包括拓扑生成器和控制面板。</span><span class="sxs-lookup"><span data-stu-id="caa5a-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="caa5a-108">管理工具必须安装在拓扑中的至少一台服务器上，或安装在运行受 Skype for Business Server 支持的 Windows OS 版本的 64 位管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="caa5a-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="caa5a-109">可以按任意顺序执行步骤 1 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="caa5a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="caa5a-110">但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="caa5a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="caa5a-111">安装管理工具是步骤 3/8。</span><span class="sxs-lookup"><span data-stu-id="caa5a-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="caa5a-113">安装 Skype for Business Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="caa5a-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="caa5a-114">Skype for Business Server 的安装媒体提供了灵活的体验。</span><span class="sxs-lookup"><span data-stu-id="caa5a-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="caa5a-115">首次运行 Setup.exe时，唯一安装的工具是 Skype for Business Server 部署向导和 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="caa5a-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="caa5a-116">通过使用这两种工具（称为核心组件）可以继续安装过程，但它们不会为整个 Skype for Business Server 环境提供主要功能。</span><span class="sxs-lookup"><span data-stu-id="caa5a-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="caa5a-117">安装核心组件后，部署向导将自动启动。</span><span class="sxs-lookup"><span data-stu-id="caa5a-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="caa5a-118">部署向导中标题为"安装管理工具"的部分将安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="caa5a-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="caa5a-119">每个 Skype for Business Server 环境都必须至少有一台安装了管理工具的服务器。</span><span class="sxs-lookup"><span data-stu-id="caa5a-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="caa5a-120">观看安装管理工具 **的视频步骤**：</span><span class="sxs-lookup"><span data-stu-id="caa5a-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="caa5a-121">从部署向导安装 Skype for Business Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="caa5a-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="caa5a-122">插入 Skype for Business Server 安装媒体。</span><span class="sxs-lookup"><span data-stu-id="caa5a-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="caa5a-123">如果安装程序不会自动开始，请双击"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="caa5a-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="caa5a-124">安装媒体需要 Microsoft Visual C++ 来运行。</span><span class="sxs-lookup"><span data-stu-id="caa5a-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="caa5a-125">将弹出一个对话框，询问是否要安装它。</span><span class="sxs-lookup"><span data-stu-id="caa5a-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="caa5a-126">单击“是”。</span><span class="sxs-lookup"><span data-stu-id="caa5a-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="caa5a-127">通过使用智能安装（Skype for Business Server 中的一项新功能）可以连接到 Internet 以在安装过程中检查更新。</span><span class="sxs-lookup"><span data-stu-id="caa5a-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="caa5a-128">这通过确保在安装时获得产品的最新更新，从而提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="caa5a-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="caa5a-129">单击 **“安装”**，开始安装。</span><span class="sxs-lookup"><span data-stu-id="caa5a-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="caa5a-130">仔细阅读许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="caa5a-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="caa5a-131">Skype for Business Server 核心组件将安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="caa5a-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="caa5a-132">核心组件由以下内容组成，如图所示。</span><span class="sxs-lookup"><span data-stu-id="caa5a-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    !["应用"屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="caa5a-134">**Skype for Business Server 部署向导** 提供用于安装 Skype for Business Server 各种组件的启动板的部署计划。</span><span class="sxs-lookup"><span data-stu-id="caa5a-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="caa5a-135">**Skype for Business Server 命令行管理程序** 允许管理 Skype for Business Server 的预配置 PowerShell 程序。</span><span class="sxs-lookup"><span data-stu-id="caa5a-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="caa5a-136">核心组件的安装完成后，Skype for Business Server 部署向导将自动启动，如图所示。</span><span class="sxs-lookup"><span data-stu-id="caa5a-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="caa5a-138">除了核心组件之外，你还需要在环境中至少一台服务器上安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="caa5a-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="caa5a-139">单击 **部署向导上的** "安装管理工具"。</span><span class="sxs-lookup"><span data-stu-id="caa5a-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="caa5a-140">单击“下一步”开始安装。</span><span class="sxs-lookup"><span data-stu-id="caa5a-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="caa5a-141">安装完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="caa5a-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="caa5a-142">管理工具现已添加到服务器，如图所示。</span><span class="sxs-lookup"><span data-stu-id="caa5a-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="caa5a-144">**Skype for Business Server 拓扑生成器** 用于构建、部署和管理拓扑的程序。</span><span class="sxs-lookup"><span data-stu-id="caa5a-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="caa5a-145">**Skype for Business Server 控制面板** 用于管理安装的程序。</span><span class="sxs-lookup"><span data-stu-id="caa5a-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

