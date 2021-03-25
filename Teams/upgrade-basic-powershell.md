---
title: 基本升级 PowerShell|Microsoft Teams|授予升级互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解在管理中心尚未在租户中亮起时用于升级到 Microsoft Teams 的 stopgap。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120534"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="052e3-103">将用户从 Skype for Business Online 升级到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="052e3-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="052e3-104">本文中所述的命令旨在用作升级基本清单 [的一](./upgrade-start-here.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="052e3-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="052e3-105">升级的技术迁移方面需要通知用户 Skype for Business 将升级到 Teams，然后将其移动到仅 **Teams** 模式。</span><span class="sxs-lookup"><span data-stu-id="052e3-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="052e3-106">这些步骤可以通过 Skype for Business 远程Windows PowerShell会话或 Microsoft Teams 管理中心完成。</span><span class="sxs-lookup"><span data-stu-id="052e3-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="052e3-107">我们正在 Microsoft [Teams](manage-teams-skypeforbusiness-admin-center.md)管理中心中积极推出升级工具，该工具应该很快就会在你的租户上推出。</span><span class="sxs-lookup"><span data-stu-id="052e3-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="052e3-108">一旦可用，就可以在设置共存和升级设置 中查找有关迁移 [用户的信息](./setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="052e3-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="052e3-109">如果现在已准备好升级，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。</span><span class="sxs-lookup"><span data-stu-id="052e3-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="052e3-110">升级基本步骤#</span><span class="sxs-lookup"><span data-stu-id="052e3-110">Upgrade Basic step #</span></span> | <span data-ttu-id="052e3-111">模式</span><span class="sxs-lookup"><span data-stu-id="052e3-111">Mode</span></span> | <span data-ttu-id="052e3-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="052e3-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="052e3-113">5</span><span class="sxs-lookup"><span data-stu-id="052e3-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="052e3-114">群岛 + 通知 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="052e3-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="052e3-115"> (如果用户当前处于"群岛"模式或默认 (，请使用) ) </span><span class="sxs-lookup"><span data-stu-id="052e3-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="052e3-116">*(例如，$SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="052e3-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="052e3-117">5</span><span class="sxs-lookup"><span data-stu-id="052e3-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="052e3-118">仅 Skype for Business + 通知 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="052e3-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="052e3-119"> (如果用户当前处于仅 **Skype for Business** 模式，请使用) </span><span class="sxs-lookup"><span data-stu-id="052e3-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="052e3-120">7</span><span class="sxs-lookup"><span data-stu-id="052e3-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="052e3-121">Teams Only</span><span class="sxs-lookup"><span data-stu-id="052e3-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |