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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: de798e3e76b4c826cf5b235b61b3fe88e94ea1c7
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837692"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Office 365 OneDrive 和 SharePoint Online 支持多地理位置的租户中的 Teams 体验
===========================================

Microsoft 团队是群组聊天软件，即 Office 365 中团队协作的中心。 它由 Office 365 组服务和 SharePoint Online 和 OneDrive for Business （适用于其文件体验）提供支持。 在 OneDrive for Business/SharePoint Online 多地域租赁中，租户已扩展到多个地理位置（如北美、欧洲和澳大利亚），基础文件体验是多地区感知，因此团队使用文件协作的体验也很多地区感知。 这是团队在其本机文件体验中跨多个 Geos 托管的文件的关键前沿功能。

例如，在具有欧洲作为卫星地域和北美的 Contoso 租赁中，欧洲卫星用户将在左窗格中的 "文件" 选项卡下看到他或她的 OneDrive 文件，但这些文件在欧洲数据位置和美国托管es 是租户的中心位置。 此外，用户可以在 "最近查看" 视图下访问最近使用过的文件。 "最近使用的文件" 可能包括与用户共享的与其他 Geos 中的用户共享的文件，并且可能会在该租户扩展到的其他地域位置中使用。 

给定团队的组网站也是多地区识别。 也就是说，如果欧洲卫星用户正在创建团队，则会在欧洲位置创建相应的组网站，并且与该团队组相关联的文件将保留在该位置的其他位置。 任何后续体验（如上载新文件或编辑文件）将定向到该欧洲位置，从而保证数据对这些文件的派驻。 这完全由基础基金会 Office 365 组变为多地区识别。

由于多地域租赁是单个全局租户，因此在 @ 提及卫星用户将能够从世界各地看到他们的同事，无论他们在哪里。 

请注意，团队体验中的聊天和会议 IM 笔记中的对话不是多地区感知，它们仅保留在租户的中央位置。 通常，聊天对话不会应用于数据派驻服务需求。

有关 Office 365 多地区的详细信息，请参阅[Microsoft 多地区功能页面](https://aka.ms/multi-geo)。