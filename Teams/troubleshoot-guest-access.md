---
title: 排查 Microsoft Teams 中的来宾访问问题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: 获取排查并解决 Microsoft Teams 中来宾访问问题方面的帮助。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948678"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="d3390-103">排查 Microsoft Teams 中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="d3390-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="d3390-104">若要了解我们是否知道您的问题，请查看 [您的组织中的支持团队](/MicrosoftTeams/troubleshoot/teams-welcome)。</span><span class="sxs-lookup"><span data-stu-id="d3390-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="d3390-105">若要查看与 Teams 中来宾访问相关的现有支持问题，请转到 [Teams 故障排除](/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="d3390-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="d3390-106">来宾是组织外部人员。</span><span class="sxs-lookup"><span data-stu-id="d3390-106">Guests are people outside your organization.</span></span> <span data-ttu-id="d3390-107">如果你组织内部的某人（包括员工、现场合同工或现场代理），则不能添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="d3390-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="d3390-108">这同样适用于你的关联公司。</span><span class="sxs-lookup"><span data-stu-id="d3390-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="d3390-109">有关即将发布的新推出或更新后的来宾访问功能，请访问 [Teams 路线图](https://aka.ms/teamsroadmap)。</span><span class="sxs-lookup"><span data-stu-id="d3390-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="d3390-110">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中告诉我们你想要的功能。</span><span class="sxs-lookup"><span data-stu-id="d3390-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="d3390-111">如果来宾看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="d3390-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="d3390-112">Teams 中的来宾访问功能使用 Azure Active Directory (Azure AD) 企业对企业 (B2B) 及其许可模式。</span><span class="sxs-lookup"><span data-stu-id="d3390-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="d3390-113">所有 Microsoft 365 商业标准版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="d3390-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d3390-114">无需额外的 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="d3390-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="d3390-115">必须在来宾主租户上启用 Teams，来宾才能登录，并使用 Teams 作为来宾访问租户 (资源) Teams。</span><span class="sxs-lookup"><span data-stu-id="d3390-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="d3390-116">如果看到许可错误，请务必阅读 [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) 外部标识的计费模型，以确定满足组织中来宾访问需求的许可要求。</span><span class="sxs-lookup"><span data-stu-id="d3390-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="d3390-117">来宾许可证计入邀请组织。</span><span class="sxs-lookup"><span data-stu-id="d3390-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="d3390-118">在计算所需的许可证数量时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="d3390-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="d3390-119">无论是受邀来宾来自另一个 Microsoft 365 组织，还是使用其个人电子邮件地址，许可证都计入组织。</span><span class="sxs-lookup"><span data-stu-id="d3390-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="d3390-120">支持 B2B 用户类型</span><span class="sxs-lookup"><span data-stu-id="d3390-120">Support for B2B User types</span></span>

<span data-ttu-id="d3390-121">目前，Teams 只支持 [Azure B2B 定义的](/azure/active-directory/b2b/user-properties)状态 1 和状态 2 类型来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d3390-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3390-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3390-122">Related topics</span></span>

[<span data-ttu-id="d3390-123">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="d3390-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="d3390-124">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d3390-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)