---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文讨论如何使用适用于 Microsoft Teams 会议室的恢复工具，该工具用于将过时系统引入支持状态。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117490"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="f14e6-103">使用 Microsoft Teams 会议室恢复工具</span><span class="sxs-lookup"><span data-stu-id="f14e6-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="f14e6-104">本文讨论如何使用适用于 Microsoft Teams 会议室的恢复工具，该工具用于将过时系统引入支持状态。</span><span class="sxs-lookup"><span data-stu-id="f14e6-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="f14e6-105">当 Microsoft Teams 会议室控制台显示"系统配置已过期"错误，或在执行按钮重置出厂还原之前，应应用 [此工具](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。</span><span class="sxs-lookup"><span data-stu-id="f14e6-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f14e6-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f14e6-106">Prerequisites</span></span>

<span data-ttu-id="f14e6-107">下载最新的 [Microsoft Teams 会议室安装包](https://go.microsoft.com/fwlink/?linkid=851168) ，并解压缩到可供 Microsoft Teams 会议室设备访问的 U 盘或网络共享。</span><span class="sxs-lookup"><span data-stu-id="f14e6-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="f14e6-108">可以通过多种方法从 MSI 提取文件。</span><span class="sxs-lookup"><span data-stu-id="f14e6-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="f14e6-109">提取所有文件并保留其目录结构的任何机制都是可接受的。</span><span class="sxs-lookup"><span data-stu-id="f14e6-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="f14e6-110">其中一种方式是使用 命令，其中 表示 Microsoft Teams Room 安装包的完整路径，表示要提取文件的文件夹 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="f14e6-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="f14e6-111">运行工具</span><span class="sxs-lookup"><span data-stu-id="f14e6-111">Running the tool</span></span>

1) <span data-ttu-id="f14e6-112">登录到 Microsoft Teams 会议室设备的管理员帐户，并启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f14e6-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="f14e6-113">从 Microsoft Teams 会议室设备验证你能否访问 ，该设备包含在从 Microsoft Teams 会议室安装包中提取 `RecoveryTool.ps1 file` 的文件内。</span><span class="sxs-lookup"><span data-stu-id="f14e6-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="f14e6-114">可以在准备先决条件时所使用的网络共享或 U 盘上找到该工具包。</span><span class="sxs-lookup"><span data-stu-id="f14e6-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="f14e6-115">运行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。</span><span class="sxs-lookup"><span data-stu-id="f14e6-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="f14e6-116">若要执行恢复出厂设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f14e6-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="f14e6-117">当脚本提示时，请选择选项 2： **重置**。</span><span class="sxs-lookup"><span data-stu-id="f14e6-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="f14e6-118">如果 BitLocker 已打开，请按照脚本输出末尾提供的说明禁用它。</span><span class="sxs-lookup"><span data-stu-id="f14e6-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="f14e6-119">执行工厂还原。</span><span class="sxs-lookup"><span data-stu-id="f14e6-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="f14e6-120">打开" **设置"** 应用，然后选择 **"&安全性"**</span><span class="sxs-lookup"><span data-stu-id="f14e6-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="f14e6-121">导航到"恢复 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f14e6-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="f14e6-122">在 **"重置此电脑"下**，选择 **"开始使用"**</span><span class="sxs-lookup"><span data-stu-id="f14e6-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="f14e6-123">选择" **删除所有内容"，** 然后选择" **下一步"和** " **重置"**</span><span class="sxs-lookup"><span data-stu-id="f14e6-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="f14e6-124">如果在 Windows 重置过程中选择了"保留我的文件 **-** 删除应用和设置，但保留个人文件"选项，Microsoft Teams 会议室设备可能变为不可用。</span><span class="sxs-lookup"><span data-stu-id="f14e6-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="f14e6-125">不要选择此选项。</span><span class="sxs-lookup"><span data-stu-id="f14e6-125">Do not select this option.</span></span>
      5. <span data-ttu-id="f14e6-126">系统将多次重新启动。</span><span class="sxs-lookup"><span data-stu-id="f14e6-126">The system will reboot multiple times.</span></span> <span data-ttu-id="f14e6-127">重置完成后，系统将在 OOBE (Windows"开箱即用) 屏幕。</span><span class="sxs-lookup"><span data-stu-id="f14e6-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="f14e6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f14e6-128">See also</span></span>

[<span data-ttu-id="f14e6-129">Microsoft Teams 会议室帮助</span><span class="sxs-lookup"><span data-stu-id="f14e6-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="f14e6-130">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="f14e6-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)