---
title: 手动更新Microsoft Teams 会议室设备
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解如何手动将设备Microsoft Teams 会议室到特定版本。
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117510"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="22347-103">手动更新Microsoft Teams 会议室设备</span><span class="sxs-lookup"><span data-stu-id="22347-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="22347-104">Microsoft Teams 会议室应用通过 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="22347-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="22347-105">从应用程序自动安装应用更新Microsoft Store在夜间维护期间自动安装;这是获取更新的建议方法。</span><span class="sxs-lookup"><span data-stu-id="22347-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="22347-106">但是，在某些情况下，Teams 会议室设备无法从服务器接收Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="22347-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="22347-107">例如，安全策略可能不允许设备连接到 Internet，或者可能不允许从客户端下载Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="22347-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="22347-108">或者，你可能希望在执行设置之前更新设备，在此期间Microsoft Store不可用。</span><span class="sxs-lookup"><span data-stu-id="22347-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="22347-109">如果无法从 Microsoft Store 获取更新，可以使用脱机应用更新 PowerShell 脚本手动将 Teams 会议室 设备更新到较新版本的 Teams 会议室 应用。</span><span class="sxs-lookup"><span data-stu-id="22347-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="22347-110">按照本文中的步骤手动更新Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="22347-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="22347-111">此过程只能使用已安装Teams 会议室更新Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="22347-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="22347-112">它不能用于执行新安装。</span><span class="sxs-lookup"><span data-stu-id="22347-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="22347-113">它还不能用于将应用降级到较旧版本。</span><span class="sxs-lookup"><span data-stu-id="22347-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="22347-114">若要执行新安装 Teams 会议室，请联系设备制造商，了解特定于它的媒体，或参阅[准备安装媒体](console.md#prepare-the-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="22347-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="22347-115">步骤 1：下载脱机应用更新脚本</span><span class="sxs-lookup"><span data-stu-id="22347-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="22347-116">首先，下载最新版本的脱机应用更新脚本。</span><span class="sxs-lookup"><span data-stu-id="22347-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="22347-117">若要下载脚本，请单击 <https://go.microsoft.com/fwlink/?linkid=2151817> 。</span><span class="sxs-lookup"><span data-stu-id="22347-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="22347-118">脚本将下载到设备上的默认下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="22347-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="22347-119">下载的文件可能标记为被Windows。</span><span class="sxs-lookup"><span data-stu-id="22347-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="22347-120">如果需要在不交互的情况下运行脚本，则需要取消阻止脚本。</span><span class="sxs-lookup"><span data-stu-id="22347-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="22347-121">若要取消阻止脚本，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="22347-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="22347-122">在文件资源管理器中右键单击文件</span><span class="sxs-lookup"><span data-stu-id="22347-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="22347-123">单击" **属性"**</span><span class="sxs-lookup"><span data-stu-id="22347-123">Click **Properties**</span></span>
3. <span data-ttu-id="22347-124">选择 **"取消阻止"**</span><span class="sxs-lookup"><span data-stu-id="22347-124">Select **Unblock**</span></span>
4. <span data-ttu-id="22347-125">单击" **确定"**</span><span class="sxs-lookup"><span data-stu-id="22347-125">Click **OK**</span></span>

<span data-ttu-id="22347-126">若要使用 PowerShell 取消阻止脚本，请参阅 [取消阻止文件](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。</span><span class="sxs-lookup"><span data-stu-id="22347-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="22347-127">下载脱机应用更新脚本后，将文件Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="22347-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="22347-128">在设备的管理模式下，可以通过使用 U 盘或从网络文件共享访问文件，将文件转移到设备。</span><span class="sxs-lookup"><span data-stu-id="22347-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="22347-129">请务必记下文件在设备上保存的位置。</span><span class="sxs-lookup"><span data-stu-id="22347-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="22347-130">步骤 2：运行脚本以更新 Teams 会议室 应用</span><span class="sxs-lookup"><span data-stu-id="22347-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="22347-131">脱机应用更新脚本需要从提升的命令提示符下运行，而 Skype 用户 (运行应用的用户) 登录。</span><span class="sxs-lookup"><span data-stu-id="22347-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="22347-132">若要详细了解如何在 Skype 用户仍登录时登录到管理员帐户以使用提升的命令提示符，请参阅切换到管理员模式，以及当 Microsoft Teams 会议室 应用[运行时](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)返回。</span><span class="sxs-lookup"><span data-stu-id="22347-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="22347-133">执行以下操作，从提升的命令提示符运行脚本：</span><span class="sxs-lookup"><span data-stu-id="22347-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="22347-134">切换到管理模式</span><span class="sxs-lookup"><span data-stu-id="22347-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="22347-135">单击"开始"图标，键入 **"命令提示符**"，然后选择" **以管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="22347-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="22347-136">运行以下命令， `<path to script>` 其中包括脚本的完整路径和脚本文件的名称：</span><span class="sxs-lookup"><span data-stu-id="22347-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="22347-137">例如，如果脚本文件位于 中，并且脚本 `C:\Users\Admin\Downloads` 文件名为 `MTR-Update-4.5.6.7.ps1` ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="22347-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="22347-138">允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="22347-138">Allow the script to run.</span></span> <span data-ttu-id="22347-139">完成后，脚本将重新启动Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="22347-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="22347-140">也可使用远程 PowerShell 运行脚本。</span><span class="sxs-lookup"><span data-stu-id="22347-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="22347-141">有关在远程设备上使用远程 PowerShell Teams 会议室，请参阅使用[PowerShell 进行远程管理](rooms-operations.md#remote-management-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="22347-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="22347-142">步骤 3：验证应用已成功更新</span><span class="sxs-lookup"><span data-stu-id="22347-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="22347-143">如果脚本成功运行，设备将重新启动到Teams 会议室应用。</span><span class="sxs-lookup"><span data-stu-id="22347-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="22347-144">如果脚本遇到问题，它将指示命令行上的问题，并记录其输出到文件。</span><span class="sxs-lookup"><span data-stu-id="22347-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="22347-145">按照脚本提供的任何说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="22347-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="22347-146">如果需要联系 Microsoft 支持部门，请确保包括日志文件支持请求。</span><span class="sxs-lookup"><span data-stu-id="22347-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="22347-147">该脚本将提供目标路径日志文件。</span><span class="sxs-lookup"><span data-stu-id="22347-147">The script will provide you with the path to the log file.</span></span>