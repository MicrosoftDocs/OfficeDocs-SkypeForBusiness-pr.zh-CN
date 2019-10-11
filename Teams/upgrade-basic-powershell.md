---
title: 基本升级 PowerShell |Microsoft 团队 |授权升级互操作策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 如果管理中心未在你的租户中亮起，则为升级到团队的 Stopgap
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397cabcbba35c153d234bc4355d12e4eb44b5c57
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435085"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="f46d6-103">将用户从 Skype for Business Online 升级到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f46d6-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="f46d6-104">本文中介绍的命令旨在用作 "[升级基本](https://aka.ms/UpgradeBasic)" 清单中的一部分。</span><span class="sxs-lookup"><span data-stu-id="f46d6-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="f46d6-105">升级的技术迁移方面必然会通知用户，Skype for Business 将升级到团队，然后将其移动到 "**仅团队**" 模式。</span><span class="sxs-lookup"><span data-stu-id="f46d6-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="f46d6-106">可通过 Skype for Business 远程 Windows PowerShell 会话或通过 Microsoft 团队管理中心完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f46d6-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="f46d6-107">我们正在积极推出[Microsoft 团队管理中心](manage-teams-skypeforbusiness-admin-center.md)的升级工具，它应该在你的租户上立即可用。</span><span class="sxs-lookup"><span data-stu-id="f46d6-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="f46d6-108">一旦可用，你就可以在[设置你的共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)中找到有关迁移用户的信息。</span><span class="sxs-lookup"><span data-stu-id="f46d6-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="f46d6-109">如果你已准备好立即升级，则可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。</span><span class="sxs-lookup"><span data-stu-id="f46d6-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="f46d6-110">升级基本步骤#</span><span class="sxs-lookup"><span data-stu-id="f46d6-110">Upgrade Basic step #</span></span> | <span data-ttu-id="f46d6-111">众</span><span class="sxs-lookup"><span data-stu-id="f46d6-111">Mode</span></span> | <span data-ttu-id="f46d6-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f46d6-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="f46d6-113">5</span><span class="sxs-lookup"><span data-stu-id="f46d6-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f46d6-114">群岛 + 通知 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="f46d6-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="f46d6-115">（如果用户当前处于 "**孤岛**" 模式下，请使用此命令（默认））</span><span class="sxs-lookup"><span data-stu-id="f46d6-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="f46d6-116">*（例如，$SipAddress = "TestUser@contoso.com"）*</span><span class="sxs-lookup"><span data-stu-id="f46d6-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="f46d6-117">5</span><span class="sxs-lookup"><span data-stu-id="f46d6-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f46d6-118">仅 skype for business + 通知 Skype for business 用户</span><span class="sxs-lookup"><span data-stu-id="f46d6-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="f46d6-119">（如果用户当前位于**Skype for** business 模式中，请使用此命令）</span><span class="sxs-lookup"><span data-stu-id="f46d6-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="f46d6-120">7</span><span class="sxs-lookup"><span data-stu-id="f46d6-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="f46d6-121">仅限团队</span><span class="sxs-lookup"><span data-stu-id="f46d6-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
