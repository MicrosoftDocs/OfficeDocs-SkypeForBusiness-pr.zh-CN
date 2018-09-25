---
title: Office 365 OneDrive 和 SharePoint Online 启用多的地理位置的租户的团队体验
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: 了解如何使用 Office 365 OneDrive 和 SharePoint Online 启用多的地理位置的租赁中的团队。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a780e0f44e7159d9bb2993ec62d4fd679b5e893
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017742"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="d3f38-103">Office 365 OneDrive 和 SharePoint Online 启用多的地理位置的租户的团队体验</span><span class="sxs-lookup"><span data-stu-id="d3f38-103">Teams experience in an Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="d3f38-104">Microsoft 团队是群聊软件，Office 365 中的团队协作的中心。</span><span class="sxs-lookup"><span data-stu-id="d3f38-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="d3f38-105">启动 Office 365 组服务以及 SharePoint Online 和 OneDrive for Business 为其文件体验。</span><span class="sxs-lookup"><span data-stu-id="d3f38-105">It is powered by the Office 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="d3f38-106">Onedrive for Business/SharePoint Online 多地理租户，在其中租户扩展到多个地理位置，如北美和欧洲、 澳大利亚，基础文件体验是请注意，多地理，因此团队体验与文件协作也是了解多地理。</span><span class="sxs-lookup"><span data-stu-id="d3f38-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="d3f38-107">这是团队曲面文件跨多个 Geo 其本机文件体验中承载的关键领先的功能。</span><span class="sxs-lookup"><span data-stu-id="d3f38-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="d3f38-108">例如，在与欧洲作为附属地理位置和北美作为中心按地理 Contoso 租户，欧洲附属用户将看到他/她 OneDrive 文件左窗格中，在文件选项卡虽然这些文件位于欧洲数据位置和美国 Stat 中es 是租户的中央位置。</span><span class="sxs-lookup"><span data-stu-id="d3f38-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="d3f38-109">此外，用户可以访问最近的视图刀片下最近使用过的文件。</span><span class="sxs-lookup"><span data-stu-id="d3f38-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="d3f38-110">最新文件可能包括其他 Geo 中与用户用户共享的文件和可能在租户扩展到其他地理位置管理。</span><span class="sxs-lookup"><span data-stu-id="d3f38-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="d3f38-111">给定的团队组网站也是了解多地理。</span><span class="sxs-lookup"><span data-stu-id="d3f38-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="d3f38-112">也就是说，如果欧洲附属用户创建一个团队，将在欧洲位置创建相应的组网站和与关联的文件，将在该位置中的其余部分保持团队组。</span><span class="sxs-lookup"><span data-stu-id="d3f38-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="d3f38-113">任何后续的体验，如上载新的文件或编辑该文件，将对该欧洲位置，保留的这些文件的数据住所承诺设定。</span><span class="sxs-lookup"><span data-stu-id="d3f38-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="d3f38-114">这是所有成为可能基础 foundation 变得多地理了解 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="d3f38-114">This is all made possible by the underlying foundation Office 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="d3f38-115">由于多地理租赁单个全局租户，期间 @ 提及附属用户将能够看到其同事从在世界各地，无论它们所在的位置。</span><span class="sxs-lookup"><span data-stu-id="d3f38-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="d3f38-116">注意聊天和会议中的团队体验的 IM 注意事项中的对话不多地理请注意，并且所有保留仅在租户的中央位置。</span><span class="sxs-lookup"><span data-stu-id="d3f38-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="d3f38-117">通常，聊天不应用于数据住所需求。</span><span class="sxs-lookup"><span data-stu-id="d3f38-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="d3f38-118">有关 Office 365 多-地理位置的详细信息，请参阅[Microsoft 多地理位置功能页](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="d3f38-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>