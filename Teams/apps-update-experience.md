---
title: 应用中的应用更新Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 了解如何在应用中更新Microsoft Teams。
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337820"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="d26bf-103">更新应用中Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d26bf-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="d26bf-104">在大多数情况下，应用开发人员发布应用更新后，新版本会自动显示给用户。</span><span class="sxs-lookup"><span data-stu-id="d26bf-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="d26bf-105">但是，需要用户接受才能完成Microsoft Teams清单<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a>的一些更新：</span><span class="sxs-lookup"><span data-stu-id="d26bf-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="d26bf-106">已添加或删除机器人</span><span class="sxs-lookup"><span data-stu-id="d26bf-106">A bot was added or removed</span></span>
* <span data-ttu-id="d26bf-107">现有机器人的"botId"属性已更改</span><span class="sxs-lookup"><span data-stu-id="d26bf-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="d26bf-108">更改了现有机器人的"isNotificationOnly"属性</span><span class="sxs-lookup"><span data-stu-id="d26bf-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="d26bf-109">机器人的"supportsFiles"属性已更改</span><span class="sxs-lookup"><span data-stu-id="d26bf-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="d26bf-110">已添加或删除消息扩展</span><span class="sxs-lookup"><span data-stu-id="d26bf-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="d26bf-111">添加了一个新连接器</span><span class="sxs-lookup"><span data-stu-id="d26bf-111">A new connector was added</span></span>
* <span data-ttu-id="d26bf-112">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="d26bf-112">A new static tab was added</span></span>
* <span data-ttu-id="d26bf-113">添加了一个新的可配置选项卡</span><span class="sxs-lookup"><span data-stu-id="d26bf-113">A new configurable tab was added</span></span>
* <span data-ttu-id="d26bf-114">"webApplicationInfo"中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="d26bf-114">Properties inside "webApplicationInfo" changed</span></span>

![可用的新版本](media/manage-your-custom-apps-update1.png)

![应用的升级选项](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="d26bf-117">更新过程适用于 Microsoft 应用、自定义应用和第三方应用的所有应用更新。</span><span class="sxs-lookup"><span data-stu-id="d26bf-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d26bf-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="d26bf-118">Related topics</span></span>

[<span data-ttu-id="d26bf-119">管理应用</span><span class="sxs-lookup"><span data-stu-id="d26bf-119">Manage apps</span></span>](manage-apps.md)