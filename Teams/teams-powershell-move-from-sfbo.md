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
description: 了解如何从 Skype for Business Online 连接器移动到 Teams PowerShell 模块以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094123"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="ad529-103">从 Skype for Business Online 连接器移动到 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="ad529-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="ad529-104">若要从使用 Skype for Business Online 连接器转移到 Teams PowerShell 模块来管理 Teams，需要更新现有的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ad529-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="ad529-105">本文介绍如何进行此操作。</span><span class="sxs-lookup"><span data-stu-id="ad529-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="ad529-106">安装 PowerShell 模块Teams最新版本。</span><span class="sxs-lookup"><span data-stu-id="ad529-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="ad529-107">有关步骤，请参阅[安装 Microsoft Teams Powershell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="ad529-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="ad529-108">卸载 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="ad529-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="ad529-109">为此，请在"控制面板"中，转到"程序和功能"，选择"Skype for Business **Online"，Windows PowerShell** 模块"，然后选择"卸载 **"。**</span><span class="sxs-lookup"><span data-stu-id="ad529-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="ad529-110">在 PowerShell 脚本中，将 中引用的模块名称从 ```Import-Module``` 或 ```SkypeOnlineConnector``` 更改为 ```LyncOnlineConnector``` ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="ad529-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="ad529-111">例如，将 ```Import-Module -Name SkypeOnlineConnector``` 更改为 ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="ad529-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="ad529-112">使用 PowerShell Teams 2.0 或更高版本时，将 New-csOnlineSession 更改为 连接-MicrosoftTeams。</span><span class="sxs-lookup"><span data-stu-id="ad529-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="ad529-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad529-113">Related topics</span></span>

[<span data-ttu-id="ad529-114">安装 Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="ad529-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="ad529-115">使用 Teams PowerShell Teams管理资源</span><span class="sxs-lookup"><span data-stu-id="ad529-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ad529-116">TeamsPowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="ad529-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ad529-117">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="ad529-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ad529-118">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="ad529-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)