---
title: 在 Microsoft Teams 管理中心管理Skype for Business设置
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心管理Skype for Business功能的设置。
ms.openlocfilehash: 06c5cc4a199a7b29f2db97159850583d6927fc13
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563700"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理Skype for Business设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

作为管理员，Microsoft Teams 管理中心是管理组织中Skype for Business用户Skype for Business功能的地方。 可以在用户详细信息页 **的Skype for Business****选项卡** 上的Skype for Business页上管理 [组织的](#manage-skype-for-business-settings-for-your-organization)设置和 [单个用户](#manage-skype-for-business-settings-for-individual-users)的设置。

仅当组织的共存模式未设置为 **Teams** 时，才会看到 **Skype for Business** 页。 同样，如果用户的共存模式不是 **仅限 Teams**，则只会看到用户的 **Skype for Business** 选项卡。 若要详细了解共存模式，请参阅[了解 Teams 和Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)，并[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business设置以前在 Microsoft Teams 管理中心的 **旧门户** 中。 随着旧门户的停用，我们将设置迁移到 Teams 管理中心中用于Skype for Business管理的新位置。

必须向你分配全局管理员或Skype for Business管理员的 [Azure AD 管理员角色](/azure/active-directory/roles/permissions-reference)才能管理 Microsoft Teams 管理中心中的Skype for Business功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理组织的Skype for Business设置

在 Microsoft Teams 管理中心的左侧导航中，转到 **组织范围的** > 设置 **Skype for Business**。 在此处，可以为组织中的所有Skype for Business用户配置和管理Skype 会议广播、状态隐私和移动设备通知。

### <a name="skype-meeting-broadcast"></a>Skype 会议直播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用以下设置管理组织中的[Skype 会议广播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理中心Skype 会议广播设置的屏幕截图。":::

- **Skype 会议广播**：启用此功能，为组织启用Skype 会议广播。 启用此功能后，需要[为Skype 会议广播设置网络](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **请参阅预览功能**：启用此功能以提前访问新功能。
- **组织者可以安排匿名会议**：如果希望让组织者创建广播活动，允许组织外部的任何人加入，而无需登录，请将其打开。 
- **录制Skype 会议广播会议**：启用此功能，使组织者和演示者能够录制会议。  
- **支持与会者的 URL**：输入会议与会者在会议期间需要帮助时可以使用的组织支持 URL。

### <a name="presence-and-mobile-notifications"></a>状态和移动通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用以下设置管理组织中的Skype for Business状态隐私和移动通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中状态设置的屏幕截图。":::

#### <a name="presence"></a>状态

默认情况下，组织中的Skype for Business用户可以看到其他Skype for Business用户的状态 (，例如“可用”、“忙碌”或“离开”) 。 选择以下选项之一，设置谁可以看到Skype for Business用户的存在。

- **自动显示状态信息**：组织中任何尚未添加到 **用户外部或****阻止** 列表的Skype for Business用户都可以看到该用户的状态。
- **仅向用户的联系人显示状态信息**：用户联系人列表中未添加到其 **外部** 或 **已阻止** 列表的任何Skype for Business用户都可以看到该用户的状态。 用户可以通过转到“设置 **工具** > **”选项** 来替代Skype for Business **中的** > 此设置。

#### <a name="mobile-notifications"></a>移动通知

可以设置Skype for Business移动用户是否通过推送通知服务收到有关传入和错过的即时消息、语音邮件和未接听呼叫的警报。 根据组织中使用的移动设备，可以使用 **Microsoft 推送通知服务**、 **Apple 推送通知服务** 或这两者。

注意以下几项：

- 如果关闭推送通知，用户下次在移动设备上启动Skype for Business时将收到所有警报。
- 默认情况下，将打开推送通知。 单个用户可以在移动设备上的Skype for Business中将其关闭。
- 当关闭推送通知时，用户将无法再打开推送通知。 

> [!IMPORTANT]
> [!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。 请参阅此 [隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理单个用户的Skype for Business设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理单个用户的Skype for Business设置，请在 Teams 管理中心的左侧导航栏中转到 **“用户**”，单击用户的显示名称打开用户详细信息页，然后选择 **“Skype for Business设置”** 选项卡。在此处，可以为用户配置外部访问和会议设置。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息页上Skype for Business选项卡的屏幕截图。":::

### <a name="external-access-settings"></a>外部访问设置

你可以有选择地允许或阻止用户是否可以与组织外部的人员通信。

- **外部Skype for Business用户**：如果希望允许用户与联合域中的Skype for Business用户通信，请启用此功能。
- **外部 Skype 用户**：如果要允许用户与 Skype 用户通信，请启用此功能。 

### <a name="meeting-settings"></a>会议设置

可以为用户配置以下会议设置。

- **音频&视频**：选择以下音频和视频设置之一：

    - **无**：用户不能使用音频或视频。
    - **仅限音频**：用户可以使用音频，但不能使用视频。
    - **音频和视频**：用户可以使用音频和视频。
    - **音频和视频 (HD)**：用户可以使用音频和高清视频。
    
- **录制会议&对话**：打开此功能，允许用户录制对话和会议。
- **合规性**：如果在法律上需要保留以电子方式存储的信息，请启用此功能。