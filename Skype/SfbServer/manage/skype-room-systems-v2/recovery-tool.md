---
title: 使用 Skype 会议室系统 v2 恢复工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文讨论如何使用 Skype 会议室系统 v2，您将用于将过期系统导入支持状态恢复工具。
ms.openlocfilehash: fd71fc189b7471e4e315b6602014a967be09f9c0
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="99813-103">使用 Skype 会议室系统 v2 恢复工具</span><span class="sxs-lookup"><span data-stu-id="99813-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="99813-104">本文讨论如何使用 Skype 会议室系统 v2，您将用于将过期系统导入支持状态恢复工具。</span><span class="sxs-lookup"><span data-stu-id="99813-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="99813-105">Skype 会议室系统 v2 控制台将显示"系统配置过期"错误时，应使用此工具。</span><span class="sxs-lookup"><span data-stu-id="99813-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="99813-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="99813-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="99813-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="99813-107">Prerequisites</span></span>

<span data-ttu-id="99813-108">下载最新的[Skype 会议室系统 v2 安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其提取到某个 USB 内存继续有效或网络共享访问 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="99813-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="99813-109">您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="99813-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="99813-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="99813-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="99813-111">验证 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="99813-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="99813-112">转到的管理员帐户登录**设置 > Windows 设置 > 管理员登录**从 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="99813-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="99813-113">此选项将您带到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="99813-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="99813-114">登录到一个管理帐户，默认管理员帐户进行`admin`使用密码`sfb`。</span><span class="sxs-lookup"><span data-stu-id="99813-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="99813-115">单击开始菜单和类型`winver.exe`到搜索框和单击 \**运行命令*的结果。</span><span class="sxs-lookup"><span data-stu-id="99813-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="99813-116">记数后版本第二条直线上的信息窗格。</span><span class="sxs-lookup"><span data-stu-id="99813-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="99813-117">如果显示的版本为 1607年或更早版本，向<a href="#Perform">执行恢复</a>步骤按照之前进行的<a href="#Windows-up">更新 Windows 恢复之前</a>步骤中的步骤。</span><span class="sxs-lookup"><span data-stu-id="99813-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="99813-118">如果显示的版本大于 1607年，请按照仅<a href="#Perform">执行恢复</a>中的步骤。</span><span class="sxs-lookup"><span data-stu-id="99813-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="99813-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="99813-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="99813-120">在恢复之前更新 Windows （如果需要）</span><span class="sxs-lookup"><span data-stu-id="99813-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="99813-121">仍在登录为管理员用户，启动一个提升的 Powershell 提示符。</span><span class="sxs-lookup"><span data-stu-id="99813-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="99813-122">运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="99813-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="99813-123">运行 Windows 更新并安装 Windows 1709 的更新。</span><span class="sxs-lookup"><span data-stu-id="99813-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="99813-124">1709 到更新后完成登录回管理员帐户，并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="99813-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="99813-125">更新可能完成从链接或使用 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="99813-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="99813-126">作为一个可选步骤，安装 Windows Update 提供任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="99813-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="99813-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="99813-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="99813-128">执行恢复</span><span class="sxs-lookup"><span data-stu-id="99813-128">Perform a recovery</span></span>

1. <span data-ttu-id="99813-129">登录到 Skype 会议室系统 v2 设备上的管理帐户并启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="99813-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="99813-130">从 Skype 会议室系统 v2 设备验证您是否能够访问`RecoveryTool.ps1`文件，其中包含在从 Skype 会议室系统 v2 安装程序包中提取的文件。</span><span class="sxs-lookup"><span data-stu-id="99813-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="99813-131">可以使用准备先决条件时的 USB 驱动器或网络共享上找到工具包。</span><span class="sxs-lookup"><span data-stu-id="99813-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="99813-132">运行 Powershell.exe 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="99813-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="99813-133">当提示您的选择脚本选项`1:"Repair System"`。</span><span class="sxs-lookup"><span data-stu-id="99813-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="99813-134">完成后，重新启动 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="99813-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="99813-135">它将重新自动重新启动，并提出完全恢复第二次。</span><span class="sxs-lookup"><span data-stu-id="99813-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="99813-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="99813-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="99813-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99813-137">See also</span></span>


#### 
[<span data-ttu-id="99813-138">Skype 会议室系统版本 2 帮助</span><span class="sxs-lookup"><span data-stu-id="99813-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="99813-139">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="99813-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
