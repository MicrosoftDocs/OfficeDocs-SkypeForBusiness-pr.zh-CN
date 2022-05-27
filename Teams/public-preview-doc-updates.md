---
title: Microsoft Teams 中的公共预览版
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: high
ms.openlocfilehash: 49ea7fe244b46840e80bfa4093706d314c708dcb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675064"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公共预览版

> [!NOTE] 
> 预览版中包含的功能可能不完整，在公开发布之前可能会发生更改。 它们仅用于评估和探索目的。 Office 365 政府社区云 (GCC) 不支持预览功能。

Microsoft Teams 的公共预览版可让用户抢先体验 Teams 中的未发布功能。预览版允许探索和测试即将推出的功能。我们也欢迎大家对公共预览版中的任何功能提出反馈意见。公共预览版是为每个 Teams 用户单独启用的，因此不必担心影响整个组织。

有关 Teams 公共预览版中可用内容的列表，请访问 [Microsoft Teams 公共预览版技术说明](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)、 [Teams 管理功能的发布说明](/OfficeUpdates/teams-admin)，以及 [Teams 中的新增内容](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。

## <a name="set-the-update-policy"></a>设置更新策略

为每个用户启用公共预览，并在管理策略中控制打开公共预览的选项。更新策略用于管理 Teams 和 Office 预览用户，这些用户将会在 Teams 应用中看到预发布或预览功能。你可以使用全局（Org-wide默认）策略并对其进行自定义，或者为用户创建一个或多个自定义策略。

1. 登录到 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)。

2. 选择“**Teams**” > “**Teams 更新策略**”。

1. 选择 **添加** 以新建策略，或选择现有策略以打开 **更新策略**。

2. 命名更新策略，添加说明，然后选择 **显示预览版功能** 的设置。

   -   **关注 Office 预览版**（默认）
       - 此新的默认选项将为在 Office 当前频道（预览）中注册的用户自动启用 Teams 公共预览版功能。 
       - 最终用户无需执行更多操作。
   -   **已启用**
       - 无论用户是否在 Office 当前频道（预览）中注册，此选项都将启用 Teams 公共预览版。 
       - 此外，最终用户还必须在其 Teams 应用中选择加入 Teams 公共预览版。

   > [!NOTE]  
   > 对于 Teams 公共预览版中不在 **当前频道(预览)** 中的现有用户，IT 管理员需要从默认的 **关注 Office 预览版** 切换为 **已启用**。
 
   - **未启用** 
     - 最终用户将无法使用 Teams 公共预览版功能。

    ![显示预览版设置对话。](media/public-preview-policy.png)  

还可以同时使用 PowerShell `Set-CsTeamsUpdateManagementPolicy` cmdlet 和 `-AllowPublicPreview` 参数以设置策略。

## <a name="enable-public-preview"></a>启用公共预览版

要在桌面或 Web 客户端上启用公共预览版，需完成以下任务:

1. 选择个人资料左侧的三个圆点，以显示 Teams 菜单。
2. 选择“**关于** > **公共预览版**”。
3. 选择“**切换到公共预览版**”。

> [!NOTE]  
> 只有当 **显示预览版功能** 设置为 **已启用** 时，此选项才可用。

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Windows 上 Microsoft Teams 会议室的公共预览版

默认情况下，公共预览版处于关闭状态。 启用公共预览版后，最终用户可以访问启用的 Teams 会议室上的公共预览版功能。 若要启用公共预览版，请将 ```<EnablePublicPreview>True</EnablePublicPreview>``` 添加到 XML 配置文件。

建议将 5-10 台设备注册到公共预览版。 

所有公共预览版功能均在 [Microsoft Teams 公共预览版 - Microsoft 技术社区](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) 中公布

## <a name="teams-now-follows-office-preview-users"></a>当前，Teams 关注 Office 预览版用户

如果用户位于 Windows 和 Mac 上的 Office 365 客户端的当前频道(预览)中，则 **关注 Office 预览版** 的新全局策略默认设置将允许用户自动位于 Teams 的公共预览版频道中。

Microsoft Office 将继续从当前频道(预览)接收更新，同时 Teams 客户端将通过公共预览版频道接收更新。 此策略不会基于 Teams 频道切换 Office 频道。 

**如何保留不使用 Office 当前频道(预览)的现有 Teams 预览版用户?**

对于已被允许选择加入或选择退出 Teams 公共预览版且希望以当前形式维护该设置的现有用户，你需要从新的默认设置 - **关注 Office 预览版** 切换为 **已启用** (请参阅 [设置更新策略](#set-the-update-policy))

**如何选择退出此设置?**

可以禁用 Teams 管理中心的设置，从 **关注 Office 预览版** 切换为 **未启用** (请参阅 [设置更新策略](#set-the-update-policy))

## <a name="related-topics"></a>相关主题

[公共开发人员预览版](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
