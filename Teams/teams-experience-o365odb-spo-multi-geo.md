---
title: Teams启用多Microsoft 365环境中体验
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 本文介绍在启用多Teams环境中Microsoft 365数据库。
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760535"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="3d4d5-103">Teams启用多Microsoft 365的租户中的体验</span><span class="sxs-lookup"><span data-stu-id="3d4d5-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="3d4d5-104">Microsoft Teams是群组聊天软件，它是团队合作Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="3d4d5-105">它由 Microsoft 365 组服务以及 SharePoint Online 和 OneDrive for Business 提供，适用于其文件体验。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="3d4d5-106">在 OneDrive for Business/SharePoint Online 多地理位置 租户中，租户扩展到北美、欧洲和澳大利亚等多个地理位置，基础文件体验是多地域感知的，因此 Teams 文件协作体验也是多地域感知的。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="3d4d5-107">此功能是一项关键的前导功能，Teams在其本机文件体验中跨多个地域托管的文件。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="3d4d5-108">这还包括OneNote和 Wiki 文件。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="3d4d5-109">例如，在 Contoso 租户中，欧洲作为卫星地域和北美作为中心位置，欧洲卫星用户将看到其 OneDrive 文件在左窗格中的"文件"选项卡下，尽管这些文件托管在欧洲数据位置，而美国是租户的中心位置。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="3d4d5-110">此外，用户可以在"最近查看"边栏选项卡下访问 **最近使用** 的文件。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="3d4d5-111">最近使用的文件可能包括其他地理位置的用户共享的文件。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="3d4d5-112">给定团队的SharePoint网站也是多地域感知的。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="3d4d5-113">也就是说，如果欧洲卫星用户正在创建团队，则SharePoint欧洲位置创建相应的网站。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="3d4d5-114">与该团队关联的文件将保留在该位置。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="3d4d5-115">任何后续体验（例如上传新文件或编辑文件）都将存储在该欧洲位置，同时保证这些文件的数据驻留。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="3d4d5-116">由于多地域租户是单一全局租户，因此在 @ 提及期间，卫星用户能够看到世界各地的同事，无论他们位于何处。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="3d4d5-117">Teams 体验中的聊天、频道消息和会议 IM 笔记/聊天中的对话不是多地域感知的，并且都仅保留在租户的中心位置内。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="3d4d5-118">通常，聊天对话不应用于数据驻留需求。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="3d4d5-119">有关详细信息，请参阅数据[在 Microsoft Teams 中](location-of-data-in-teams.md)的位置。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="3d4d5-120">多地域对 Teams 的支持已Microsoft 365[路线图。](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)</span><span class="sxs-lookup"><span data-stu-id="3d4d5-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="3d4d5-121">有关多地域功能的信息，请参阅 [Microsoft 多地域功能页](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="3d4d5-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
