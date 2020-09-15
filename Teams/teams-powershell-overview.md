---
title: Microsoft 团队 PowerShell 概述
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 PowerShell 控件管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814361"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="3bb5e-103">Microsoft 团队 PowerShell 概述</span><span class="sxs-lookup"><span data-stu-id="3bb5e-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="3bb5e-104">Microsoft 团队 PowerShell 是一组用于直接从 PowerShell 命令行管理团队的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="3bb5e-105">在 .NET 标准版中，团队 PowerShell 在 Windows、PowerShell 6 和更高版本上的 PowerShell 5.1 上工作，包括 Azure 外壳程序。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="3bb5e-106">在开始使用 PowerShell 之前，你需要 [安装它](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="3bb5e-107">PowerShell 7 和团队 PowerShell 存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="3bb5e-108">我们建议在解决问题之前使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="3bb5e-109">新闻</span><span class="sxs-lookup"><span data-stu-id="3bb5e-109">Releases</span></span>


<span data-ttu-id="3bb5e-110">在两种版本类型中，团队 PowerShell 在 [PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams) 中可用。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="3bb5e-111">\*\* (GA) 的常规可用性 \*\*：生产的 cmdlet，每月更新。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="3bb5e-112">**公共预览版**：及早访问功能。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="3bb5e-113">更新频率可能比 GA 更频繁。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="3bb5e-114">有关两个版本的功能添加和改进的详细信息，请阅读 [团队 PowerShell 发行说明](teams-powershell-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="3bb5e-115">通过 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="3bb5e-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="3bb5e-116">您将使用团队 PowerShell 模块来完全管理团队：</span><span class="sxs-lookup"><span data-stu-id="3bb5e-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="3bb5e-117">[Microsoft 团队 powershell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：团队 powershell 模块包含用于管理团队、聊天和频道的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="3bb5e-118">最新的 [团队 powershell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/) 已与 Skype For Business Online 连接器集成，为团队 PowerShell 管理提供单个模块。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="3bb5e-119">[Skype for Business Powershell 连接器](https://www.microsoft.com/download/details.aspx?id=39366)： skype For business powershell 连接器现在是团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="3bb5e-120">有关使用这些模块管理团队的完整指南，请参阅使用 [团队 PowerShell 管理团队](teams-powershell-managing-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3bb5e-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="3bb5e-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="3bb5e-121">Related topics</span></span>

[<span data-ttu-id="3bb5e-122">安装团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb5e-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="3bb5e-123">通过团队 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="3bb5e-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="3bb5e-124">团队 PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="3bb5e-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3bb5e-125">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3bb5e-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3bb5e-126">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3bb5e-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="3bb5e-127">使用 Microsoft Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="3bb5e-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
