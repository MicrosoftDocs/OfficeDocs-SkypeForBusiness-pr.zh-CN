---
title: 在 Skype for Business 2015 中部署 SEFAUtil 工具
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 为业务 Server 部署中 Skype 的 SEFAUtil 工具。
ms.openlocfilehash: f0bb660218b761e513e120f4ea5786eb9278b12a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="90f30-103">在 Skype for Business 2015 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="90f30-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="90f30-104">为业务 Server 部署中 Skype 的 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="90f30-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="90f30-105">部署和管理组呼叫分拣，您需要 Skype 用于业务服务器版本的 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="90f30-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="90f30-106">Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="90f30-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="90f30-107">在部署中，可以在任何前端池中运行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="90f30-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90f30-108">有关运行 SEFAUtil，有关详细信息，请参阅 Technet 博客文章，"[如何获取 SEFAutil 运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。</span><span class="sxs-lookup"><span data-stu-id="90f30-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="90f30-109">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="90f30-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="90f30-110">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="90f30-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="90f30-111">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="90f30-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="90f30-112">SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="90f30-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="90f30-113">如果需要定义打算运行 SEFAUtil 的前端池的受信任应用程序池。</span><span class="sxs-lookup"><span data-stu-id="90f30-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="90f30-114">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="90f30-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="90f30-p102">将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="90f30-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="90f30-117">如有需要，您可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="90f30-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="90f30-p103">启用包含您的更改的拓扑。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="90f30-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="90f30-120">如果尚未准备好，下载 Business Server 版 SEFAUtil 工具 Skype 从[该位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)，并安装您在步骤 3 中创建它的受信任应用程序池。</span><span class="sxs-lookup"><span data-stu-id="90f30-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="90f30-121">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90f30-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="90f30-122">a.</span><span class="sxs-lookup"><span data-stu-id="90f30-122">a.</span></span> <span data-ttu-id="90f30-123">使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="90f30-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="90f30-124">b.</span><span class="sxs-lookup"><span data-stu-id="90f30-124">b.</span></span> <span data-ttu-id="90f30-125">显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="90f30-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="90f30-126">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="90f30-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="90f30-127">将显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="90f30-127">The call forwarding settings for the user will be displayed.</span></span>
    

