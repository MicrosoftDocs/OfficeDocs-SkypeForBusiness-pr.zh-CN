---
title: Microsoft Teams 中的公共预览版
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Learn about the public preview in Microsoft Teams. Try out new features and provide feedback.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ffdd34d8a36726d96bc44ae766e91ca6ae77280b
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869583"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公共预览版

> [!NOTE] 
> 预览版中包含的功能可能不完整，在公开发布之前可能会发生更改。 它们仅用于评估和探索目的。 Office 365 政府社区云 (GCC) 不支持预览功能。

Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.

有关 Teams 公共预览版中可用内容的列表，请访问 [Microsoft Teams 公共预览版技术说明](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)、[Teams 管理员功能的发行说明](/OfficeUpdates/teams-admin)和 [Office 当前频道发行说明 (预览版) ](/officeupdates/current-channel-preview)。

## <a name="set-the-update-policy"></a>设置更新策略

Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.

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
