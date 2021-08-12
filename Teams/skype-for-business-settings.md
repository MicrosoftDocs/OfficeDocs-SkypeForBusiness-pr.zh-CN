---
title: 在 Skype for Business 管理中心Microsoft Teams设置
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
description: 了解如何在管理中心管理Skype for Business功能Microsoft Teams设置。
ms.openlocfilehash: f05bdd7dfb53e75d5cc83945985dd6b511635d5ab5792afc0291b5349433ae22
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280557"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>在 Skype for Business 管理中心Microsoft Teams设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

作为管理员，Microsoft Teams管理中心是管理组织中Skype for Business用户Skype for Business功能的地方。 可以在用户[详细信息页面的](#manage-skype-for-business-settings-for-your-organization)"Skype for Business"选项卡上管理组织的设置以及Skype for Business用户的[](#manage-skype-for-business-settings-for-individual-users)设置。 

如果组织的共存 **Skype for Business** 未设置为"仅"，你将只能看到Teams **页面**。 同样，如果用户的共存模式Skype for Business，则只会看到用户的"Teams **选项卡**。 若要详细了解共存模式，请参阅了解Teams Skype for Business[和](teams-and-skypeforbusiness-coexistence-and-interoperability.md)互操作性以及设置[共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

> [!NOTE]
> Skype for Business之前在旧版门户中 **，Microsoft Teams** 管理中心。 旧门户停用后，我们已将设置迁移到 Teams 管理中心中的这些新Skype for Business位置。

必须分配全局管理员或管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员Skype for Business才能Skype for Business管理中心Microsoft Teams功能。

## <a name="manage-skype-for-business-settings-for-your-organization"></a>管理Skype for Business组织设置

在管理中心的左侧导航Microsoft Teams，转到"**组织范围的设置"Skype for Business。**  >   在这里，你可以为组织Skype 会议用户配置和管理Skype for Business、状态隐私和移动设备通知。

### <a name="skype-meeting-broadcast"></a>Skype 会议直播

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

使用以下设置管理Skype 会议[广播](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)。

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="管理Skype 会议广播设置的屏幕截图":::

- **Skype 会议广播**：打开此选项，为Skype 会议启用直播。 启用此功能后，需要为"广播"设置[Skype 会议网络](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)。
- **请参阅预览功能**：启用此功能可提前访问新功能。
- **组织者可以安排匿名会议**：如果希望组织者创建允许组织外部任何人无需登录即可加入的直播活动，请启用此功能。 
- **录制Skype 会议** 直播会议：启用此功能以允许组织者和演示者录制会议。  
- **与会者的支持 URL：** 输入组织的支持 URL，与会者在会议期间需要帮助时可以使用该 URL。

### <a name="presence-and-mobile-notifications"></a>状态和移动通知

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


使用以下设置管理Skype for Business状态隐私和移动通知。

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="管理中心中状态设置的屏幕截图":::

#### <a name="presence"></a>状态

默认情况下，Skype for Business中的用户可以看到其他 (的状态，例如") "或"离开Skype for Business状态。 选择下列选项之一，设置谁可以看到你的Skype for Business状态。

- **自动显示状态信息**：Skype for Business未添加到用户的"外部"或"阻止"列表中的任何用户都可以看到该用户的显示状态。 
- 仅向 **用户的** 联系人显示状态信息：用户的联系人列表中未添加到"外部"或"阻止"列表中的任何 Skype for Business 用户都可以看到该用户的显示状态。   用户可以在"工具选项"Skype for Business中设置  >  **此设置**  >  。

#### <a name="mobile-notifications"></a>移动通知

你可以设置你的Skype for Business用户是否通过推送通知服务收到有关传入和错过的即时消息、语音邮件和错过的呼叫的警报。 根据组织中使用的移动设备，可以使用 **Microsoft** 推送通知服务和/或 **Apple 推送通知** 服务。

注意以下几项：

- 如果关闭推送通知，用户在下次在移动设备上启动推送通知Skype for Business收到所有警报。
- 默认情况下，推送通知已打开。 单个用户可以在移动设备上Skype for Business关闭它们。
- 当关闭推送通知时，用户将无法再打开推送通知。 

> [!IMPORTANT]
> [!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。 请参阅 [本隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。

## <a name="manage-skype-for-business-settings-for-individual-users"></a>管理Skype for Business用户的用户设置

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

若要Skype for Business用户设置，请在 Teams 管理中心的左侧导航栏中，转到"用户"，单击用户的 显示名称以打开用户详细信息页，然后选择 **"Skype for Business 设置"选项卡**。在这里，您可以为用户配置外部访问和会议设置。

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="用户详细信息Skype for Business选项卡的屏幕截图":::

### <a name="external-access-settings"></a>外部访问设置

可以选择性地允许或阻止用户是否可以与组织外部人员通信。

- **外部Skype for Business用户**：如果希望允许用户与联合域中的Skype for Business通信，请启用此功能。
- **外部Skype用户**：如果希望允许用户与用户通信，请Skype此功能。 

### <a name="meeting-settings"></a>会议设置

你可以为用户配置以下会议设置。

- **音频和视频&：** 选择以下音频和视频设置之一：

    - **无**：用户不能使用音频或视频。
    - **仅音频**：用户可以使用音频，但不能使用视频。
    - **音频和视频**：用户可以使用音频和视频。
    - **音频和视频 (HD) ：** 用户可以使用音频和视频。
    
- **录制&** 对话：启用此功能以允许用户录制对话和会议。
- **合规性**：如果法律要求您保留电子存储的信息，请启用此功能。