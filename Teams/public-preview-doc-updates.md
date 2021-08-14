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
ms.openlocfilehash: c9e6ba763edd0791310d30f8dc1e71cccc8a4cf8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235197"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公共预览版

> [!NOTE] 
> 预览版中包含的功能可能不完整，且可能会在公共版本中可用之前进行更改。这些功能仅用于评估和浏览目的。Office 365 政府社区云(GCC) 不支持预览版功能。

Microsoft Teams 公共预览版提供对 Teams 中未发布的功能的早期访问权限。预览版允许浏览并测试即将推出的功能。此外，我们还欢迎针对公共预览版中的任何功能提供反馈。我们已为每个团队用户启用公共预览版，因此无需担心会影响整个组织。

有关 Teams 公共预览版中可用内容的列表，请访问 [Microsoft Teams 公共预览版技术说明](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)、 [Teams 管理功能的发布说明](/OfficeUpdates/teams-admin)，以及 [Teams 中的新增内容](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。

## <a name="set-the-update-policy"></a>设置更新策略

我们已为每个用户启用公共预览版，并在管理策略中控制启用公共预览版的选项。更新策略用于管理 Teams 和 Office 预览版用户，这些用户将在 Teams 应用中查看预发布或预览版功能。可以使用全局(默认为组织范围内)策略并对其进行自定义，或为用户创建一个或多个自定义策略。由于策略不会覆盖全局策略，因此需将其分配给特定用户。

1. 登录到管理中心。

2. 选择 **Teams** > **更新策略**，然后选择 **更新策略** 选项。

1. 选择 **添加** 以新建策略，或选择现有策略以打开 **更新策略**。

2. 命名更新策略，添加说明，然后选择 **显示预览版功能** 的设置。

   -   **关注 Office 预览版** (默认): 此新的默认选项将为在 Office 当前频道(预览)中注册的用户自动启用 Teams 公共预览版功能。 最终用户无需执行更多操作。
   -   **已启用**: 无论用户是否在 Office 当前频道(预览)中注册，此选项都将启用 Teams 公共预览版。 此外，最终用户还必须在其 Teams 应用中选择加入 Teams 公共预览版。

   > [!NOTE]  
   > 对于 Teams 公共预览版中不在 **当前频道(预览)** 中的现有用户，IT 管理员需要从默认的 **关注 Office 预览版** 切换为 **已启用**。
 
   - **未启用**: 最终用户将无法使用 Teams 公共预览版功能。

    ![显示预览版设置对话](media/public-preview-policy.png)  

还可以同时使用 PowerShell `Set-CsTeamsUpdateManagementPolicy` cmdlet 和 `-AllowPublicPreview` 参数以设置策略。

> [!NOTE]   
> AllowPreview 参数将很快被弃用。

## <a name="enable-public-preview"></a>启用公共预览版

要在桌面或 Web 客户端上启用公共预览版，需完成以下任务:

1. 选择个人资料左侧的三个圆点，以显示 Teams 菜单。
2. 选择“**关于** > **公共预览版**”。
3. 选择“**切换到公共预览版**”。

> [!NOTE]  
> 只有当 **显示预览版功能** 设置为 **已启用** 时，此选项才可用。

## <a name="teams-now-follows-office-preview-users"></a>当前，Teams 关注 Office 预览版用户

如果用户位于 Windows 上的 Office 365 客户端的当前频道(预览)中，则 **关注 Office 预览版** 的新全局策略默认设置将允许用户自动位于 Teams 的公共预览版频道中。

Microsoft Office 将继续从当前频道(预览)接收更新，同时 Teams 客户端将通过公共预览版频道接收更新。 此策略不会基于 Teams 频道切换 Office 频道。 

**如何保留不使用 Office 当前频道(预览)的现有 Teams 预览版用户?**

对于已被允许选择加入或选择退出 Teams 公共预览版且希望以当前形式维护该设置的现有用户，你需要从新的默认设置 - **关注 Office 预览版** 切换为 **已启用** (请参阅 [设置更新策略](#set-the-update-policy))

**如何选择退出此设置?**

可以禁用 Teams 管理中心的设置，从 **关注 Office 预览版** 切换为 **未启用** (请参阅 [设置更新策略](#set-the-update-policy))

## <a name="known-issues"></a>已知问题

当 Office 当前频道(预览)用户的更新策略设置为 **关注 Office 预览版** 时，其可以通过 Teams 客户端“关于”菜单退出 Teams 公共预览版。 此功能非预期功能，未来将被删除。 如果用户位于 Office 的当前频道(预览)中，则下次设备处于空闲状态时，Teams 客户端可能会自动将自己设置回公共预览版。

## <a name="related-topics"></a>相关主题

[公共开发人员预览版](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
