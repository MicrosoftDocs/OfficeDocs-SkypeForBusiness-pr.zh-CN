---
title: 打开或关闭 Microsoft Teams 中的来宾访问
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
- chat-teams-channels-revamp
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 了解如何以Office 365管理员身份在 Microsoft Teams 中打开或关闭来宾访问功能。
ms.openlocfilehash: 906a5554d4dbcb03efabb2300a5a900ad3c8dc21
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199094"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>打开或关闭 Microsoft Teams 中的来宾访问

本文介绍如何在 Teams 中配置来宾访问设置（包括通话、会议和聊天）。 Teams 中的来宾访问还需要在 Microsoft 365 中配置其他设置，包括 Azure AD、Microsoft 365 组 和 SharePoint 中的设置。 如果你已准备好开始邀请来宾加入 Teams，请阅读以下内容之一：

- 若要为 Teams 配置来宾访问以供一般使用，请参阅[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。
- 若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册以实现团队访问，请参阅[创建托管有来宾的 B2B 外联网](/microsoft-365/solutions/b2b-extranet)。

> [!NOTE]
> 如果只希望查找、通话、聊天以及安排与其他组织人员的会议，请使用[外部访问](manage-external-access.md)。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>在 Teams 管理中心配置来宾访问

1. 登录到 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)。

2. 选择 **“用户** > **来宾访问权限**”。

3. 将 **“允许 Teams 中的来宾访问”** 设置为 **“打开**”。

    ![“允许来宾访问”开关设置为“开”。](media/guest-access-setting.png)

4. 在“**通话**”、“**会议和****消息传送**”下，为每个功能选择“**打开**”或“**关闭”**，具体取决于要允许来宾使用的内容。

      - **进行私人呼叫** - **打开此设置以** 允许来宾进行对等呼叫。
      - **IP 视频** - **打开此设置以** 允许来宾在其通话和会议中使用视频。
      - **屏幕共享模式** – 此设置控制来宾屏幕共享的可用性。
          - 将此设置设置为 **“已禁用** ”，以删除来宾在 Teams 中共享其屏幕的功能。
          - 将此设置转换为 **“单个应用程序** ”以允许共享单个应用程序。
          - 将此设置更改为 **“整个屏幕** ”以允许完整的屏幕共享。
      - **立即开会** - **打开此设置以** 允许来宾使用 Microsoft Teams 中的“立即开会”功能。
      - **编辑已发送的邮件** - **打开此设置以** 允许来宾编辑他们以前发送的邮件。
      - **删除已发送邮件** – **启用此设置以** 允许来宾删除他们以前发送的邮件。
      - **删除聊天** - **启用此设置以** 允许来宾删除整个聊天对话。
      - **聊天** – **启用此设置，** 使来宾能够在 Teams 中使用聊天。
      - **对话中的 Giphy** - **打开此设置以** 允许来宾在对话中使用 Giphys。 Giphy 是一个在线数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。 为每个 Giphy 分配内容分级。
      - **Giphy 内容分级** - 从下拉列表中选择分级：
          - **允许所有内容** - 无论内容分级如何，来宾都可以在聊天中插入所有 Giphys。
          - **中等** - 来宾将能够插入聊天中的 Giphys，但会受到成人内容的适度限制。
          - **严格** - 来宾可以在聊天中插入 Giphys，但将受到限制，不能插入成人内容。
      - **对话中的 Meme** - **打开此设置以** 允许来宾在对话中使用 Meme。
      - **对话中的贴纸** – 打开 **此设置以允许** 来宾在对话中使用贴纸。
      - **邮件的沉浸式阅读器** - **打开此设置以** 允许来宾 [在 Teams 中使用沉浸式阅读器](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)。

    ![Teams 中的来宾权限设置。](media/manage-guest-access-image1.png)

5. 选择“**保存**”。

## <a name="turning-guest-access-off"></a>关闭来宾访问权限

如果在 Teams 中关闭来宾访问权限，现有来宾将失去对其团队的访问权限。 但不会从团队中删除他们。 他们仍然对团队成员可见，并且后者可以 @提及他们。 如果再次启用 Teams 来宾访问权限，他们将重新获得访问权限。

如果计划关闭来宾访问权限，可能需要建议团队所有者手动从其团队中删除来宾帐户。 虽然这些来宾无权访问，但其帐户在团队中可见可能会导致其他团队成员感到困惑。


## <a name="see-also"></a>另请参阅

[与 Microsoft 365 建立安全协作](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[阻止来自特定团队的来宾](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
