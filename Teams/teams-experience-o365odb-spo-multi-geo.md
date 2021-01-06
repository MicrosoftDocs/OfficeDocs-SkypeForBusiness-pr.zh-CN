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
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757747"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Microsoft 365 支持多地域的租户中的团队体验

Microsoft Teams 是群组聊天软件，是 Microsoft 365 中团队合作的中心。 它由 Microsoft 365 组服务以及 SharePoint 和 OneDrive 提供，可体验文件。 在租户扩展到北美、欧洲和澳大利亚等多个地理位置的多地域组织中，基础文件体验是多地域感知的，因此，使用文件协作的 Teams 体验也是多地域感知的。 这样，Teams 可以在其本机文件体验中显示托管在多个地理位置的文件。

例如，在 Contoso 租户中，欧洲作为卫星地域和北美作为中心位置，欧洲卫星用户将在左窗格中的"文件"选项卡下看到其 OneDrive 文件，尽管文件托管在欧洲数据位置，而美国是租户的中心位置。 此外，用户可以在"最近查看"边栏选项卡下访问最近使用的文件。 最近使用的文件可能包括其他地理位置的用户共享的文件。 

给定团队的 SharePoint 网站也是多地域感知网站。 也就是说，如果欧洲卫星用户正在创建团队，则相应的 SharePoint 网站将在欧洲位置创建，与该团队关联的文件将保留在该位置。 任何后续体验（如上传新文件或编辑文件）都将存储在该欧洲位置，保持这些文件的数据驻留承诺。

请注意，Teams 体验中的聊天和会议 IM 笔记中的对话不是多地域感知的，并且都仅保留在组织的中心位置内。

有关多地域功能，请参阅 Microsoft [多地域功能](https://aka.ms/multi-geo)。
