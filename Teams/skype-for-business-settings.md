---
title: 在 Microsoft Teams 管理中心管理 Skype for Business 设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心管理 Skype for Business 功能的设置。
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834212"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理 Skype for Business 设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

作为管理员，Microsoft Teams 管理中心是管理组织中 Skype for Business 用户的 Skype for Business 功能的地方。 可以在 Skype [](#manage-skype-for-business-settings-for-your-organization) **for Business** 页面上管理组织的设置，在用户 [](#manage-skype-for-business-settings-for-individual-users)详细信息页面的 **"Skype for Business"** 选项卡上管理单个用户的设置。

如果你的组织共存模式未设置为 **Teams，** 你将只能看到 Skype for Business **页面**。 同样，如果用户的共存模式不是仅 **Teams，** 你将只看到用户的 Skype for Business **选项卡**。 若要了解有关共存模式的信息，请参阅了解 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 和 Skype for Business 共存和互操作性以及 [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business 设置 **以前位于** Microsoft Teams 管理中心的旧版门户中。 旧门户停用后，我们已将设置迁移到 Teams 管理中心中用于 Skype for Business 管理的这些新位置。

必须分配全局管理员或 Skype for Business 管理员 [的 Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 管理员角色，才能在 Microsoft Teams 管理中心管理 Skype for Business 功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理组织的 Skype for Business 设置

在 Microsoft Teams 管理中心的左侧导航中，转到 **组织范围的**  >  **Skype for Business 设置**。 在这里，你可以为贵组织的所有 Skype for Business 用户配置和管理 Skype 会议直播、状态隐私和移动设备通知。

### <a name="skype-meeting-broadcast"></a>Skype 会议直播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用以下设置在你的 [组织中管理 Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 会议直播。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理中心中的 Skype 会议直播设置的屏幕截图":::

- **Skype 会议直播**：打开此选项以为贵组织启用 Skype 会议直播。 启用此功能后，你需要为 Skype 会议直播 [设置你的网络](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **查看预览功能**：启用此功能可提前访问新功能。
- **组织者可以安排匿名会议**：如果希望组织者创建允许组织外部任何人无需登录即可加入的直播活动，请启用此功能。 
- **录制 Skype 会议直播会议**：启用此功能以允许组织者和演示者录制会议。  
- **与会者的支持 URL：** 输入与会者在会议期间需要帮助时可以使用的组织支持 URL。

### <a name="presence-and-mobile-notifications"></a>状态和移动通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用以下设置在你的组织中管理 Skype for Business 状态隐私和移动通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中状态设置的屏幕截图":::

#### <a name="presence"></a>状态

默认情况下，你组织的 Skype for Business 用户可以看到状态 (其他 Skype for Business 用户的") "或"离开"状态。 选择下列选项之一，设置哪些人可以看到 Skype for Business 用户。

- **自动显示状态信息**：您的组织中尚未添加到用户的"外部"或"阻止"列表中的任何 Skype for  Business用户都可以看到该用户的显示状态。
- **仅向用户的** 联系人显示状态信息：用户的联系人列表中未添加到"外部"或"阻止"列表中的任何 Skype for Business 用户都可以看到该用户的显示状态。 用户可以在 Skype for Business 中通过访问"设置工具选项  >  **"来替代**  >  **此设置**。

#### <a name="mobile-notifications"></a>移动通知

你可以设置 Skype for Business 移动用户是否通过推送通知服务收到有关传入和错过的即时消息、语音邮件和错过的呼叫的通知。 根据组织中使用的移动设备，可以使用 **Microsoft 推送通知** 服务和/或 **Apple 推送通知** 服务。

注意以下几项：

- 如果关闭推送通知，用户在下次在移动设备上启动 Skype for Business 时将收到通知。
- 默认情况下，推送通知已打开。 个人用户可以在移动设备上的 Skype for Business 中将其关闭。
- 当关闭推送通知时，用户将无法再打开推送通知。 

> [!IMPORTANT]
> [!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。 请参阅 [本隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理单个用户的 Skype for Business 设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理单个用户的 Skype for Business 设置，请在 Teams 管理中心的左侧导航栏中转到"用户"，单击用户的 显示名称 以打开用户详细信息页面，然后选择 **"Skype for Business** 设置"选项卡。在这里，您可以为用户配置外部访问和会议设置。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息页面上 Skype for Business 选项卡的屏幕截图":::

### <a name="external-access-settings"></a>外部访问设置

可以选择性地允许或阻止用户是否可以与组织外部人员通信。

- **外部 Skype for Business 用户**：如果希望允许用户与联盟域中的 Skype for Business 用户通信，请启用此功能。
- **外部 Skype** 用户：如果希望允许用户与 Skype 用户通信，请启用此功能。 

### <a name="meeting-settings"></a>会议设置

您可以为用户配置以下会议设置。

- **音频和视频&：** 选择以下音频和视频设置之一：

    - **无**：用户不能使用音频或视频。
    - **仅音频**：用户可以使用音频，但不能使用视频。
    - **音频和视频**：用户可以使用音频和视频。
    - **音频和视频 (HD) ：** 用户可以使用音频和视频。
    
- **录制&** 对话：启用此功能以允许用户录制对话和会议。
- **合规性**：如果法律要求您保留电子存储的信息，请启用此功能。 
