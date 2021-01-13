---
title: 在 Skype for Business 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在 Skype for Business Server 中部署 SEFAUtil 工具。
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812382"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="89a44-103">在 Skype for Business 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="89a44-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="89a44-104">在 Skype for Business Server 中部署 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="89a44-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="89a44-105">若要部署和管理组内呼叫接听，你需要使用 SEFAUtil 工具的 Skype for Business Server 版本。</span><span class="sxs-lookup"><span data-stu-id="89a44-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="89a44-106">必须在计划运行 SEFAUtil (的任何计算机上安装 UCMA) 5 运行时的 Microsoft 统一通信托管 API。</span><span class="sxs-lookup"><span data-stu-id="89a44-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="89a44-107">在此处下载： [统一通信托管 API 5.0 运行时](https://www.microsoft.com/download/details.aspx?id=47344)。</span><span class="sxs-lookup"><span data-stu-id="89a44-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="89a44-108">还可以在此处下载 UCMA 5 SDK（包括运行时[）：UCMA 5.0 SDK。](https://www.microsoft.com/download/details.aspx?id=47345)</span><span class="sxs-lookup"><span data-stu-id="89a44-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="89a44-109">可以在部署的任何前端池中运行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="89a44-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="89a44-110">若要运行 SEFAUtil 工具，必须在受信任应用程序计算机上从 Skype for Business 部署向导运行步骤 1、2 和 3。</span><span class="sxs-lookup"><span data-stu-id="89a44-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="89a44-111">SEFAUtil 要求存在本地配置存储以及证书。</span><span class="sxs-lookup"><span data-stu-id="89a44-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89a44-112">有关运行 SEFAUtil 的更多详细信息，请参阅博客文章"[如何运行 SEFAutil？"。](https://go.microsoft.com/fwlink/?LinkId=278940)</span><span class="sxs-lookup"><span data-stu-id="89a44-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="89a44-113">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="89a44-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="89a44-114">以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**</span><span class="sxs-lookup"><span data-stu-id="89a44-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="89a44-115">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="89a44-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="89a44-116">SEFAUtil 工具只能在属于受信任应用程序一部分的计算机上应用程序池。</span><span class="sxs-lookup"><span data-stu-id="89a44-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="89a44-117">如果需要，请为应用程序池 SEFAUtil 的前端池定义受信任的池。</span><span class="sxs-lookup"><span data-stu-id="89a44-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="89a44-118">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="89a44-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="89a44-119">池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN (通常是 Skype for Business 前端服务器或池) 。</span><span class="sxs-lookup"><span data-stu-id="89a44-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="89a44-120">池注册器 FQDN：与此域关联的 Skype for Business 前端服务器或池的 FQDN 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="89a44-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="89a44-121">池站点：此池所位于的站点的站点 ID。</span><span class="sxs-lookup"><span data-stu-id="89a44-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="89a44-122">将 SEFAUtil 工具定义为受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="89a44-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="89a44-123">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="89a44-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="89a44-124">如果需要，可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="89a44-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="89a44-125">使用更改启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="89a44-125">Enable the topology with your changes.</span></span> <span data-ttu-id="89a44-126">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="89a44-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="89a44-127">如果尚未下载，请从此位置下载 Skype for Business Server 版本的 SEFAUtil 工具，并安装在你在步骤 3 中创建的受应用程序池服务器上。 [](https://www.microsoft.com/download/details.aspx?id=52631)</span><span class="sxs-lookup"><span data-stu-id="89a44-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="89a44-128">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89a44-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="89a44-129">a.</span><span class="sxs-lookup"><span data-stu-id="89a44-129">a.</span></span> <span data-ttu-id="89a44-130">使用管理员权限从 Windows 命令提示符运行该工具，以显示部署中用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="89a44-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="89a44-131">b.</span><span class="sxs-lookup"><span data-stu-id="89a44-131">b.</span></span> <span data-ttu-id="89a44-132">显示用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="89a44-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="89a44-133">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="89a44-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="89a44-134">将显示用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="89a44-134">The call forwarding settings for the user will be displayed.</span></span>
    

