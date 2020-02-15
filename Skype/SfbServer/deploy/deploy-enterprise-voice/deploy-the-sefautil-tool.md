---
title: 在 Skype for Business 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986807"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="f00f5-103">在 Skype for Business 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="f00f5-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="f00f5-104">在 Skype for Business Server 中部署 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="f00f5-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="f00f5-105">若要部署和管理组呼叫应答，您需要使用 Skype for Business Server 版本的 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="f00f5-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f00f5-106">Microsoft 统一通信托管 API （UCMA）5运行时必须安装在您计划运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="f00f5-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="f00f5-107">请在此处下载：[统一通信托管 API 5.0 运行时](https://www.microsoft.com/download/details.aspx?id=47344)。</span><span class="sxs-lookup"><span data-stu-id="f00f5-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="f00f5-108">您还可以从以下位置下载包含运行时的 UCMA 5 SDK： [UCMA 5.0 sdk](https://www.microsoft.com/download/details.aspx?id=47345)。</span><span class="sxs-lookup"><span data-stu-id="f00f5-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="f00f5-109">您可以在部署中的任何前端池中运行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="f00f5-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="f00f5-110">若要运行 SEFAUtil 工具，必须在受信任的应用程序计算机上运行 "Skype for Business 部署" 向导中的步骤1、2和3。</span><span class="sxs-lookup"><span data-stu-id="f00f5-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="f00f5-111">SEFAUtil 要求提供本地配置存储以及证书。</span><span class="sxs-lookup"><span data-stu-id="f00f5-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f00f5-112">有关运行 SEFAUtil 的更多详细信息，请参阅博客文章 "how[to Get SEFAUtil 正在运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。</span><span class="sxs-lookup"><span data-stu-id="f00f5-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="f00f5-113">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="f00f5-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="f00f5-114">登录到 Skype for Business Server 命令行管理程序作为 RTCUniversalServerAdmins 组的成员安装的计算机，或使用**委派安装权限**中所述的必要用户权限。</span><span class="sxs-lookup"><span data-stu-id="f00f5-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f00f5-115">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="f00f5-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f00f5-116">SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="f00f5-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="f00f5-117">如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="f00f5-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="f00f5-118">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="f00f5-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="f00f5-119">池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN （通常为 Skype for business 前端服务器或池）。</span><span class="sxs-lookup"><span data-stu-id="f00f5-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="f00f5-120">池注册器 FQDN：与此应用程序池关联的 Skype for Business 前端服务器或池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f00f5-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="f00f5-121">池网站：此池所驻留的网站的网站 ID。</span><span class="sxs-lookup"><span data-stu-id="f00f5-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="f00f5-122">将 SEFAUtil 工具定义为受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f00f5-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="f00f5-123">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="f00f5-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="f00f5-124">如果需要，可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="f00f5-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="f00f5-125">使用您的更改启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="f00f5-125">Enable the topology with your changes.</span></span> <span data-ttu-id="f00f5-126">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="f00f5-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="f00f5-127">如果还没有，请从[该位置](https://www.microsoft.com/download/details.aspx?id=52631)下载 SEFAUtil 工具的 Skype For business Server 版本，并将其安装在您在步骤3中创建的受信任应用程序池。</span><span class="sxs-lookup"><span data-stu-id="f00f5-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="f00f5-128">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f00f5-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="f00f5-129">a.</span><span class="sxs-lookup"><span data-stu-id="f00f5-129">a.</span></span> <span data-ttu-id="f00f5-130">从带有管理员权限的 Windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="f00f5-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="f00f5-131">b.</span><span class="sxs-lookup"><span data-stu-id="f00f5-131">b.</span></span> <span data-ttu-id="f00f5-132">显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="f00f5-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="f00f5-133">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="f00f5-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="f00f5-134">将显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="f00f5-134">The call forwarding settings for the user will be displayed.</span></span>
    

