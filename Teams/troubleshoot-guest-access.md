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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837632"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="55d68-103">解决 Microsoft 团队中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="55d68-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="55d68-104">您可能需要等待24小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="55d68-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="55d68-105">若要使用团队中的来宾访问权限检查当前支持问题，请转到[团队疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="55d68-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="55d68-106">若要查看我们是否知道你的问题，请查看[Microsoft 团队的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="55d68-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="55d68-107">来宾是您的组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="55d68-107">Guests are users outside your organization.</span></span> <span data-ttu-id="55d68-108">如果某人在你的组织内（包括你的员工、现场承包商或现场工程师），则不能将其添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="55d68-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="55d68-109">这同样适用于您的会员。</span><span class="sxs-lookup"><span data-stu-id="55d68-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="55d68-110">了解[团队路线图](https://aka.ms/teamsroadmap)中即将推出的新的或更新的来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="55d68-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="55d68-111">请告诉我们你希望的[团队 UserVoice](https://aka.ms/TeamsUserVoice)内容。</span><span class="sxs-lookup"><span data-stu-id="55d68-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="55d68-112">如果您的客人看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="55d68-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="55d68-113">团队中的来宾访问使用 Azure Active Directory （Azure AD）企业到企业（B2B）和其许可模型。</span><span class="sxs-lookup"><span data-stu-id="55d68-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="55d68-114">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="55d68-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="55d68-115">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="55d68-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="55d68-116">如果您看到 "授权错误"，请确保阅读[Azure Active DIRECTORY B2B 授权指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)以确定授权要求以满足您的组织中的来宾访问要求。</span><span class="sxs-lookup"><span data-stu-id="55d68-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="55d68-117">来宾许可证按邀请的组织计入。</span><span class="sxs-lookup"><span data-stu-id="55d68-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="55d68-118">当你计算所需的许可证数量时，请考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="55d68-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="55d68-119">根据您的组织统计许可证，无论受邀的来宾来自其他 Office 365 租户还是使用其个人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="55d68-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="55d68-120">对 B2B 用户类型的支持</span><span class="sxs-lookup"><span data-stu-id="55d68-120">Support for B2B User types</span></span>
<span data-ttu-id="55d68-121">当前团队仅支持[由 AZURE B2B 定义](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)的状态1和状态2类型的来宾用户。</span><span class="sxs-lookup"><span data-stu-id="55d68-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="55d68-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="55d68-122">Related topics</span></span>

[<span data-ttu-id="55d68-123">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="55d68-123">Guest access in Teams</span></span>](guest-access.md)


