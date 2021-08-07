---
title: 设置Microsoft Teams Android 设备用户界面
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解如何在 Android 设备上设置Teams界面。
ms.openlocfilehash: f743a0f51015e7bd8fdabd41d120a187774c3370
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725677"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>设置Microsoft Teams Android 设备用户界面

Microsoft TeamsAndroid 设备可以基于分配给已登录帐户的许可证类型显示特定的用户界面。 可以重写此行为并控制显示哪个接口。 本文详细介绍了如何选择默认用户界面，以及如何使用 Powershell 策略更改界面。

Android 设备上有三种类型的用户界面Teams：

1. 用户
2. 公用区域
3. 会议

如果将[用户](/microsoftteams/user-access)许可证分配给帐户（例如 E3 或 E5 许可证），Teams 设备会显示默认最终用户接口，该界面已针对大多数用户方案提供完整功能。 但是，如果设备正在执行特定功能，例如公用区域电话或会议室，则这些用法有特定的用户界面。

以下三个图像显示了用户界面如何根据分配给用户帐户的许可证进行更改。 第一个图像为用户帐户分配了一个 E5 许可证。 这是用户许可证，因此设备会显示默认的最终用户接口：

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="用户界面":::

在此图像中，为用户帐户分配了一个 [公用区域电话许可证](/microsoftteams/set-up-common-area-phones)。 公用区域电话主要用于拨打和接听电话。 因此，拨号盘会显示在显示器上：

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="公用区域电话接口":::

最后，此图显示了分配有标准Microsoft Teams 会议室[用户帐户](/MicrosoftTeams/rooms/rooms-licensing)。 Teams 会议室许可证用于会议室或共享空间，因此用户界面会更改，以便通过显示日历视图轻松加入会议：

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="会议界面":::

> [!NOTE]
> 更改用户界面不会影响你使用其他许可功能的能力。 例如，即使团队聊天室许可证的默认视图是日历视图，如果帐户获得正确许可和配置，您仍然可以拨打和接听公用电话交换电话网络 (PSTN) 电话呼叫。

> [!IMPORTANT]
> 接口的其他元素会更改。 例如，为了防止最终用户注销公用区域电话或会议室设备，这些设备上的"注销"选项将移动到需要管理员权限才能访问的设置菜单的一部分。

## <a name="override-automatic-user-interface-detection"></a>替代自动用户界面检测

在某些情况下，可以选择将许可证分配给与预期用途不匹配的帐户。 例如，可以将用户许可证分配给用于登录 Android Teams 会议室帐户。 默认情况下，你将看到最终用户界面，而不是会议室界面。 若要替代默认接口，请创建一个新的 Teams [IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)，并应用到该帐户。

> [!NOTE]
> 分配给用户帐户的许可证必须至少具有与所需用户界面相同的许可证权利。 "公用电话"许可证仅允许"公用区域"电话用户界面。 会议室许可证允许会议室和公用区域电话用户界面。 E3 或 E5 许可证支持所有登录模式。

下面是如何替代自动许可证检测的示例。 本示例假设为名为 conf-adams@contoso.com 的会议室资源帐户分配了 E3 许可证。 此帐户登录后，您希望用户看到会议室用户界面。

### <a name="create-a-new-policy-and-assign-to-user"></a>创建新策略并分配给用户

1. 启动远程Windows PowerShell会话，并Microsoft Teams cmdlet 连接到远程会话：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 创建新的 Teams IP 电话 策略，将登录模式设置为"MeetingSignIn"：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 现在，您可以将此新策略分配给会议室资源帐户：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

将策略授予会议室资源帐户后，您需要等待策略分配复制。 还需要注销设备并重新登录。
