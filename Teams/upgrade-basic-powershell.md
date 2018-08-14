---
title: 升级基本 PowerShell 命令的 Microsoft 团队
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 如果在您的租户亮起尚未 Admin Center 升级到团队的应急
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001716"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="f40b0-103">您的用户从升级 Skype 业务 online 到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f40b0-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="f40b0-104">本文中介绍的命令旨在用作[基本升级](https://aka.ms/UpgradeBasic)的清单的一部分。</span><span class="sxs-lookup"><span data-stu-id="f40b0-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="f40b0-105">升级的技术迁移方面伴有将升级到团队，然后将它们移动到**团队仅**模式 for Business 的 Skype 通知用户。</span><span class="sxs-lookup"><span data-stu-id="f40b0-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="f40b0-106">业务远程 Windows PowerShell 会话或通过 Microsoft 团队和业务管理中心的 Skype，可以通过 Skype 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f40b0-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="f40b0-107">我们主动推出升级中[的 Microsoft 团队和业务管理中心的 Skype](manage-teams-skypeforbusiness-admin-center.md)、 工具和应立即在您的租户上可用。</span><span class="sxs-lookup"><span data-stu-id="f40b0-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="f40b0-108">只要可用它，您可以找到有关迁移用户[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)的信息。</span><span class="sxs-lookup"><span data-stu-id="f40b0-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="f40b0-109">如果您已经准备立即升级，您可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。</span><span class="sxs-lookup"><span data-stu-id="f40b0-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 
 |<span data-ttu-id="f40b0-110">升级的基本步骤 #</span><span class="sxs-lookup"><span data-stu-id="f40b0-110">Upgrade Basic step #</span></span> | <span data-ttu-id="f40b0-111">模式</span><span class="sxs-lookup"><span data-stu-id="f40b0-111">Mode</span></span> | <span data-ttu-id="f40b0-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f40b0-112">PowerShell command</span></span> |
|-------|--------|------|
| [<span data-ttu-id="f40b0-113">5</span><span class="sxs-lookup"><span data-stu-id="f40b0-113">5</span></span>](upgrade-basic.md#step-5) |<span data-ttu-id="f40b0-114">群岛 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="f40b0-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="f40b0-115">（如果用户当前正在**群岛**模式 （默认），则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="f40b0-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="f40b0-116">_(例如，$SipAddress = 'TestUser@contoso.com)_</span><span class="sxs-lookup"><span data-stu-id="f40b0-116">_(for example, $SipAddress='TestUser@contoso.com')_</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="f40b0-117">5</span><span class="sxs-lookup"><span data-stu-id="f40b0-117">5</span></span>](upgrade-basic.md#step-5)  | <span data-ttu-id="f40b0-118">Skype for Business 仅 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="f40b0-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="f40b0-119">（如果用户当前正在**for Business 仅 Skype**模式，则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="f40b0-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="f40b0-120">7</span><span class="sxs-lookup"><span data-stu-id="f40b0-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="f40b0-121">仅团队</span><span class="sxs-lookup"><span data-stu-id="f40b0-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


