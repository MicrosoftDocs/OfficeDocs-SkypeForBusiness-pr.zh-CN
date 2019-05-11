---
title: 基本升级 PowerShell |Microsoft 团队 |授予升级互操作性策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 如果在您的租户亮起尚未 Admin Center 升级到团队的应急
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 281938456c4fca695b2254e7cf6e50078bb32c80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920429"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="2bf78-103">您的用户从升级 Skype 业务 online 到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="2bf78-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="2bf78-104">本文中介绍的命令旨在用作[基本升级](https://aka.ms/UpgradeBasic)的清单的一部分。</span><span class="sxs-lookup"><span data-stu-id="2bf78-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="2bf78-105">升级的技术迁移方面伴有将升级到团队，然后将它们移动到**团队仅**模式 for Business 的 Skype 通知用户。</span><span class="sxs-lookup"><span data-stu-id="2bf78-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="2bf78-106">业务远程 Windows PowerShell 会话或通过 Microsoft 团队管理中心，可以通过 Skype 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="2bf78-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="2bf78-107">我们主动推出升级工具在[Microsoft 团队管理中心](manage-teams-skypeforbusiness-admin-center.md)中，并应立即在您的租户上可用。</span><span class="sxs-lookup"><span data-stu-id="2bf78-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="2bf78-108">只要可用它，您可以找到有关迁移用户[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)的信息。</span><span class="sxs-lookup"><span data-stu-id="2bf78-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="2bf78-109">如果您已经准备立即升级，您可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。</span><span class="sxs-lookup"><span data-stu-id="2bf78-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="2bf78-110">升级的基本步骤 #</span><span class="sxs-lookup"><span data-stu-id="2bf78-110">Upgrade Basic step #</span></span> | <span data-ttu-id="2bf78-111">模式</span><span class="sxs-lookup"><span data-stu-id="2bf78-111">Mode</span></span> | <span data-ttu-id="2bf78-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="2bf78-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="2bf78-113">5</span><span class="sxs-lookup"><span data-stu-id="2bf78-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="2bf78-114">群岛 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="2bf78-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="2bf78-115">（如果用户当前正在**群岛**模式 （默认），则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="2bf78-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="2bf78-116">*(例如，$SipAddress = 'TestUser@contoso.com)*</span><span class="sxs-lookup"><span data-stu-id="2bf78-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="2bf78-117">5</span><span class="sxs-lookup"><span data-stu-id="2bf78-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="2bf78-118">Skype for Business 仅 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="2bf78-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="2bf78-119">（如果用户当前正在**for Business 仅 Skype**模式，则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="2bf78-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="2bf78-120">7</span><span class="sxs-lookup"><span data-stu-id="2bf78-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="2bf78-121">仅团队</span><span class="sxs-lookup"><span data-stu-id="2bf78-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
