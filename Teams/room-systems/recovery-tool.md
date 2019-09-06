---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。
ms.openlocfilehash: aded92fac90f20246444419bff19415922175856
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775201"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="cb033-103">使用 Microsoft Teams 会议室恢复工具</span><span class="sxs-lookup"><span data-stu-id="cb033-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="cb033-104">本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。</span><span class="sxs-lookup"><span data-stu-id="cb033-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="cb033-105">当 Microsoft 团队聊天室控制台显示 "系统配置已过期" 错误时，你将使用此工具。</span><span class="sxs-lookup"><span data-stu-id="cb033-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="cb033-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="cb033-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="cb033-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="cb033-107">Prerequisites</span></span>

<span data-ttu-id="cb033-108">下载最新的[Microsoft 团队聊天室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其解压缩到 Microsoft 团队聊天室设备可访问的 USB 记忆棒或网络共享。</span><span class="sxs-lookup"><span data-stu-id="cb033-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="cb033-109">您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="cb033-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="cb033-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="cb033-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="cb033-111">验证 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="cb033-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="cb033-112">通过转到 "**设置"> Windows 设置 "> 管理员**从 Microsoft 团队聊天室设备登录，登录到管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="cb033-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="cb033-113">此选项可将您带入 "登录" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="cb033-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="cb033-114">登录到管理员帐户， `admin`使用密码`sfb`的默认管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="cb033-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="cb033-115">单击 "开始" 菜单并在`winver.exe`搜索框中键入，然后在结果中单击 "\**运行命令*"。</span><span class="sxs-lookup"><span data-stu-id="cb033-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="cb033-116">记下 "信息" 窗格第二行中 "版本" 之后的数字。</span><span class="sxs-lookup"><span data-stu-id="cb033-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="cb033-117">如果显示的版本是1607或更早版本，请在 proceding 之前的<a href="#Windows-up">更新窗口</a>中的步骤，然后再<a href="#Perform">执行恢复</a>步骤。</span><span class="sxs-lookup"><span data-stu-id="cb033-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="cb033-118">如果显示的版本大于1607，请仅按照<a href="#Perform">执行恢复</a>中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="cb033-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="cb033-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="cb033-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="cb033-120">恢复之前更新 Windows （如果需要）</span><span class="sxs-lookup"><span data-stu-id="cb033-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="cb033-121">当仍以管理员用户身份登录时，请启动提升的 Powershell 提示。</span><span class="sxs-lookup"><span data-stu-id="cb033-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="cb033-122">运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="cb033-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="cb033-123">运行 windows 更新并安装适用于 Windows 1709 的更新。</span><span class="sxs-lookup"><span data-stu-id="cb033-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="cb033-124">更新到1709后，请重新登录到管理员帐户并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="cb033-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="cb033-125">更新可能是通过链接或使用 Windows 更新完成的。</span><span class="sxs-lookup"><span data-stu-id="cb033-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="cb033-126">作为可选步骤，请安装 Windows 更新中提供的任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="cb033-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="cb033-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="cb033-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="cb033-128">执行恢复</span><span class="sxs-lookup"><span data-stu-id="cb033-128">Perform a recovery</span></span>

1. <span data-ttu-id="cb033-129">在 Microsoft 团队聊天室设备上登录到管理员帐户，并启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="cb033-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="cb033-130">从 Microsoft 团队聊天室设备验证你是否能够访问该`RecoveryTool.ps1`文件，该设备包含在从 Microsoft 团队聊天室安装包提取的文件中。</span><span class="sxs-lookup"><span data-stu-id="cb033-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="cb033-131">在准备必备条件时使用的网络共享或 USB 驱动器上可以找到该工具包。</span><span class="sxs-lookup"><span data-stu-id="cb033-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="cb033-132">运行 Powershell 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="cb033-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="cb033-133">当脚本选择 "选项`1:"Repair System"`" 时出现提示。</span><span class="sxs-lookup"><span data-stu-id="cb033-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="cb033-134">完成后，重新启动 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="cb033-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="cb033-135">它将自动重新启动，并在第二次恢复时完全恢复。</span><span class="sxs-lookup"><span data-stu-id="cb033-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="cb033-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="cb033-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="cb033-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb033-137">See also</span></span>
 
[<span data-ttu-id="cb033-138">Microsoft Teams 会议室帮助</span><span class="sxs-lookup"><span data-stu-id="cb033-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="cb033-139">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="cb033-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
