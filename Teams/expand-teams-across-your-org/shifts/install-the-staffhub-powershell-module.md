---
title: 安装 StaffHub PowerShell 模块
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何安装并连接到 Microsoft StaffHub PowerShell 模块。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245913"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="31932-103">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="31932-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31932-104">有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。</span><span class="sxs-lookup"><span data-stu-id="31932-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="31932-105">我们 StaffHub 功能构建到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="31932-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="31932-106">如今，团队包括日程管理引进相关应用程序和其他功能将随着时间的推移推出。</span><span class="sxs-lookup"><span data-stu-id="31932-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="31932-107">StaffHub 上 2019 年 10 月 1，将停止的所有用户的工作。</span><span class="sxs-lookup"><span data-stu-id="31932-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="31932-108">尝试打开 StaffHub 的任何人都将显示一条消息，来下载团队。</span><span class="sxs-lookup"><span data-stu-id="31932-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="31932-109">若要了解详细信息，请参阅[Microsoft StaffHub 要停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="31932-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="31932-110">使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="31932-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="31932-111">您将需要此能够通过使用 PowerShell 管理 StaffHub 和移动到的 Microsoft 团队 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="31932-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="31932-112">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="31932-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="31932-113">下载[StaffHub PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)。</span><span class="sxs-lookup"><span data-stu-id="31932-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="31932-114">打开 Windows PowerShell 3.0 或更高版本，以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="31932-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="31932-115">若要执行此操作，单击**开始**，键入**Windows PowerShell**，右键单击**Windows PowerShell**中，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="31932-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="31932-116">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="31932-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="31932-117">检查在输出中的文件夹路径，并确保路径中的所有文件夹都存在您的计算机上，转到下一步之前。</span><span class="sxs-lookup"><span data-stu-id="31932-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="31932-118">如果缺少文件夹，创建它们。</span><span class="sxs-lookup"><span data-stu-id="31932-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="31932-119">运行以下内容，其中&lt;路径&gt;是从步骤 2 在输出中的路径。</span><span class="sxs-lookup"><span data-stu-id="31932-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="31932-120">例如，路径可能类似于 C:\Users\User1\Documents\WindowsPowerShell\Modules。</span><span class="sxs-lookup"><span data-stu-id="31932-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="31932-121">连接到 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="31932-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="31932-122">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="31932-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="31932-123">系统提示时，登录作为全局管理员。</span><span class="sxs-lookup"><span data-stu-id="31932-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31932-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="31932-124">Related topics</span></span>

- [<span data-ttu-id="31932-125">Microsoft StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="31932-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="31932-126">将 Microsoft StaffHub 团队迁移到 Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="31932-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
