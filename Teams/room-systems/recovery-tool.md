---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。
ms.openlocfilehash: 79cdd7b2e3530570033083bdac7089e862f169ce
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909458"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="f32b8-103">使用 Microsoft Teams 会议室恢复工具</span><span class="sxs-lookup"><span data-stu-id="f32b8-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="f32b8-104">本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。</span><span class="sxs-lookup"><span data-stu-id="f32b8-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="f32b8-105">当 Microsoft 团队聊天室控制台显示 "系统配置已过期" 错误或执行按钮重置[出厂还原](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore)之前，应应用此工具。</span><span class="sxs-lookup"><span data-stu-id="f32b8-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f32b8-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f32b8-106">Prerequisites</span></span>

<span data-ttu-id="f32b8-107">下载最新的[Microsoft 团队聊天室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其解压缩到 Microsoft 团队聊天室设备可访问的 USB 记忆棒或网络共享。</span><span class="sxs-lookup"><span data-stu-id="f32b8-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="f32b8-108">从 MSI 中提取文件可以通过多种方式完成。</span><span class="sxs-lookup"><span data-stu-id="f32b8-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="f32b8-109">提取所有文件并保留其目录结构的任何机制都是可接受的。</span><span class="sxs-lookup"><span data-stu-id="f32b8-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="f32b8-110">其中一种方法是使用该命令`msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` ， `PathToMsi`其中表示 Microsoft 团队聊天室安装包的完整路径，并`PathToTarget`表示你希望将文件提取到的文件夹的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f32b8-110">One such way is to use the command `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="f32b8-111">运行工具</span><span class="sxs-lookup"><span data-stu-id="f32b8-111">Running the tool</span></span>

1) <span data-ttu-id="f32b8-112">在 Microsoft 团队聊天室设备上登录到管理员帐户，并启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f32b8-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="f32b8-113">从 Microsoft 团队聊天室设备验证你可以访问的`RecoveryTool.ps1 file`，该设备包含在从 Microsoft 团队聊天室安装包提取的文件中。</span><span class="sxs-lookup"><span data-stu-id="f32b8-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="f32b8-114">在准备必备条件时使用的网络共享或 USB 驱动器上可以找到该工具包。</span><span class="sxs-lookup"><span data-stu-id="f32b8-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="f32b8-115">运行`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="f32b8-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="f32b8-116">如果要执行出厂还原：</span><span class="sxs-lookup"><span data-stu-id="f32b8-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="f32b8-117">当脚本提示时，选择选项2： **Reset**。</span><span class="sxs-lookup"><span data-stu-id="f32b8-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="f32b8-118">如果 BitLocker 已打开，请按照脚本输出末尾提供的说明将其禁用。</span><span class="sxs-lookup"><span data-stu-id="f32b8-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="f32b8-119">执行出厂还原。</span><span class="sxs-lookup"><span data-stu-id="f32b8-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="f32b8-120">打开 "**设置**" 应用，然后选择 "**更新 & 安全性**"</span><span class="sxs-lookup"><span data-stu-id="f32b8-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="f32b8-121">导航到 "**恢复**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f32b8-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="f32b8-122">在 "**重置此电脑**" 下，选择 "**开始**"</span><span class="sxs-lookup"><span data-stu-id="f32b8-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="f32b8-123">选择 "**删除所有内容**" **，然后单击**"**重置**"</span><span class="sxs-lookup"><span data-stu-id="f32b8-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="f32b8-124">系统将重启多次。</span><span class="sxs-lookup"><span data-stu-id="f32b8-124">The system will reboot multiple times.</span></span> <span data-ttu-id="f32b8-125">重置完成后，系统将位于 Windows OOBE 屏幕。</span><span class="sxs-lookup"><span data-stu-id="f32b8-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="f32b8-126">如果您要修复 "过时" 系统，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f32b8-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="f32b8-127">当脚本提示时，选择选项1： "**修复**"。</span><span class="sxs-lookup"><span data-stu-id="f32b8-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="f32b8-128">完成后，重新启动 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="f32b8-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="f32b8-129">它将自动重新启动，并在第二次恢复时完全恢复。</span><span class="sxs-lookup"><span data-stu-id="f32b8-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="f32b8-130">如果**保留我的文件-删除应用和设置，但**在 Windows 重置过程中选中了 "保留你的个人文件" 选项，则 Microsoft 团队聊天室可能会变得不可用的已知问题。</span><span class="sxs-lookup"><span data-stu-id="f32b8-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="f32b8-131">请勿*使用此*选项。</span><span class="sxs-lookup"><span data-stu-id="f32b8-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="f32b8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f32b8-132">See also</span></span>

[<span data-ttu-id="f32b8-133">Microsoft Teams 会议室帮助</span><span class="sxs-lookup"><span data-stu-id="f32b8-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="f32b8-134">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="f32b8-134">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
