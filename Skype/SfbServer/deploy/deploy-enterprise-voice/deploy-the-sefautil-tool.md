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
description: 在 Skype for Business 服务器中部署 SEFAUtil 工具。
ms.openlocfilehash: ab0d41990e0c4bf9d4d2abb635ce447180899de8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767495"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="6698f-103">在 Skype for Business 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="6698f-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="6698f-104">在 Skype for Business 服务器中部署 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="6698f-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="6698f-105">若要部署和管理组呼叫，您需要使用 SEFAUtil 工具的 Skype for business 服务器版本。</span><span class="sxs-lookup"><span data-stu-id="6698f-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6698f-106">Microsoft 统一通信托管 API （UCMA）5运行时必须安装在你计划运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="6698f-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="6698f-107">请在此处下载：[统一通信托管 API 5.0 运行时](https://www.microsoft.com/en-us/download/details.aspx?id=47344)。</span><span class="sxs-lookup"><span data-stu-id="6698f-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="6698f-108">你还可以下载 UCMA 5 SDK，其中包括运行时，如下所示： [UCMA 5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345)。</span><span class="sxs-lookup"><span data-stu-id="6698f-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="6698f-109">你可以在部署的任何前端池中运行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="6698f-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="6698f-110">若要运行 SEFAUtil 工具，必须从受信任的应用程序计算机上的 "Skype for Business 部署" 向导中运行步骤1、2和3。</span><span class="sxs-lookup"><span data-stu-id="6698f-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="6698f-111">SEFAUtil 要求存在本地配置存储以及证书。</span><span class="sxs-lookup"><span data-stu-id="6698f-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6698f-112">有关运行 SEFAUtil 的更多详细信息，请参阅博客文章 "[如何获取 SEFAUtil 运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。</span><span class="sxs-lookup"><span data-stu-id="6698f-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="6698f-113">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6698f-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="6698f-114">登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="6698f-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="6698f-115">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6698f-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6698f-116">SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="6698f-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="6698f-117">如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="6698f-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="6698f-118">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6698f-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="6698f-119">池 FQDN：将托管 SEFAUtil 应用程序（通常是 Skype for business 前端服务器或池）的服务器或池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6698f-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="6698f-120">池注册机构 FQDN：与此应用程序池关联的 Skype for business 前端服务器或池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6698f-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="6698f-121">池网站：此池所驻留的网站的网站 ID。</span><span class="sxs-lookup"><span data-stu-id="6698f-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="6698f-p105">将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6698f-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="6698f-124">如有需要，您可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="6698f-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="6698f-p106">启用包含您的更改的拓扑。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6698f-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="6698f-127">如果尚未安装，请从[该位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)下载 SEFAUtil 工具的 Skype For business 服务器版本，并将其安装在您在步骤3中创建的受信任的应用程序池中。</span><span class="sxs-lookup"><span data-stu-id="6698f-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="6698f-128">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6698f-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="6698f-129">a.</span><span class="sxs-lookup"><span data-stu-id="6698f-129">a.</span></span> <span data-ttu-id="6698f-130">使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="6698f-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="6698f-131">b.</span><span class="sxs-lookup"><span data-stu-id="6698f-131">b.</span></span> <span data-ttu-id="6698f-132">显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="6698f-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="6698f-133">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6698f-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="6698f-134">将显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="6698f-134">The call forwarding settings for the user will be displayed.</span></span>
    

