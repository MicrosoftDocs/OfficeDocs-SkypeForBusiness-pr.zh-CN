---
title: Microsoft Teams PowerShell 概述
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
description: 了解如何使用 PowerShell 控件管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569018"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="1ac30-103">Microsoft Teams PowerShell 概述</span><span class="sxs-lookup"><span data-stu-id="1ac30-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="1ac30-104">Microsoft Teams PowerShell 是一组 cmdlet，用于直接从 PowerShell 命令行管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="1ac30-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="1ac30-105">Teams PowerShell 以 .NET Standard 编写，适用于 Windows、PowerShell 6.x 和更高版本的所有平台上的 PowerShell 5.1，包括 Azure Cloud Shell。</span><span class="sxs-lookup"><span data-stu-id="1ac30-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="1ac30-106">在开始使用 PowerShell 之前，需要 [安装它](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac30-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="1ac30-107">PowerShell 7 和 Teams PowerShell 存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="1ac30-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="1ac30-108">我们建议使用 PowerShell 5.1，直到问题得到解决。</span><span class="sxs-lookup"><span data-stu-id="1ac30-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="1ac30-109">发布</span><span class="sxs-lookup"><span data-stu-id="1ac30-109">Releases</span></span>


<span data-ttu-id="1ac30-110">Teams PowerShell 在 [PowerShell 库中提供两](https://www.powershellgallery.com/packages/MicrosoftTeams) 种发布类型。</span><span class="sxs-lookup"><span data-stu-id="1ac30-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="1ac30-111">**常规 (GA) ：** 生产就绪的 cmdlet，每月更新一次。</span><span class="sxs-lookup"><span data-stu-id="1ac30-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="1ac30-112">**公共预览** 版：提前访问功能。</span><span class="sxs-lookup"><span data-stu-id="1ac30-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="1ac30-113">更新频率可能高于 GA。</span><span class="sxs-lookup"><span data-stu-id="1ac30-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="1ac30-114">有关两个版本中的功能添加和改进的详细信息，请阅读 [Teams PowerShell 发行说明](teams-powershell-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac30-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="1ac30-115">使用 PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="1ac30-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="1ac30-116">你将使用 Teams PowerShell 模块来完全管理 Teams：</span><span class="sxs-lookup"><span data-stu-id="1ac30-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="1ac30-117">[Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：Teams PowerShell 模块包含用于管理团队、聊天和频道的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ac30-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="1ac30-118">[Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)1.1.6 或更高版本与 Skype for Business Online 连接器集成，为 Teams PowerShell 管理提供单个模块。</span><span class="sxs-lookup"><span data-stu-id="1ac30-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="1ac30-119">[Skype for Business PowerShell 连接器：Skype](https://www.microsoft.com/download/details.aspx?id=39366)for Business PowerShell 连接器现在是 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ac30-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="1ac30-120">有关使用这些模块管理 Teams 的完整指南，请参阅"使用[Teams PowerShell 管理 Teams"。](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1ac30-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1ac30-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ac30-121">Related topics</span></span>

[<span data-ttu-id="1ac30-122">安装 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ac30-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="1ac30-123">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="1ac30-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="1ac30-124">Teams PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="1ac30-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1ac30-125">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="1ac30-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1ac30-126">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="1ac30-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="1ac30-127">使用 Microsoft Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="1ac30-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
