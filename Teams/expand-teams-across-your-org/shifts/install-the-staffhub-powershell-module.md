---
title: 安装 StaffHub PowerShell 模块
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何安装和连接到 Microsoft StaffHub PowerShell 模块。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75ed6840b409f391b87759e2004c0f1ea475ce69
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827560"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="da7ec-103">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="da7ec-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da7ec-104">2019年12月31日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="da7ec-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="da7ec-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="da7ec-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="da7ec-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="da7ec-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="da7ec-107">StaffHub 将停止为2019年12月31日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="da7ec-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="da7ec-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="da7ec-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="da7ec-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="da7ec-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="da7ec-110">使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="da7ec-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="da7ec-111">你将需要此操作才能[将你的 StaffHub 团队移动到团队](move-staffhub-teams-to-shifts-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="da7ec-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="da7ec-112">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="da7ec-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="da7ec-113">下载[StaffHub PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftStaffHub)。</span><span class="sxs-lookup"><span data-stu-id="da7ec-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="da7ec-114">以管理员身份打开 Windows PowerShell 3.0 或更高版本。若要执行此操作，请单击 "**开始**"，键入**windows powershell**，右键单击 " **windows powershell**"，然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="da7ec-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="da7ec-115">若要获取最新版本的 Windows PowerShell，请参阅[安装 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="da7ec-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="da7ec-116">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da7ec-116">Run the following:</span></span>

    ```PowerShell
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="da7ec-117">检查输出中的文件夹路径，并确保你的计算机上的所有文件夹都存在于你的计算机上，然后再转到下一步。</span><span class="sxs-lookup"><span data-stu-id="da7ec-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="da7ec-118">如果文件夹丢失，请创建它们。</span><span class="sxs-lookup"><span data-stu-id="da7ec-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="da7ec-119">运行以下内容以允许安装 StaffHub PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="da7ec-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="da7ec-120">运行以下，其中&lt;path&gt;是步骤3的输出中的路径。</span><span class="sxs-lookup"><span data-stu-id="da7ec-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="da7ec-121">例如，路径可能如下所示 C:\Users\User1\Documents\WindowsPowerShell\Modules。</span><span class="sxs-lookup"><span data-stu-id="da7ec-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="da7ec-122">请确保单独运行每个命令。</span><span class="sxs-lookup"><span data-stu-id="da7ec-122">Be sure to run each command separately.</span></span>

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="da7ec-123">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="da7ec-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="da7ec-124">以全局管理员身份打开 Windows PowerShell 3.0 或更高版本，然后运行以下操作：</span><span class="sxs-lookup"><span data-stu-id="da7ec-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="da7ec-125">连接到 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="da7ec-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="da7ec-126">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da7ec-126">Run the following:</span></span>

    ```PowerShell
    Connect-StaffHub
    ```

2. <span data-ttu-id="da7ec-127">出现提示时，以全局管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="da7ec-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da7ec-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="da7ec-128">Related topics</span></span>

- [<span data-ttu-id="da7ec-129">Microsoft StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="da7ec-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="da7ec-130">将 Microsoft StaffHub 团队迁移到 Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="da7ec-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
