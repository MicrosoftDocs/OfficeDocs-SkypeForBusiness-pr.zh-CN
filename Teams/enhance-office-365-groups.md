---
title: "使用 Microsoft Teams 增强现有 Office 365 组"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何使用 Microsoft Teams 将通讯组列表邀请到团队来增强 Office 365 组，以及如何添加启用邮件的安全组等。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 428915dc70a8044fd6a7b4202e5bdefed036daa9
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="enhance-existing-office-365-groups-with-microsoft-teams"></a><span data-ttu-id="a9726-103">使用 Microsoft Teams 增强现有 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="a9726-103">Enhance Existing Office 365 groups with Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="a9726-104">Microsoft Teams 用户可以使用 Microsoft Teams 功能来增强现有 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="a9726-104">Microsoft Teams users can enhance an existing Office 365 Group with Microsoft Teams functionality.</span></span> <span data-ttu-id="a9726-105">考虑增强公用 Office 365 组时，如果成员数等于或少于 2500，则用户可以增强该组。</span><span class="sxs-lookup"><span data-stu-id="a9726-105">When looking at enhancing a public Office 365 Group, users can do that if the number of members is equal to or less than 2500.</span></span>

<span data-ttu-id="a9726-106">为此，用户应该从 Microsoft Teams 客户端完成创建新团队的流程。</span><span class="sxs-lookup"><span data-stu-id="a9726-106">To do this, users should go through the flow of creating a new team from the Microsoft Teams client.</span></span> <span data-ttu-id="a9726-107">选择屏幕底部的**“是，添加 Microsoft Teams 功能”**，然后选择要使用 Microsoft Teams 增强的现有组。</span><span class="sxs-lookup"><span data-stu-id="a9726-107">Select **“Yes, add Microsoft Teams functionality”** at the bottom of the screen and then choose the existing group that they want to enhance with Microsoft Teams.</span></span> <span data-ttu-id="a9726-108">现有组成员将自动作为成员添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="a9726-108">Existing group members will be added as members to the team automatically.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="a9726-109">仅 Office 365 组所有者有权使用 Microsoft Teams 增强现有组。</span><span class="sxs-lookup"><span data-stu-id="a9726-109">Only the Office 365 Group owners have permission to enhance an existing group with Microsoft Teams.</span></span> 

<span data-ttu-id="a9726-110">用户也可以将通讯组列表邀请到团队，该通讯组列表的成员将添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="a9726-110">Users can also invite a distribution list to a team, and the members of that distribution list will be added to the team.</span></span> <span data-ttu-id="a9726-111">这是一次性同步操作，以后通讯组列表中组成员身份的变化不会复制到 Teams。</span><span class="sxs-lookup"><span data-stu-id="a9726-111">This is a one-time sync, and later changes in group membership in the distribution list will not be replicated to Teams.</span></span> 

![一个序列中的这些屏幕截图显示了邀请一个通讯组列表及其成员加入团队。](media/Enhance_Existing_Office_365_groups_with_Microsoft_Teams_image2.png)

<span data-ttu-id="a9726-113">你还可以将启用邮件的安全组添加为某个团队的成员。</span><span class="sxs-lookup"><span data-stu-id="a9726-113">You can also add mail-enabled security groups as members of a team.</span></span> <span data-ttu-id="a9726-114">但是，如果你以后向该安全组添加了更多成员，这些成员不会自动添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="a9726-114">But, if you later add more members to the security group, those members are not automatically added to the team.</span></span> <span data-ttu-id="a9726-115">你必须单独将新成员添加到该团队，或将该安全组重新添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="a9726-115">You must add the new members separately or re-add the security group to the team.</span></span> <span data-ttu-id="a9726-116">（如果你重新添加安全组，删除重复操作可确保成员只添加一次。）</span><span class="sxs-lookup"><span data-stu-id="a9726-116">(If you re-add the security group, deduplication makes sure members are added only once.)</span></span>

<span data-ttu-id="a9726-117">Office 365 组有两种类型的隐私设置：**公用和专用**。</span><span class="sxs-lookup"><span data-stu-id="a9726-117">There are two types of privacy settings with Office 365 groups, **public and private**.</span></span> <span data-ttu-id="a9726-118">虽然可以为 Microsoft Teams 启用这两种组类型，但在进行自助服务时，存在一个细微的差别。</span><span class="sxs-lookup"><span data-stu-id="a9726-118">Whereas both group types can be enabled for Microsoft Teams, there is a slight difference when it comes to self-service.</span></span>

-   <span data-ttu-id="a9726-119">用户可以搜索公用组，并且无需团队所有者的批准即可自己加入公用组。</span><span class="sxs-lookup"><span data-stu-id="a9726-119">Users can search for public groups and can join by themselves without a need for team owner’s approval.</span></span>

-   <span data-ttu-id="a9726-120">专用组不可搜索，除非团队所有者将用户添加为成员，否则用户无法加入专用组。</span><span class="sxs-lookup"><span data-stu-id="a9726-120">Private groups are not searchable, and users cannot join unless a team owner add them as a member.</span></span>

<span data-ttu-id="a9726-121">在 Microsoft Teams 中创建新团队时，现有专用 Office 365 组的所有者可以选择使用 Office 365 组中的成员身份来创建团队。</span><span class="sxs-lookup"><span data-stu-id="a9726-121">When creating a new team in Microsoft Teams, an owner of an existing private Office 365 group has an option to use the membership in the Office 365 group to create the team.</span></span> <span data-ttu-id="a9726-122">用户可以通过为 SharePoint 添加一个选项卡并合并 OneNote 文件来添加其现有 SharePoint 和 OneNote 文件。</span><span class="sxs-lookup"><span data-stu-id="a9726-122">Users can add their existing SharePoint and OneNote files by adding a tab for SharePoint and merging OneNote files.</span></span>
