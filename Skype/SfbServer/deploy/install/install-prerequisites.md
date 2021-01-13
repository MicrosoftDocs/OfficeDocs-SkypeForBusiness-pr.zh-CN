---
title: 安装 Skype for Business Server 的先决条件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要：了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801712"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="6b161-104">安装 Skype for Business Server 的先决条件</span><span class="sxs-lookup"><span data-stu-id="6b161-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="6b161-105">**摘要：** 了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6b161-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="6b161-106">从 Microsoft 评估中心下载 Skype for Business Server [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="6b161-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6b161-107">安装必备组件包括设置 Windows Server，方法为在拓扑中的每台服务器上安装所需的角色和功能。</span><span class="sxs-lookup"><span data-stu-id="6b161-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="6b161-108">要求基于服务器在拓扑中将担任的角色。</span><span class="sxs-lookup"><span data-stu-id="6b161-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="6b161-109">可以按任意顺序执行步骤 1 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="6b161-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="6b161-110">但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="6b161-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="6b161-111">安装必备组件是步骤 1/8。</span><span class="sxs-lookup"><span data-stu-id="6b161-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="6b161-113">设置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="6b161-113">Setup Windows Server</span></span>

<span data-ttu-id="6b161-114">Skype for Business Server 需要 Windows Server 操作系统和许多必备组件才能安装。</span><span class="sxs-lookup"><span data-stu-id="6b161-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="6b161-115">有关规划先决条件的详细信息，请参阅 Skype [for Business Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b161-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="6b161-116">此过程使用 Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="6b161-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="6b161-117">如果使用的是不同版本的 Windows Server，此过程可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="6b161-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6b161-118">开始之前，使用 Windows 更新确保 Windows Server 是最新的。</span><span class="sxs-lookup"><span data-stu-id="6b161-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server 最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="6b161-120">观看安装必备组件 **的视频步骤**：</span><span class="sxs-lookup"><span data-stu-id="6b161-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="6b161-121">为前端服务器安装所需的角色和功能</span><span class="sxs-lookup"><span data-stu-id="6b161-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="6b161-122">可以使用服务器管理器安装所需的角色和功能。</span><span class="sxs-lookup"><span data-stu-id="6b161-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="6b161-123">安装 Skype [for Business Server 的服务器要求中列出的必备软件功能](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b161-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="6b161-124">必需的软件必须位于将运行 Skype for Business Server 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="6b161-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="6b161-125">Windows Server 2012 R2 不会为所需的功能安装所有源文件。</span><span class="sxs-lookup"><span data-stu-id="6b161-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="6b161-126">如果服务器未连接到 Internet，则需要插入 Windows Server 2012 R2 媒体，然后选择"指定备用源路径"以安装所需的功能。</span><span class="sxs-lookup"><span data-stu-id="6b161-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="6b161-127">源文件位于 sources\sxs 目录中。</span><span class="sxs-lookup"><span data-stu-id="6b161-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="6b161-128">例如，如果 Windows Server 2012 R2 媒体位于驱动器 D 中，则您将路径设置为 `d:\sources\sxs` 。</span><span class="sxs-lookup"><span data-stu-id="6b161-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="6b161-129">从 Windows 更新获取最新更新非常重要。</span><span class="sxs-lookup"><span data-stu-id="6b161-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="6b161-130">如果未连接到 Internet，则需要手动安装所有相关更新以及所需更新的任何必备组件。</span><span class="sxs-lookup"><span data-stu-id="6b161-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="6b161-131">当对话框指示安装已完成时，需要重新启动服务器才能完成该过程。</span><span class="sxs-lookup"><span data-stu-id="6b161-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="6b161-132">再次 **运行 Windows** 更新，检查是否对已安装的角色和服务进行了任何更新。</span><span class="sxs-lookup"><span data-stu-id="6b161-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="6b161-133">如果你将在此服务器上使用 Skype for Business Server 控制面板，则还必须安装 Silverlight。</span><span class="sxs-lookup"><span data-stu-id="6b161-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="6b161-134">若要安装 Silverlight，请参阅[Microsoft Silverlight。](https://www.microsoft.com/silverlight/)</span><span class="sxs-lookup"><span data-stu-id="6b161-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="6b161-135">执行前端服务器角色（如控制器、持久聊天或边缘角色）的服务器的先决条件有其自己的先决条件。</span><span class="sxs-lookup"><span data-stu-id="6b161-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="6b161-136">有关每种服务器类型所需的确切先决条件的详细信息，请参阅 [Skype for Business Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b161-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

