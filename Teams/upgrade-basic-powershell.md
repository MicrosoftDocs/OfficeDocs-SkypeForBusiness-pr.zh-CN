---
title: 基本升级 PowerShell |Microsoft 团队 |授予升级互操作性策略
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 如果在您的租户亮起尚未 Admin Center 升级到团队的应急
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f0d76ffb4f2564a09ea3a4418f9baf7e53e8446
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754380"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="f1b24-103">您的用户从升级 Skype 业务 online 到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f1b24-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="f1b24-104">本文中介绍的命令旨在用作[基本升级](https://aka.ms/UpgradeBasic)的清单的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1b24-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="f1b24-105">升级的技术迁移方面伴有将升级到团队，然后将它们移动到**团队仅**模式 for Business 的 Skype 通知用户。</span><span class="sxs-lookup"><span data-stu-id="f1b24-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="f1b24-106">业务远程 Windows PowerShell 会话或通过 Microsoft 团队管理中心，可以通过 Skype 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f1b24-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="f1b24-107">我们主动推出升级工具在[Microsoft 团队管理中心](manage-teams-skypeforbusiness-admin-center.md)中，并应立即在您的租户上可用。</span><span class="sxs-lookup"><span data-stu-id="f1b24-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="f1b24-108">只要可用它，您可以找到有关迁移用户[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)的信息。</span><span class="sxs-lookup"><span data-stu-id="f1b24-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="f1b24-109">如果您已经准备立即升级，您可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。</span><span class="sxs-lookup"><span data-stu-id="f1b24-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="f1b24-110">升级的基本步骤 #</span><span class="sxs-lookup"><span data-stu-id="f1b24-110">Upgrade Basic step #</span></span> | <span data-ttu-id="f1b24-111">模式</span><span class="sxs-lookup"><span data-stu-id="f1b24-111">Mode</span></span> | <span data-ttu-id="f1b24-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f1b24-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="f1b24-113">5</span><span class="sxs-lookup"><span data-stu-id="f1b24-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f1b24-114">群岛 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="f1b24-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="f1b24-115">（如果用户当前正在**群岛**模式 （默认），则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="f1b24-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="f1b24-116">*(例如，$SipAddress = 'TestUser@contoso.com)*</span><span class="sxs-lookup"><span data-stu-id="f1b24-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="f1b24-117">5</span><span class="sxs-lookup"><span data-stu-id="f1b24-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f1b24-118">Skype for Business 仅 + 业务用户通知 Skype</span><span class="sxs-lookup"><span data-stu-id="f1b24-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="f1b24-119">（如果用户当前正在**for Business 仅 Skype**模式，则使用此命令）</span><span class="sxs-lookup"><span data-stu-id="f1b24-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="f1b24-120">7</span><span class="sxs-lookup"><span data-stu-id="f1b24-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="f1b24-121">仅团队</span><span class="sxs-lookup"><span data-stu-id="f1b24-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |