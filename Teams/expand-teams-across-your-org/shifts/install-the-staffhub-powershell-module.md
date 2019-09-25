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
description: 了解如何安装并连接到 Microsoft StaffHub PowerShell 模块的预发布版本。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142030"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="4a41e-103">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="4a41e-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a41e-104">2019年10月1日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="4a41e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="4a41e-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="4a41e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="4a41e-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="4a41e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="4a41e-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="4a41e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="4a41e-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="4a41e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="4a41e-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="4a41e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="4a41e-110">使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块的预发布版本。</span><span class="sxs-lookup"><span data-stu-id="4a41e-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="4a41e-111">你将需要此操作才能[将你的 StaffHub 团队移动到团队](move-staffhub-teams-to-shifts-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4a41e-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="4a41e-112">安装 Microsoft StaffHub PowerShell 模块的预发布版本</span><span class="sxs-lookup"><span data-stu-id="4a41e-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="4a41e-113">以管理员身份打开 Windows PowerShell 3.0 或更高版本。若要执行此操作，请单击 "**开始**"，键入**windows powershell**，右键单击 " **windows powershell**"，然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="4a41e-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4a41e-114">若要获取最新版本的 Windows PowerShell，请参阅[安装 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4a41e-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="4a41e-115">运行以下内容安装 StaffHub PowerShell 模块的预发布版本：</span><span class="sxs-lookup"><span data-stu-id="4a41e-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="4a41e-116">您可能会看到警告消息：</span><span class="sxs-lookup"><span data-stu-id="4a41e-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="4a41e-117">键入`Y`，然后单击`Enter`。</span><span class="sxs-lookup"><span data-stu-id="4a41e-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="4a41e-118">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4a41e-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="4a41e-119">连接到 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="4a41e-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="4a41e-120">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a41e-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="4a41e-121">出现提示时，以全局管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="4a41e-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a41e-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a41e-122">Related topics</span></span>

- [<span data-ttu-id="4a41e-123">Microsoft StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="4a41e-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="4a41e-124">将 Microsoft StaffHub 团队迁移到 Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="4a41e-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
