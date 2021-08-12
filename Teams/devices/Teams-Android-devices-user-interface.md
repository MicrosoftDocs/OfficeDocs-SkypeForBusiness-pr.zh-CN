---
title: 设置 Microsoft Teams Android 设备用户接口
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
description: 了解如何在 Android 设备上Teams用户界面。
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327348"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>设置 Microsoft Teams Android 设备用户接口

Microsoft TeamsAndroid 设备可以基于分配给登录帐户的许可证类型显示特定的用户界面。 你可以替代此行为并控制显示哪个接口。 本文详细介绍了如何选择默认用户界面以及如何使用 Powershell 策略更改界面。

Android 设备上有三种类型的用户界面Teams：

1. 用户
2. 公用区域
3. 会议

如果将[用户](/microsoftteams/user-access)许可证分配给帐户（如 E3 或 E5 许可证），Teams 设备将显示默认最终用户界面，该界面为大多数用户方案提供完整功能。 但是，如果设备正在执行特定功能，如公用区域电话或会议室，则存在用于这些用途的特定用户界面。

以下三个图像显示了如何根据分配给用户帐户的许可证更改用户界面。 第一个图像中，为用户帐户分配了 E5 许可证。 这是用户许可证，因此设备显示默认最终用户界面：

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="用户模式界面":::

在此图像中，用户帐户已分配有公用 [区域电话许可证](/microsoftteams/set-up-common-area-phones)。 公用区域电话主要用于拨打和接听电话。 因此，拨号盘会显示在显示器上：

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="公用区域电话界面":::

最后，此图显示分配了 Microsoft Teams 会议室[许可证的](/MicrosoftTeams/rooms/rooms-licensing)用户帐户。 Teams 会议室许可证旨在用于会议室或共享空间，因此用户界面会更改，以便通过显示日历视图轻松加入会议：

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="会议界面":::

> [!NOTE]
> 更改用户界面不会影响你使用其他许可功能的能力。 例如，即使团队会议室许可证的默认视图是日历视图，但如果帐户获得正确的许可和配置，您仍可以拨打和接听公用电话交换网 (PSTN) 电话呼叫。

> [!IMPORTANT]
> 接口的其他元素会发生变化。 例如，为了防止最终用户注销公用区域电话或会议室设备，这些设备上的"注销"选项将移动到需要管理员权限才能访问的设置菜单的一部分。

## <a name="override-automatic-user-interface-detection"></a>替代自动用户界面检测

在某些情况下，你可以选择将许可证分配给与预期用途不匹配的帐户。 例如，你可以将用户许可证分配给要登录到 Android 上的Teams 会议室帐户。 默认情况下，你将看到最终用户界面，而不是会议室界面。 若要覆盖默认接口，请创建一Teams [IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)，并应用于该帐户。

> [!NOTE]
> 分配给用户帐户的许可证必须至少具有与所需用户界面相同的许可证权利。 公共区域电话许可证仅允许公共区域电话用户界面。 会议室许可证允许会议室和公用区域电话用户界面。 E3 或 E5 许可证支持所有登录模式。

下面是如何覆盖自动许可证检测的示例。 本示例假定名为 conf-adams@contoso.com 会议室资源帐户已分配有 E3 许可证。 当此帐户登录时，您希望用户看到会议室用户界面。

### <a name="create-a-new-policy-and-assign-to-user"></a>创建新策略并分配给用户

1. 启动远程Windows PowerShell会话，然后Microsoft Teams cmdlet 连接到远程会话：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 创建新的 ip Teams IP 电话 策略，将登录模式设置为"MeetingSignIn"：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 现在，您可以将此新策略分配给会议室资源帐户：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

将策略授予会议室资源帐户后，您需要等待策略分配复制。 你还需要注销设备并重新登录。
