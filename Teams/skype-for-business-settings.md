---
title: 在 Microsoft 团队管理中心中管理 Skype for Business 设置
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队管理中心中管理 Skype for business 功能的设置。
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753557"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理 Skype for Business 设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

作为管理员，Microsoft 团队管理中心是你在其中管理你的组织中 Skype for business 用户的 Skype for business 功能的地方。 你可以在 " **skype** for business" 页面上管理[你的组织](#manage-skype-for-business-settings-for-your-organization)的设置，并在用户详细信息页面的 " **skype for business** " 选项卡上管理[单个用户](#manage-skype-for-business-settings-for-individual-users)的设置。

如果你的组织的共存模式未设置为 "**仅限团队**"，你将仅看到 " **Skype for business** " 页面。 同样，如果用户的共存模式不是**团队成员**，你将只能看到用户的 " **Skype for business** " 选项卡。 若要了解有关共存模式的详细信息，请参阅 [了解团队和 Skype for business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，并 [设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business 设置以前位于 Microsoft 团队管理中心的 **旧版门户** 中。 在停用旧版门户后，我们会将这些新位置的设置迁移到 Skype for business 管理的团队管理中心。

你必须分配有全局管理员或 Skype for Business 管理员的 [AZURE AD 管理员角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在 Microsoft 团队管理中心中管理 Skype for business 功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理你的组织的 Skype for Business 设置

在 Microsoft 团队管理中心的左侧导航中，转到 "**组织范围的设置**  >  **Skype for**business"。 在此处，你可以为组织中的所有 Skype for business 用户配置和管理 Skype 会议直播、状态隐私和移动设备通知。

### <a name="skype-meeting-broadcast"></a>Skype 会议直播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用以下设置管理组织中的 [Skype 会议直播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理中心中的 Skype 会议直播设置的屏幕截图":::

- **Skype 会议广播**：打开此项可为你的组织启用 Skype 会议直播。 启用此功能后，您需要为 [Skype 会议直播设置您的网络](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **请参阅预览功能**：打开此功能可提前获取新功能。
- **组织者可以安排匿名会议**：如果要让组织者创建允许组织外部的任何人无需登录即可加入的广播事件，请打开此操作。 
- **录制 Skype 会议直播会议**：启用此项可使组织者和演示者可以录制会议。  
- **面向与会者的帮助者支持 url**：输入组织的支持 url （如果与会者在会议期间需要帮助）。

### <a name="presence-and-mobile-notifications"></a>联机状态和手机通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用以下设置管理组织中的 Skype for business 状态隐私和手机通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中的状态设置的屏幕截图":::

#### <a name="presence"></a>状态

默认情况下，组织中的 Skype for Business 用户可以查看状态状态 (如 "可用"、"忙碌" 或 "离开其他 Skype for Business 用户") 。 选择下列操作之一，设置哪些人可以查看您的 Skype for Business 用户的状态。

- **自动显示状态信息**：你的组织中未添加到用户的 **外部** 或 **阻止** 列表的任何 Skype for business 用户都可以看到该用户的状态。
- **仅向用户的联系人显示状态信息**：用户联系人列表中未添加到其 **外部** 或 **被阻止** 列表的任何 Skype for business 用户都可以看到该用户的状态。 用户可以转到 "**设置**  >  **工具**"  >  **选项**，在 Skype for business 中覆盖此设置。

#### <a name="mobile-notifications"></a>手机通知

你可以设置 Skype for Business 移动用户是否收到有关传入和错过的即时消息、语音邮件和未接来电通知服务的通知。 根据你的组织中使用的移动设备，你可以使用 **Microsoft 推送通知服务**、 **Apple 推送通知服务**，或者同时使用这两者。

注意以下几项：

- 如果您关闭推送通知，用户将在其移动设备上下次启动 Skype for Business 时收到所有通知。
- 默认情况下，推送通知处于打开状态。 单个用户可在其移动设备上的 Skype for Business 中将其关闭。
- 当关闭推送通知时，用户将无法再打开推送通知。 

> [!IMPORTANT]
> [!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。 请参阅本 [隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理单个用户的 Skype for Business 设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要管理单个用户的 Skype for Business 设置，请在团队管理中心的左侧导航中，转到 " **用户**"，单击用户的显示名称以打开 "用户详细信息" 页面，然后选择 " **Skype for business 设置** " 选项卡。在此处，你可以为用户配置外部访问和会议设置。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息页面上的 "Skype for Business" 选项卡的屏幕截图":::

### <a name="external-access-settings"></a>外部访问设置

你可以有选择地允许或阻止用户是否可以与组织外部的人员进行通信。

- **外部 Skype For business 用户**：如果你希望允许用户与联盟域中的 Skype for business 用户通信，请打开此项。
- **外部 Skype 用户**：如果您希望允许用户与 Skype 用户通信，请打开此项。 

### <a name="meeting-settings"></a>会议设置

你可以为用户配置以下会议设置。

- **音频 & 视频**：选择以下音频和视频设置之一：

    - **None**：用户不能使用音频或视频。
    - **仅适用于音频**：用户可以使用音频，但不能使用视频。
    - **音频和视频**：用户可以使用音频和视频。
    - **音频和视频 (HD) **：用户可以使用音频和高清晰度视频。
    
- **& 会议中记录对话**：启用此项可允许用户录制对话和会议。
- **合规性**：如果你被法律要求保留电子存储的信息，请启用此项。 
