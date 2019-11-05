---
title: Microsoft Teams 中保留策略的已知问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Microsoft 团队保留策略的已知问题的当前列表。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968333"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="e5f52-103">Microsoft Teams 中保留策略的已知问题</span><span class="sxs-lookup"><span data-stu-id="e5f52-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e5f52-104">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="e5f52-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="e5f52-105">支持在专用频道中共享的文件的保留。</span><span class="sxs-lookup"><span data-stu-id="e5f52-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="e5f52-106">以下是正在跟踪和调查的团队中的保留策略的已知问题。</span><span class="sxs-lookup"><span data-stu-id="e5f52-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="e5f52-107">在 "团队频道消息位置" 行中的 "选择团队" 下，你可能会看到不是团队的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="e5f52-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="e5f52-108">未来将对此进行寻址。</span><span class="sxs-lookup"><span data-stu-id="e5f52-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="e5f52-109">在 "在团队聊天位置中选择用户" 行中，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="e5f52-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="e5f52-110">保留策略不适于为来宾设置，我们正在努力从列表中删除这些保留策略。</span><span class="sxs-lookup"><span data-stu-id="e5f52-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="e5f52-111">Exchange 生命周期助理（ELC）每天运行，但其 SLA 为7天。</span><span class="sxs-lookup"><span data-stu-id="e5f52-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="e5f52-112">因此，如果你有一个团队保留策略来删除超过60天的项目，这些项目最多可持续67天。</span><span class="sxs-lookup"><span data-stu-id="e5f52-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="e5f52-113">这不是一种新情况-它遵循 Exchange 模型。</span><span class="sxs-lookup"><span data-stu-id="e5f52-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="e5f52-114">当然，在大多数情况下，不会有延迟。</span><span class="sxs-lookup"><span data-stu-id="e5f52-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![代表决策点的图标](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="e5f52-116">决策点</span><span class="sxs-lookup"><span data-stu-id="e5f52-116">Decision point</span></span>         |<span data-ttu-id="e5f52-117">贵组织需要哪些安全性和合规性功能？</span><span class="sxs-lookup"><span data-stu-id="e5f52-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="e5f52-118">贵组织是否有所需的许可证来满足安全性和合规性业务需求？</span><span class="sxs-lookup"><span data-stu-id="e5f52-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![表示后续步骤的图标](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="e5f52-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5f52-120">Next steps</span></span>         |<span data-ttu-id="e5f52-121">记录所需的安全和合规性功能。</span><span class="sxs-lookup"><span data-stu-id="e5f52-121">Document your required security and compliance features.</span></span>         |
