---
title: 设置 Microsoft Teams Android 设备用户界面
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
ms.openlocfilehash: 859c1d9d0f7a946f37b53ad81dc2a0637bb26621
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269317"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>设置 Microsoft Teams Android 设备用户界面

Microsoft Teams Android 设备可以根据分配给登录帐户的许可证类型显示特定用户界面。 可以重写此行为并控制显示的接口。 本文详细介绍了如何选择默认用户界面，以及如何使用 Powershell 策略更改接口。

Teams Android 设备上有三种类型的用户界面：

1. 用户
2. 公用区域
3. 会议

如果将 [用户许可证分配](/microsoftteams/user-access) 给帐户（如 E3 或 E5 许可证），Teams 设备将显示默认最终用户界面，该界面在大多数用户方案中都具有完全特色。 但是，如果设备正在执行特定的函数（例如公共区域电话或会议室），则这些用法有特定的用户界面。

以下三张图像显示用户界面如何根据分配给用户帐户的许可证进行更改。 

## <a name="end-user-interface"></a>最终用户界面 

为用户帐户分配了 E5 许可证。 这是用户许可证，因此设备显示默认的最终用户界面：

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="用户模式接口。":::

## <a name="common-area-interface"></a>公共区域接口

在此映像中，已为用户帐户分配了 [Common Area Phone 许可证](/microsoftteams/set-up-common-area-phones)。 公共区域电话主要用于拨打和接听电话。 因此，拨号盘显示在显示屏上：

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="公用区域电话接口。":::

## <a name="meeting-interface"></a>会议接口

此图显示了分配了[Microsoft Teams 会议室标准版许可证的](/MicrosoftTeams/rooms/rooms-licensing)用户帐户。 Teams 会议室许可证用于会议室或共享空间，因此用户界面会更改，以便通过显示日历视图轻松加入会议：

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="会议接口。":::

> [!NOTE]
> 更改用户界面不会影响你使用其他许可功能的能力。 例如，即使团队会议室许可证的默认视图是日历视图，如果帐户已正确许可和配置，仍可 (PSTN) 电话呼叫发出和接收公共交换机电话网络。

> [!IMPORTANT]
> 接口的其他元素会发生更改。 例如，为了防止最终用户注销公共区域电话或会议室设备，这些设备上的“注销”选项将移动到需要管理员访问权限的设置菜单的一部分。

## <a name="override-automatic-user-interface-detection"></a>替代自动用户界面检测

在某些情况下，可以选择将许可证分配给与预期用途不匹配的帐户。 例如，可以将用户许可证分配给要在 Android 上登录到Teams 会议室的帐户。 默认情况下，你会看到最终用户界面，而不是会议室接口。 若要重写默认接口，请创建新的 [Teams IP Phone 策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 并将其应用到该帐户。

> [!NOTE]
> 分配给用户帐户的许可证必须至少具有与所需用户界面相同的许可证权利。 Common Area Phone 许可证仅允许通用区域电话用户界面。 会议室许可证允许会议室和公共区域电话用户界面。 E3 或 E5 许可证支持所有登录模式。

下面是一个有关如何替代自动许可证检测的示例。 在此示例中，假定已为名为 conf-adams@contoso.com 的会议室资源帐户分配了 E3 许可证。 登录此帐户时，你希望用户看到会议室用户界面。

### <a name="create-a-new-policy-and-assign-to-user"></a>创建新策略并将其分配给用户

1. 启动远程Windows PowerShell会话并使用以下 cmdlet 连接到 Microsoft Teams：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 创建新的 Teams IP Phone 策略并将登录模式设置为“MeetingSignIn”：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 现在可以将此新策略分配给会议室资源帐户：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

将策略授予会议室资源帐户后，需要等待策略分配复制。 还需要注销设备并重新登录。

## <a name="impact-on-microsoft-teams-admin-center"></a>对 Microsoft Teams 管理中心的影响

Microsoft Teams 管理中心允许你管理 Microsoft Teams 设备。 有关使用 Teams 管理中心管理设备的详细信息，请参阅 [Microsoft Teams 中的“管理设备](device-management.md)”。


Teams 管理中心提供管理 Teams 电话的功能。 手机根据其功能筛选成三个选项卡之一：用户电话、公共区域电话和会议电话。 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Teams 管理中心内的电话标头。":::

与用户界面检测一样，Teams 手机根据分配给登录到手机的帐户的许可证进行分类。 例如，如果分配有公共区域电话许可证的帐户登录到手机，则该电话将同时显示在默认 **的“所有电话”** 部分和 **“公共区域电话** ”部分中。

如果希望手机显示在其他部分中，可以为手机分配不同的许可证，也可以创建和分配 Teams IP Phone 策略，如 [上所述](#override-automatic-user-interface-detection)。
