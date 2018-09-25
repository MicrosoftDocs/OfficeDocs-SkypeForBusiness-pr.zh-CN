---
title: 有关 Microsoft 团队中的保留策略的已知的问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 当前的 Microsoft 团队保留策略的已知问题的列表。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6d71a1b2422dfadfbc7ae0fb87e607fd288152
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004583"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="47c70-103">有关 Microsoft 团队中的保留策略的已知的问题</span><span class="sxs-lookup"><span data-stu-id="47c70-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="47c70-104">以下已知问题被的团队中的保留策略的跟踪，调查。</span><span class="sxs-lookup"><span data-stu-id="47c70-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="47c70-105">下选择工作组添加工作组通道消息位置行中，您可能会看到的 Office 365 组不还团队。</span><span class="sxs-lookup"><span data-stu-id="47c70-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="47c70-106">这将在将来解决。</span><span class="sxs-lookup"><span data-stu-id="47c70-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="47c70-107">下团队聊天位置行中选择用户，您可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="47c70-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="47c70-108">保留策略不打算为来宾，设置，而且我们正在这些从列表中删除。</span><span class="sxs-lookup"><span data-stu-id="47c70-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="47c70-109">Exchange 生命周期助理 (ELC)，每日，运行，但它具有 7 天的 SLA。</span><span class="sxs-lookup"><span data-stu-id="47c70-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="47c70-110">因此，很可能，如果您有删除早于 60 天的项目工作组保留策略，这些项目无法达 67 天保留。</span><span class="sxs-lookup"><span data-stu-id="47c70-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="47c70-111">这不是新情况-遵循 Exchange 模型。</span><span class="sxs-lookup"><span data-stu-id="47c70-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="47c70-112">当然，在大多数情况下，没有延迟。</span><span class="sxs-lookup"><span data-stu-id="47c70-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="47c70-114">决策点</span><span class="sxs-lookup"><span data-stu-id="47c70-114">Decision point</span></span>         |<span data-ttu-id="47c70-115">贵组织需要哪些安全性和合规性功能？</span><span class="sxs-lookup"><span data-stu-id="47c70-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="47c70-116">贵组织是否有所需的许可证来满足安全性和合规性业务需求？</span><span class="sxs-lookup"><span data-stu-id="47c70-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="47c70-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="47c70-118">Next steps</span></span>         |<span data-ttu-id="47c70-119">文档所需的安全性和遵从性功能。</span><span class="sxs-lookup"><span data-stu-id="47c70-119">Document your required security and compliance features.</span></span>         |
