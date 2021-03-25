---
title: Microsoft Teams 中的公共预览版
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft Teams 中的公共预览版。尝试新增功能并提供反馈。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: cc3dca351924daa368658a8f0c110099768e9986
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117700"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公共预览版

> [!NOTE]
> 预览版中包含的功能可能并不完整，在公开发布之前可能会发生更改。所提供的这些功能仅用于评估和探索目的。不支持Office 365 政府版社区云（GCC）。

Microsoft Teams 的公共预览版可让用户抢先体验 Teams 中的未发布功能。预览版允许探索和测试即将推出的功能。我们也欢迎大家对公共预览版中的任何功能提出反馈意见。公共预览版是为每个 Teams 用户单独启用的，因此不必担心影响整个组织。

有关 Teams 公共预览版中可用功能的列表，请访问 [Office 当前频道（预览）发行说明](/officeupdates/current-channel-preview)。

## <a name="set-the-update-policy"></a>设置更新策略

公共预览版的启用是以用户为单位，并且公共预览版启用选项的控制将在管理策略中实现。 更新策略用于管理 Teams 和 Office 预览版用户，这些用户将在 Teams 应用中看到预发布或预览功能。 你可以使用全局（默认为组织范围）策略并对其进行自定义，或者为用户创建一个或多个自定义策略。 策略需要分配到具体的用户，因为它不能覆盖全局策略。

1. 登录到管理中心。
2. 选择“**Teams**”>“**更新策略**”。

   ![选择“更新策略”选项](media/updatePolicies.png)

3. 选择“**添加**”。
4. 为更新策略命名，添加说明，然后打开“**显示预览功能**”。

你也可以用 PowerShell 的 `CsTeamsUpdateManagementPolicy`cmdlet 来设置策略。

## <a name="enable-public-preview"></a>启用公共预览版

若要在桌面或 Web 客户端上启用公共预览版，你需要执行以下任务：

1. 选择你的个人资料以显示 Teams 菜单。
2. 选择“**关于**”→“**公共预览版**”。
3. 选择“**切换到公共预览版**”。

## <a name="related-topics"></a>相关主题

[公共开发人员预览版](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)