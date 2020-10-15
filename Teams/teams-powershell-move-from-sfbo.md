---
title: 从 Skype for Business Online 连接器迁移到团队 PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online 连接器迁移到团队 PowerShell 模块以管理团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469661"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="94d6e-103">从 Skype for Business Online 连接器迁移到团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="94d6e-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="94d6e-104">若要从使用 Skype for Business Online 连接器转到团队 PowerShell 模块以管理团队，您需要更新现有 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="94d6e-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="94d6e-105">本文介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="94d6e-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="94d6e-106">安装最新的团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="94d6e-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="94d6e-107">有关步骤，请参阅 [安装 Microsoft 团队 Powershell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="94d6e-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="94d6e-108">卸载 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="94d6e-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="94d6e-109">若要执行此操作，请在 "控制面板" 中，转到 " **程序和功能**"，选择 " **Skype for Business Online，Windows PowerShell 模块**"，然后选择 " **卸载**"。</span><span class="sxs-lookup"><span data-stu-id="94d6e-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="94d6e-110">在 PowerShell 脚本中，更改 "从" 或 "到" 中引用的模块名称 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="94d6e-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="94d6e-111">例如，"更改 ```Import-Module -Name SkypeOnlineConnector``` 为" ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="94d6e-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="94d6e-112">管理员应继续使用 [新的 CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) ，并在使用 Skype For business Online cmdlet 之前导入该会话。</span><span class="sxs-lookup"><span data-stu-id="94d6e-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="94d6e-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="94d6e-113">Related topics</span></span>

[<span data-ttu-id="94d6e-114">安装 Microsoft 团队 Powershell</span><span class="sxs-lookup"><span data-stu-id="94d6e-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="94d6e-115">通过团队 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="94d6e-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="94d6e-116">团队 PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="94d6e-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="94d6e-117">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="94d6e-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="94d6e-118">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="94d6e-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
