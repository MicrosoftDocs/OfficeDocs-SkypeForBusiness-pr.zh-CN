---
title: 排查 Microsoft Teams 中的来宾访问问题
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837632"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="722e2-103">排查 Microsoft Teams 中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="722e2-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="722e2-104">最长可能需要等待 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="722e2-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="722e2-105">若要查看与 Teams 中来宾访问相关的现有支持问题，请转到 [Teams 故障排除](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="722e2-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="722e2-106">若要确定你的问题是否已顺利反馈，请查看 [Microsoft Teams 已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="722e2-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="722e2-107">来宾是你组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="722e2-107">Guests are users outside your organization.</span></span> <span data-ttu-id="722e2-108">如果你组织内部的某人（包括员工、现场合同工或现场代理），则不能添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="722e2-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="722e2-109">这同样适用于你的关联公司。</span><span class="sxs-lookup"><span data-stu-id="722e2-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="722e2-110">有关即将发布的新推出或更新后的来宾访问功能，请访问 [Teams 路线图](https://aka.ms/teamsroadmap)。</span><span class="sxs-lookup"><span data-stu-id="722e2-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="722e2-111">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中告诉我们你想要的功能。</span><span class="sxs-lookup"><span data-stu-id="722e2-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="722e2-112">如果来宾看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="722e2-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="722e2-113">Teams 中的来宾访问功能使用 Azure Active Directory (Azure AD) 企业对企业 (B2B) 及其许可模式。</span><span class="sxs-lookup"><span data-stu-id="722e2-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="722e2-114">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="722e2-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="722e2-115">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="722e2-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="722e2-116">如果看到许可错误，请务必阅读 [Azure Active Directory B2B 许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以确定许可要求，从而满足你组织中的来宾访问需求。</span><span class="sxs-lookup"><span data-stu-id="722e2-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="722e2-117">来宾许可证计入邀请组织。</span><span class="sxs-lookup"><span data-stu-id="722e2-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="722e2-118">在计算所需的许可证数量时，请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="722e2-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="722e2-119">无论受邀的来宾是来自另一个 Office 365 租户，还是使用自己的个人电子邮件地址，许可证都会计入你的组织。</span><span class="sxs-lookup"><span data-stu-id="722e2-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="722e2-120">支持 B2B 用户类型</span><span class="sxs-lookup"><span data-stu-id="722e2-120">Support for B2B User types</span></span>
<span data-ttu-id="722e2-121">目前，Teams 只支持 [Azure B2B 定义的](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)状态 1 和状态 2 类型来宾用户。</span><span class="sxs-lookup"><span data-stu-id="722e2-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="722e2-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="722e2-122">Related topics</span></span>

[<span data-ttu-id="722e2-123">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="722e2-123">Guest access in Teams</span></span>](guest-access.md)


