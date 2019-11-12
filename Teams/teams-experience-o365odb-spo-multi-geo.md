---
title: Office 365 OneDrive 和 SharePoint Online 支持多地理位置的租户中的 Teams 体验
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: 了解如何在 Office 365 OneDrive 和 SharePoint Online 多地理启用的租赁中使用团队。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe181e7ef55b386d4a6eb40bb7e383ca89a956d9
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231243"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="01bd7-103">Office 365 OneDrive 和 SharePoint Online 支持多地理位置的租户中的 Teams 体验</span><span class="sxs-lookup"><span data-stu-id="01bd7-103">Teams experience in an Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="01bd7-104">Microsoft 团队是群组聊天软件，即 Office 365 中团队协作的中心。</span><span class="sxs-lookup"><span data-stu-id="01bd7-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="01bd7-105">它由 Office 365 组服务和 SharePoint Online 和 OneDrive for Business （适用于其文件体验）提供支持。</span><span class="sxs-lookup"><span data-stu-id="01bd7-105">It is powered by the Office 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="01bd7-106">在 OneDrive for Business/SharePoint Online 多地域租赁中，租户已扩展到多个地理位置（如北美、欧洲和澳大利亚），基础文件体验是多地区感知，因此团队使用文件协作的体验也很多地区感知。</span><span class="sxs-lookup"><span data-stu-id="01bd7-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="01bd7-107">这是团队在其本机文件体验中跨多个 Geos 托管的文件的关键前沿功能。</span><span class="sxs-lookup"><span data-stu-id="01bd7-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="01bd7-108">例如，在具有欧洲作为卫星地域和北美的 Contoso 租赁中，欧洲卫星用户将在左窗格中的 "文件" 选项卡下看到他或她的 OneDrive 文件，但这些文件在欧洲数据位置和美国托管es 是租户的中心位置。</span><span class="sxs-lookup"><span data-stu-id="01bd7-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="01bd7-109">此外，用户可以在 "最近查看" 视图下访问最近使用过的文件。</span><span class="sxs-lookup"><span data-stu-id="01bd7-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="01bd7-110">"最近使用的文件" 可能包括与用户共享的与其他 Geos 中的用户共享的文件，并且可能会在该租户扩展到的其他地域位置中使用。</span><span class="sxs-lookup"><span data-stu-id="01bd7-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="01bd7-111">给定团队的组网站也是多地区识别。</span><span class="sxs-lookup"><span data-stu-id="01bd7-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="01bd7-112">也就是说，如果欧洲卫星用户正在创建团队，则会在欧洲位置创建相应的组网站，并且与该团队组相关联的文件将保留在该位置的其他位置。</span><span class="sxs-lookup"><span data-stu-id="01bd7-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="01bd7-113">任何后续体验（如上载新文件或编辑文件）将定向到该欧洲位置，从而保证数据对这些文件的派驻。</span><span class="sxs-lookup"><span data-stu-id="01bd7-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="01bd7-114">这完全由基础基金会 Office 365 组变为多地区识别。</span><span class="sxs-lookup"><span data-stu-id="01bd7-114">This is all made possible by the underlying foundation Office 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="01bd7-115">由于多地域租赁是单个全局租户，因此在 @ 提及卫星用户将能够从世界各地看到他们的同事，无论他们在哪里。</span><span class="sxs-lookup"><span data-stu-id="01bd7-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="01bd7-116">请注意，团队体验中的聊天和会议 IM 笔记中的对话不是多地区感知，它们仅保留在租户的中央位置。</span><span class="sxs-lookup"><span data-stu-id="01bd7-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="01bd7-117">通常，聊天对话不会应用于数据派驻服务需求。</span><span class="sxs-lookup"><span data-stu-id="01bd7-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="01bd7-118">有关 Office 365 多地区的详细信息，请参阅[Microsoft 多地区功能页面](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="01bd7-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>