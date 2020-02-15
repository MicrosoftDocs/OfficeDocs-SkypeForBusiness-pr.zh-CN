---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何安装 Skype for Business Server 安装所需的管理工具。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018263"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="3b22b-104">在 Skype for Business Server 中安装管理工具</span><span class="sxs-lookup"><span data-stu-id="3b22b-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="3b22b-105">**摘要：** 了解如何安装 Skype for business Server 安装所需的管理工具。</span><span class="sxs-lookup"><span data-stu-id="3b22b-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="3b22b-106">从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。</span><span class="sxs-lookup"><span data-stu-id="3b22b-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3b22b-107">管理工具包括拓扑生成器和 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3b22b-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="3b22b-108">必须在拓扑中至少一台服务器上或运行 Skype for Business Server 支持的 Windows OS 版本的64位管理工作站上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="3b22b-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="3b22b-109">您可以按任意顺序执行步骤1至5。</span><span class="sxs-lookup"><span data-stu-id="3b22b-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="3b22b-110">但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="3b22b-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="3b22b-111">安装管理工具是第3步（共8步）。</span><span class="sxs-lookup"><span data-stu-id="3b22b-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="3b22b-113">安装 Skype for Business Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="3b22b-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="3b22b-114">Skype for business Server 的安装媒体提供了灵活的体验。</span><span class="sxs-lookup"><span data-stu-id="3b22b-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="3b22b-115">当您首次运行 setup.exe 时，安装的唯一工具是 Skype for Business Server 部署向导和 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3b22b-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3b22b-116">通过使用这两个工具（称为核心组件），可以继续安装过程，但不提供整个 Skype for Business Server 环境的主要功能。</span><span class="sxs-lookup"><span data-stu-id="3b22b-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="3b22b-117">安装核心组件后，将自动启动部署向导。</span><span class="sxs-lookup"><span data-stu-id="3b22b-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="3b22b-118">"部署向导" 中的 "**安装管理工具**" 一节安装了 Skype For Business Server 拓扑生成器和 skype For Business server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="3b22b-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b22b-119">每个 Skype for Business Server 环境都必须至少有一台安装了管理工具的服务器。</span><span class="sxs-lookup"><span data-stu-id="3b22b-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="3b22b-120">观看**安装管理工具**的视频步骤：</span><span class="sxs-lookup"><span data-stu-id="3b22b-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="3b22b-121">从部署向导安装 Skype for Business Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="3b22b-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="3b22b-122">插入 Skype for Business Server 安装媒体。</span><span class="sxs-lookup"><span data-stu-id="3b22b-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="3b22b-123">如果安装程序未自动开始，请双击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="3b22b-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="3b22b-124">安装介质需要 Microsoft Visual c + + 才能运行。</span><span class="sxs-lookup"><span data-stu-id="3b22b-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="3b22b-125">将弹出一个对话框，询问您是否要安装此对话框。</span><span class="sxs-lookup"><span data-stu-id="3b22b-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="3b22b-126">单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b22b-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="3b22b-127">通过使用 "智能安装" （Skype for Business Server 中的一项新功能），您可以连接到 Internet 以在安装过程中检查是否有更新。</span><span class="sxs-lookup"><span data-stu-id="3b22b-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="3b22b-128">这样可以确保在安装时有最新的产品更新，从而提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="3b22b-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="3b22b-129">单击 **“安装”**，开始安装。</span><span class="sxs-lookup"><span data-stu-id="3b22b-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="3b22b-130">仔细阅读许可协议，如果您同意，请选择 "**我接受许可协议中的条款**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3b22b-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="3b22b-131">Skype for Business Server 核心组件将安装在服务器上。</span><span class="sxs-lookup"><span data-stu-id="3b22b-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="3b22b-132">核心组件由以下部分组成，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="3b22b-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![应用程序屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="3b22b-134">**Skype For Business Server 部署向导**提供用于安装 Skype for Business Server 的各种组件的启动板的部署程序。</span><span class="sxs-lookup"><span data-stu-id="3b22b-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="3b22b-135">**Skype For Business Server 命令行管理程序**允许管理 Skype for Business Server 的预配置 PowerShell 程序。</span><span class="sxs-lookup"><span data-stu-id="3b22b-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="3b22b-136">核心组件的安装完成后，Skype for Business Server 部署向导将自动启动，如图中所示。</span><span class="sxs-lookup"><span data-stu-id="3b22b-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="3b22b-138">除了核心组件之外，还需要在环境中的至少一台服务器上安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="3b22b-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="3b22b-139">单击 "部署向导" 上的 "**安装管理工具**"。</span><span class="sxs-lookup"><span data-stu-id="3b22b-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="3b22b-140">单击“下一步”\*\*\*\* 开始安装。</span><span class="sxs-lookup"><span data-stu-id="3b22b-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="3b22b-141">安装完成后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="3b22b-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="3b22b-142">管理工具现已添加到服务器中，如图所示。</span><span class="sxs-lookup"><span data-stu-id="3b22b-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="3b22b-144">**Skype For Business Server 拓扑生成器**用于生成、部署和管理拓扑的程序。</span><span class="sxs-lookup"><span data-stu-id="3b22b-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="3b22b-145">**Skype For Business Server 控制面板**用于管理安装的程序。</span><span class="sxs-lookup"><span data-stu-id="3b22b-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

