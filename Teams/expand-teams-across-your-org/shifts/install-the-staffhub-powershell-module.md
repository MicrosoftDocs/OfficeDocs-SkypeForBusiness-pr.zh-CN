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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464661"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1569c-103">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1569c-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1569c-104">2019年10月1日生效, Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="1569c-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="1569c-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="1569c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="1569c-106">今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="1569c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="1569c-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="1569c-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="1569c-108">任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="1569c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="1569c-109">若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="1569c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="1569c-110">使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="1569c-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="1569c-111">你将需要此方法来使用 PowerShell 管理 StaffHub 并将 StaffHub 团队移动到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="1569c-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1569c-112">安装 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1569c-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="1569c-113">以管理员身份打开 Windows PowerShell 3.0 或更高版本。若要执行此操作, 请单击 "**开始**", 键入**windows powershell**, 右键单击 " **windows powershell**", 然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="1569c-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1569c-114">若要获取最新版本的 Windows PowerShell, 请参阅[安装 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1569c-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="1569c-115">运行以下操作以安装当前稳定版本的 StaffHub PowerShell 模块:</span><span class="sxs-lookup"><span data-stu-id="1569c-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="1569c-116">仅当需要安装最新版本时, 才能运行此命令, 该版本可能比当前稳定版本的 instabilities 多。`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="1569c-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="1569c-117">如果在使用更多 instabilities 安装最新版本的过程中收到错误, 则可以运行:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="1569c-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="1569c-118">您可能会看到警告消息:</span><span class="sxs-lookup"><span data-stu-id="1569c-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="1569c-119">键入`Y` , 然后`Enter`单击。</span><span class="sxs-lookup"><span data-stu-id="1569c-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="1569c-120">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1569c-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1569c-121">连接到 Microsoft StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1569c-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="1569c-122">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1569c-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="1569c-123">出现提示时, 以全局管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="1569c-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1569c-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="1569c-124">Related topics</span></span>

- [<span data-ttu-id="1569c-125">Microsoft StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="1569c-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="1569c-126">将 Microsoft StaffHub 团队迁移到 Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="1569c-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
