---
title: Microsoft 365 多地域支持环境中的团队体验
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
description: 本文介绍在启用 Microsoft 365 多地域的环境中使用 Teams。
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122242"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Microsoft 365 支持多地域的租户中的团队体验

Microsoft Teams 是群组聊天软件，是 Microsoft 365 和 Office 365 中团队合作的中心。 它由 Microsoft 365 组服务以及 SharePoint Online 和 OneDrive for Business 提供，可体验文件。 在 OneDrive for Business/SharePoint Online 多地域租户中，租户扩展到北美、欧洲和澳大利亚等多个地理位置，基础文件体验是多地域感知的，因此使用文件协作的 Teams 体验也是多地域感知的。 此功能是 Teams 在本机文件体验中显示跨多个地域托管的文件的关键领先功能。 这还包括 OneNote 和 Wiki 文件。

例如，在 Contoso 租户中，欧洲作为卫星地域和北美作为中心位置，欧洲卫星用户将在左窗格中的"文件"选项卡下看到其 OneDrive 文件，尽管这些文件托管在欧洲数据位置，而美国是租户的中心位置。  此外，用户可以在"最近查看"边栏选项卡下访问 **最近使用** 的文件。 最近使用的文件可能包括其他地理位置的用户共享的文件。 

给定团队的 SharePoint 网站也是多地域感知网站。 也就是说，如果欧洲卫星用户正在创建团队，则相应的 SharePoint 网站将在欧洲位置创建。 与该团队关联的文件将保留在该位置。 任何后续体验（例如上传新文件或编辑文件）都将存储在该欧洲位置，保持这些文件的数据驻留承诺。

由于多地域租户是单一全局租户，因此在 @ 提及期间，无论同事位于何处，卫星用户都能看到世界各地的同事。

Teams 体验中的聊天、频道消息和会议 IM 笔记/聊天中的对话不是多地域感知的，并且都仅保留在租户的中心位置内。 通常，聊天对话不应用于数据驻留需求。 有关详细信息，请参阅 [Microsoft Teams 中数据的位置](location-of-data-in-teams.md)。

有关多地域功能的信息，请参阅 [Microsoft 多地域功能页](https://aka.ms/multi-geo)。
