---
title: 安装团队 PowerShell 模块的预发布版本
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 请按照以下步骤从 PowerShell 测试库中安装团队 PowerShell 模块的预发布版本。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321765"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="afd4e-103">安装团队 PowerShell 模块的预发布版本</span><span class="sxs-lookup"><span data-stu-id="afd4e-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="afd4e-104">本文介绍如何从[PowerShell 测试库](https://www.poshtestgallery.com/packages/MicrosoftTeams/)安装团队 PowerShell 模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="afd4e-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="afd4e-105">你将需要使用团队 PowerShell 模块的预发布版本，在此方案中，不支持在模块的通用版本中不支持用于管理团队功能的 cmdlet，并且仅适用于预发布版本。</span><span class="sxs-lookup"><span data-stu-id="afd4e-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="afd4e-106">使用这些步骤从 PowerShell 测试库中安装团队 PowerShell 模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="afd4e-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="afd4e-107">不要使用来自[公共 Powershell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/)的模块版本并排从 PowerShell 测试库中安装团队 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="afd4e-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="afd4e-108">按照以下步骤，首先从公共 PowerShell 库中卸载团队 PowerShell 模块，然后从 PowerShell 测试库中安装最新版本的模块。</span><span class="sxs-lookup"><span data-stu-id="afd4e-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="afd4e-109">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="afd4e-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="afd4e-110">启动 Windows PowerShell 模块的新实例。</span><span class="sxs-lookup"><span data-stu-id="afd4e-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="afd4e-111">运行以下内容从公共 PowerShell 库中卸载团队 PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="afd4e-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="afd4e-112">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="afd4e-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="afd4e-113">再次启动 Windows PowerShell 模块，然后运行以下内容以将 PowerShell 测试库注册为受信任的来源：</span><span class="sxs-lookup"><span data-stu-id="afd4e-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="afd4e-114">运行以下内容从 PowerShell 测试库安装最新的团队 PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="afd4e-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="afd4e-115">运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：</span><span class="sxs-lookup"><span data-stu-id="afd4e-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="afd4e-116">从 PowerShell 测试库更新到团队 PowerShell 模块的最新版本</span><span class="sxs-lookup"><span data-stu-id="afd4e-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="afd4e-117">如果已从 PowerShell 测试库中安装了团队 PowerShell 模块，请使用以下步骤更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="afd4e-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="afd4e-118">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="afd4e-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="afd4e-119">启动 Windows PowerShell 模块的新实例。</span><span class="sxs-lookup"><span data-stu-id="afd4e-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="afd4e-120">运行以下内容从 PowerShell 测试库更新当前安装的团队 PowerShell 模块版本：</span><span class="sxs-lookup"><span data-stu-id="afd4e-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="afd4e-121">运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：</span><span class="sxs-lookup"><span data-stu-id="afd4e-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="afd4e-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="afd4e-122">Related topics</span></span>

- [<span data-ttu-id="afd4e-123">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="afd4e-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
