---
title: 从 Skype for Business Online 连接器移动到 Teams PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online 连接器移动到 Teams PowerShell 模块以管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569078"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="46669-103">从 Skype for Business Online 连接器移动到 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="46669-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="46669-104">若要从使用 Skype for Business Online 连接器转移到 Teams PowerShell 模块来管理 Teams，需要更新现有 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="46669-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="46669-105">本文介绍如何进行此操作。</span><span class="sxs-lookup"><span data-stu-id="46669-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="46669-106">安装最新的 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="46669-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="46669-107">有关步骤，请参阅["安装 Microsoft Teams Powershell"。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="46669-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="46669-108">卸载 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="46669-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="46669-109">为此，请在"控制面板"中，转到"程序和功能"，选择 **"Skype for Business Online"，** 选择"Windows PowerShell模块"，然后选择"**卸载"。**</span><span class="sxs-lookup"><span data-stu-id="46669-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="46669-110">在 PowerShell 脚本中，更改从/向引用的 ```Import-Module``` ```SkypeOnlineConnector``` 模块 ```LyncOnlineConnector``` 名称 ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="46669-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="46669-111">例如，更改为 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="46669-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="46669-112">使用 Teams PowerShell 模块 2.0 或更高版本时，请将 New-csOnlineSession 更改为 Connect-MicrosoftTeams。</span><span class="sxs-lookup"><span data-stu-id="46669-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="46669-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="46669-113">Related topics</span></span>

[<span data-ttu-id="46669-114">安装 Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="46669-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="46669-115">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="46669-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="46669-116">Teams PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="46669-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="46669-117">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="46669-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="46669-118">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="46669-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
