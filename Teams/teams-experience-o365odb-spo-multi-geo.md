---
title: Microsoft 365 或 Office 365 OneDrive 和 SharePoint Online 多地理启用的租赁中的团队体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: 在本文中，你将了解如何在 Microsoft 365 或 Office 365 OneDrive 和 SharePoint Online 多地理启用的租赁中使用团队。
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
ms.openlocfilehash: 1fdfd99494b8f65c448a2b1183a183b8cf7477af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583239"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Microsoft 365 或 Office 365 OneDrive 和 SharePoint Online 多地理启用的租赁中的团队体验
===========================================

Microsoft 团队是群组聊天软件，即 Microsoft 365 和 Office 365 中团队协作的中心。 它由 Microsoft 365 组服务和 SharePoint Online 和 OneDrive for Business （适用于其文件体验）提供支持。 在 OneDrive for Business/SharePoint Online 多地域租赁中，租户已扩展到多个地理位置（如北美、欧洲和澳大利亚），基础文件体验是多地区感知，因此团队使用文件协作的体验也很多地区感知。 这是团队在其本机文件体验中跨多个 Geos 托管的文件的关键前沿功能。

例如，在具有欧洲作为卫星地域和北美的 Contoso 租赁中，欧洲卫星用户将在左窗格中的 "文件" 选项卡下看到他或她的 OneDrive 文件，尽管这些文件是在欧洲数据位置托管的，而美国是租户的中心位置。 此外，用户可以在 "最近查看" 视图下访问最近使用过的文件。 "最近使用的文件" 可能包括与用户共享的与其他 Geos 中的用户共享的文件，并且可能会在该租户扩展到的其他地域位置中使用。 

给定团队的组网站也是多地区识别。 也就是说，如果欧洲卫星用户正在创建团队，则会在欧洲位置创建相应的组网站，并且与该团队组相关联的文件将保留在该位置的其他位置。 任何后续体验（如上载新文件或编辑文件）将定向到该欧洲位置，从而保证数据对这些文件的派驻。 这一切都是由基础基金会 Microsoft 365 组变为多地区识别所实现的。

由于多地域租赁是单个全局租户，因此在 @ 提及卫星用户将能够从世界各地看到他们的同事，无论他们在哪里。 

请注意，团队体验中的聊天和会议 IM 笔记中的对话不是多地区感知，它们仅保留在租户的中央位置。 通常，聊天对话不会应用于数据派驻服务需求。

有关多地区的详细信息，请参阅[Microsoft 多地区功能页面](https://aka.ms/multi-geo)。