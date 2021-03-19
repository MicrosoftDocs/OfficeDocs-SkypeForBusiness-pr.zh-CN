---
title: 启用或禁用 Microsoft Teams 的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 了解如何以 Office 365 管理员角色打开或关闭 Microsoft Teams 中的来宾访问功能。
ms.openlocfilehash: c82172eb4d0c9fe50832d45ce2146c89d7e6d7d8
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884516"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>启用或禁用 Microsoft Teams 的来宾访问

> [!Note]

> 在 **2021 年 2** 月之前，来宾访问默认已关闭。 必须先为 Teams 启用来宾访问，管理员或团队所有者才能添加来宾。 启用来宾访问后，更改可能需要几个小时才能生效。 如果用户 **尝试将来宾** 添加到团队时看到消息"联系管理员"，则可能是来宾访问尚未打开或设置尚未生效。

> **2021** 年 2 月之后，对于尚未配置此设置的现有&，默认情况下将启用 Microsoft Teams 中的来宾访问。 实施此更改后，如果尚未在 Microsoft Teams 中配置来宾访问功能，将在租户中启用该功能。 如果希望组织的来宾访问保持禁用状态，则需要确认来宾访问设置设置为"关闭 **"，而不是**"服务 **默认"。**

> [!IMPORTANT]
> 启用来宾访问取决于 Azure Active Directory、Microsoft 365、SharePoint 和 Teams 中的设置。 有关详细信息，请参阅 [在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>在 Teams 管理中心配置来宾访问权限

1. 登录到 Microsoft [Teams 管理中心](https://admin.teams.microsoft.com/)。

2. 选择 **"组织范围的设置**  >  **""来宾访问"。**

3. 将 **"允许 Microsoft Teams 中的来宾访问"设置为****"打开"。**

    !["允许来宾访问"开关设置为"开" ](media/guest-access-setting.png)

4. 在 **"呼叫****、会议**"和"**消息** 传送"下，选择每个功能"开"或"关"，具体取决于要允许来宾用户使用的功能。

      - **进行私人呼叫** - 将此设置 **设置为"打开** "，允许来宾进行对等呼叫。
      - **允许 IP 视频** - 启用 **此设置** ，允许来宾在通话和会议中使用视频。
      - **屏幕共享模式** - 此设置控制来宾用户屏幕共享的可用性。
          - 将此设置设置为 **"已禁用** "，以删除来宾在 Teams 中共享其屏幕的能力。
          - 将此设置设置为 **"单个应用程序** "，以允许共享单个应用程序。
          - 将此设置设置为 **"整个屏幕** "以允许完整的屏幕共享。
      - **允许"现在** 开会"- **启用此设置** ，允许来宾使用 Microsoft Teams 中的"现在开会"功能。
      - **编辑已发送的消息** - 将此设置 **设置为"打开** "以允许来宾编辑他们之前发送的消息。
      - **来宾可以删除已发送的消息** – 将此设置 **设置为"打开** "以允许来宾删除以前发送的消息。
      - **聊天** - 启用 **此设置，** 让来宾能够在 Teams 中聊天。
      - **在对话中使用 Giphy** -启用此设置以允许来宾在对话中使用 Giphy。 Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。 每个 Giphy 都分配有一个内容分级。
      - **Giphy 内容分级** - 从下拉列表中选择分级：
          - **允许所有** 内容 - 来宾能够在聊天中插入所有 Giphy，而不考虑内容分级。
          - **中等** - 来宾能够在聊天中插入 Giphy，但会适度限制成人内容。
          - **严格** - 来宾可以在聊天中插入 Giphy，但无法插入成人内容。
      - **在对话中使用 Meme** -启用此设置以允许来宾在对话中使用 Meme。
      - **在对话中使用** 贴纸 - 启用此设置以允许来宾在对话中使用贴纸。

    ![Teams 中的来宾权限设置](media/manage-guest-access-image1.png)

5. 选择"**保存"。**

## <a name="external-access-federation-vs-guest-access"></a>外部访问（联合身份验证）与来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>另请参阅

[与 Microsoft 365 建立安全协作](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[阻止来自特定团队的来宾用户](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
