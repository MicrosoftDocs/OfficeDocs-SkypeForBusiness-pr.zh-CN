---
title: 设置Microsoft Teams Android 设备用户界面
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: 了解如何在 Teams Android 设备上设置用户界面。
ms.openlocfilehash: 0efabef522a791a56ac187da9a63fab10e4ab3e9
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392431"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>设置Microsoft Teams Android 设备用户界面

Microsoft Teams Android 设备可以根据分配给已登录帐户的许可证类型显示特定的用户界面。 可以重写此行为并控制显示哪个接口。 本文详细介绍了如何选择默认用户界面，以及如何使用 Powershell 策略更改接口。

Teams Android 设备上有三种类型的用户界面：

1. 用户
2. 公用区域
3. 会议

如果将 [用户许可证分配给](/microsoftteams/user-access) 帐户（如 E3 或 E5 许可证），Teams 设备将显示默认的最终用户界面，该界面在大多数用户方案中完全具有功能。 但是，如果设备正在执行特定功能（如公用区域电话或会议室），则这些用法有特定的用户界面。

以下三个图像显示了用户界面如何根据分配给用户帐户的许可证而更改。

## <a name="end-user-interface"></a>最终用户界面

为用户帐户分配了 E5 许可证。 这是一个用户许可证，因此设备会显示默认的最终用户界面：

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="用户模式界面。":::

## <a name="common-area-interface"></a>公用区域接口

在此映像中，已为用户帐户分配了[Microsoft Teams 共享设备许可证](/microsoftteams/teams-add-on-licensing/teams-shared-device-license)。 公用区域电话主要用于拨打和接听电话。 因此，拨号盘显示在显示器上：

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="公用区域电话接口。":::

## <a name="meeting-interface"></a>会议界面

此图显示分配有[Microsoft Teams 会议室许可证的](/MicrosoftTeams/rooms/rooms-licensing)用户帐户。 Teams 会议室许可证旨在用于会议室或共享空间，因此用户界面会更改，以便通过显示日历视图轻松加入会议：

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="会议界面。":::

> [!NOTE]
> 更改用户界面不会影响使用其他许可功能的能力。 例如，即使团队会议室许可证的默认视图是日历视图，如果帐户已获得正确许可和配置，你仍然可以拨打和接收公用电话交换网 (PSTN) 电话呼叫。

> [!IMPORTANT]
> 接口的其他元素会发生变化。 例如，为了防止最终用户注销公用区域电话或会议室设备，这些设备上的“注销”选项将移动到需要管理员权限才能访问的设置菜单的一部分。

## <a name="override-automatic-user-interface-detection"></a>重写自动用户界面检测

在某些情况下，可以选择将许可证分配给与其预期用途不匹配的帐户。 例如，可以将用户许可证分配给用于在 Android 上登录到 Teams 会议室 的帐户。 默认情况下，会看到最终用户界面，而不是会议室界面。 若要替代默认接口，请创建新的 [Teams IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy) 并将其应用于该帐户。

> [!NOTE]
> 分配给用户帐户的许可证必须至少具有与所需用户界面相同的许可证权利。 **Microsoft Teams 共享设备** 许可证仅允许公用区域电话用户界面。 **Teams 会议室** 许可证允许会议室和公共区域电话用户界面。 E3 或 E5 许可证支持所有登录模式。

下面是如何替代自动许可证检测的示例。 在此示例中，假设已为名为 conf-adams@contoso.com 的会议室资源帐户分配了 E3 许可证。 当此帐户登录时，你希望用户看到会议室用户界面。

### <a name="create-a-new-policy-and-assign-to-user"></a>创建新策略并分配给用户

1. 使用以下 cmdlet 启动远程Windows PowerShell会话并连接到 Microsoft Teams：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 创建新的 Teams IP 电话策略并将登录模式设置为“MeetingSignIn”：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 现在可以将此新策略分配给会议室资源帐户：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

向会议室资源帐户授予策略后，需要等待策略分配复制。 你还需要注销设备并重新登录。

## <a name="impact-on-microsoft-teams-admin-center"></a>对 Microsoft Teams 管理中心的影响

Microsoft Teams 管理中心允许你管理Microsoft Teams 设备。 有关使用 Teams 管理中心管理设备的详细信息，请参阅[在 Microsoft Teams 中管理设备](device-management.md)。

Teams 管理中心提供管理 Teams 电话的功能。 电话根据其功能筛选为三个选项卡之一：用户电话、公用区域电话和会议电话。

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Teams 管理中心中的电话标头。":::

与用户界面检测一样，Teams 电话根据分配给登录到手机的帐户的许可证进行分类。 例如，如果分配有 **Microsoft Teams 共享设备** 许可证的帐户登录到手机，则该手机将显示在默认的 **“所有电话**”部分和 **“公用区域电话**”部分中。

如果希望手机出现在其他部分中，可以向手机分配不同的许可证，或如上所述创建和分配 Teams IP 电话[策略。](#override-automatic-user-interface-detection)
