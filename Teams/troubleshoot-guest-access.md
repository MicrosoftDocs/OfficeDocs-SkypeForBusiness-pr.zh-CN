---
title: 解决 Microsoft 团队中的来宾访问问题
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
description: 获取有关解决和解决 Microsoft 团队中的来宾访问问题的帮助。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 2931a3f5440492aa1ab99a53cd196ab2973eb122
ms.sourcegitcommit: b1bf37a96a8faa169d8a32b7478f1e2d1022ebbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311257"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="d5675-103">解决 Microsoft 团队中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="d5675-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="d5675-104">[!注释] 你可能必须等待长达 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="d5675-104">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="d5675-105">若要使用团队中的来宾访问权限检查当前支持问题，请转到[团队疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="d5675-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="d5675-106">若要查看我们是否知道你的问题，请查看[Microsoft 团队的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d5675-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="d5675-107">来宾是您的组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="d5675-107">Guests are users outside your organization.</span></span> <span data-ttu-id="d5675-108">如果某人在你的组织内（包括你的员工、现场承包商或现场工程师），则不能将其添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="d5675-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="d5675-109">这同样适用于您的会员。</span><span class="sxs-lookup"><span data-stu-id="d5675-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="d5675-110">了解[团队路线图](https://aka.ms/teamsroadmap)中即将推出的新的或更新的来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="d5675-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="d5675-111">请告诉我们你希望的[团队 UserVoice](https://aka.ms/TeamsUserVoice)内容。</span><span class="sxs-lookup"><span data-stu-id="d5675-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="d5675-112">如果您的客人看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="d5675-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="d5675-113">团队中的来宾访问使用 Azure Active Directory （Azure AD）企业到企业（B2B）和其许可模型。</span><span class="sxs-lookup"><span data-stu-id="d5675-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="d5675-114">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="d5675-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d5675-115">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="d5675-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="d5675-116">如果您看到 "授权错误"，请确保阅读[Azure Active DIRECTORY B2B 授权指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)以确定授权要求以满足您的组织中的来宾访问要求。</span><span class="sxs-lookup"><span data-stu-id="d5675-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="d5675-117">来宾许可证按邀请的组织计入。</span><span class="sxs-lookup"><span data-stu-id="d5675-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="d5675-118">当你计算所需的许可证数量时，请考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="d5675-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="d5675-119">根据您的组织统计许可证，无论受邀的来宾来自其他 Office 365 租户还是使用其个人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d5675-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="d5675-120">对 B2B 用户类型的支持</span><span class="sxs-lookup"><span data-stu-id="d5675-120">Support for B2B User types</span></span>
<span data-ttu-id="d5675-121">当前团队仅支持[由 AZURE B2B 定义](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)的状态1和状态2类型的来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d5675-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5675-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5675-122">Related topics</span></span>

[<span data-ttu-id="d5675-123">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="d5675-123">Guest access in Teams</span></span>](guest-access.md)


