---
title: 使用 Skype 的空间系统 v2 恢复工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: 本文讨论如何使用恢复工具 Skype 的空间系统 v2，用来将已过期的系统引入到受支持的状态。
ms.openlocfilehash: 7c7a6188ec1cbd1153c09b768e81789fcffd266e
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="7673e-103">使用 Skype 的空间系统 v2 恢复工具</span><span class="sxs-lookup"><span data-stu-id="7673e-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="7673e-104">本文讨论如何使用恢复工具 Skype 的空间系统 v2，用来将已过期的系统引入到受支持的状态。</span><span class="sxs-lookup"><span data-stu-id="7673e-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="7673e-105">当 Skype 的空间系统 v2 控制台显示"系统配置已过期"错误，您将使用此工具。</span><span class="sxs-lookup"><span data-stu-id="7673e-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="7673e-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="7673e-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="7673e-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="7673e-107">Prerequisites</span></span>

<span data-ttu-id="7673e-108">将最新的[Skype 的空间系统 v2 安装包](https://go.microsoft.com/fwlink/?linkid=851168)下载并解压缩到 USB 内存棒或网络可访问的共享到 Skype 的空间系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="7673e-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="7673e-109">您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="7673e-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="7673e-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="7673e-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="7673e-111">验证 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="7673e-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="7673e-112">登录到管理员帐户转到**设置 > Windows 设置 > 管理登录**从 Skype 的空间系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="7673e-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="7673e-113">此选项将带您到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="7673e-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="7673e-114">登录到管理员帐户，默认管理员帐户被`admin`密码`sfb`。</span><span class="sxs-lookup"><span data-stu-id="7673e-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="7673e-115">单击开始菜单和类型`winver.exe`到搜索框中，单击 \* 结果上的*运行命令*。</span><span class="sxs-lookup"><span data-stu-id="7673e-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="7673e-116">在版本的第二行上的信息窗格后请记数。</span><span class="sxs-lookup"><span data-stu-id="7673e-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="7673e-117">如果显示的版本是 1607年或更早版本，<a href="#Perform">执行恢复</a>的步骤按照前进行<a href="#Windows-up">更新 Windows 在恢复之前</a>步骤中的步骤。</span><span class="sxs-lookup"><span data-stu-id="7673e-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="7673e-118">如果大于 1607年版本显示，请按照只<a href="#Perform">执行一次恢复</a>。</span><span class="sxs-lookup"><span data-stu-id="7673e-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="7673e-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="7673e-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="7673e-120">在恢复之前更新 Windows （如果需要）</span><span class="sxs-lookup"><span data-stu-id="7673e-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="7673e-121">虽然仍以管理员用户身份登录，则启动提升的 Powershell 提示符。</span><span class="sxs-lookup"><span data-stu-id="7673e-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="7673e-122">运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="7673e-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="7673e-123">运行 Windows 更新并为 Windows 1709 安装更新。</span><span class="sxs-lookup"><span data-stu-id="7673e-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="7673e-124">为 1709年更新后完成登录回管理员帐户，并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="7673e-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="7673e-125">此更新可以从链接或使用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="7673e-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="7673e-126">一个可选的步骤，从 Windows Update 安装其他所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="7673e-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="7673e-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="7673e-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="7673e-128">执行恢复</span><span class="sxs-lookup"><span data-stu-id="7673e-128">Perform a recovery</span></span>

1. <span data-ttu-id="7673e-129">登录到管理员帐户上 Skype 的空间系统 v2 设备，并启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7673e-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="7673e-130">从 Skype 的空间系统 v2 设备验证您是否可以访问`RecoveryTool.ps1`文件，其中包括在从 Skype 的空间系统 v2 安装程序包中提取文件。</span><span class="sxs-lookup"><span data-stu-id="7673e-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="7673e-131">工具包可以位于网络共享或准备系统必备组件时使用的 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="7673e-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="7673e-132">运行 Powershell.exe 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="7673e-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="7673e-133">当提示您的脚本选择选项`1:"Repair System"`。</span><span class="sxs-lookup"><span data-stu-id="7673e-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="7673e-134">完成后，重新启动 Skype 的空间系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="7673e-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="7673e-135">它会自动再次重新引导，并提出完全恢复第二次。</span><span class="sxs-lookup"><span data-stu-id="7673e-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="7673e-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="7673e-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="7673e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7673e-137">See also</span></span>


#### 

[<span data-ttu-id="7673e-138">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="7673e-138">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
