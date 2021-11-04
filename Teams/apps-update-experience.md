---
title: 应用中的应用更新Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在应用中更新Microsoft Teams。
ms.openlocfilehash: 025096ebce82fb9c5dd7fb8bb23f81094655d106
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746478"
---
# <a name="update-apps-in-microsoft-teams"></a>更新应用中Microsoft Teams

在大多数情况下，应用开发人员发布应用更新后，新版本会自动显示给用户。 但是，需要用户接受才能完成Microsoft Teams清单<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a>的一些更新：

* 已添加或删除机器人
* 现有机器人的"botId"属性已更改
* 更改了现有机器人的"isNotificationOnly"属性
* 添加了机器人的 SupportsCalling、SupportsVideo 和 SupportsFiles 功能
* 已添加消息传送扩展
* 添加了一个新连接器
* "webApplicationInfo"中的属性已更改

![新版本可用。](media/manage-your-custom-apps-update1.png)

![应用的升级选项。](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 更新过程适用于 Microsoft 应用、自定义应用和第三方应用的所有应用更新。 

## <a name="related-topics"></a>相关主题

[管理应用](manage-apps.md)
