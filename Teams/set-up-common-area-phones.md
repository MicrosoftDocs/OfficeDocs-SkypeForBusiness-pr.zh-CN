---
title: 为 Microsoft Teams 设置公用区域电话
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: 了解如何为大厅、接待区和会议室设置公用区域电话。
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392152"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>为 Microsoft Teams 设置公用区域电话

公用区域电话通常放置在大厅等区域或可供许多人拨打电话的另一个区域：接待区、大厅或会议电话。 公用区域电话使用绑定到 **Microsoft Teams 共享设备** 许可证的帐户登录。

本文概述了如何将 Teams 电话设备部署和配置为共享空间的公用区域电话。 若要获得更完整的会议室体验（包括音频会议），请考虑改为使用 **Teams 会议室** 设备购买专用Teams 会议室许可证。 有关Teams 会议室的详细信息，请参阅 [Microsoft Teams 会议室](rooms/index.md)。

> [!NOTE]
> 在 Skype for Business Server 中创建的公用区域电话对象的帐户无法迁移到 Microsoft Teams。 按照本文中的步骤为 Teams 重新创建这些帐户，并根据需要迁移公用电话交换网 (PSTN) 连接。

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

首先，需要购买 **Teams 共享设备** 许可证，并确保拥有经过认证的手机。 若要搜索并详细了解已认证的手机，请转到[Microsoft Teams 设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在 [Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，转到 **“计费** > **购买服务**”。

2. 如果尚未显示 **“按类别查看**”部分，请转到 **“从Microsoft购买**”，然后选择“**查看产品**”。 然后选择“ **协作和通信**”。  

3. 在产品列表中，找到 **Microsoft Teams 共享设备**，然后选择 **“详细信息**”。

4. 输入所需的许可证数，然后选择“ **购买**”。

> [!NOTE]
> 如果在环境中使用 Intune，并且具有要求设备符合性的条件访问规则，则需要分配 **Azure Active Directory Premium计划 1**，并将 **许可证Intune** 公用区域电话的设备帐户。
>
> 公用区域电话可能会受到条件访问规则和其他标识配置（如多重身份验证）的影响。 有关详细信息 [，请参阅 Teams Android 设备的身份验证最佳做法](devices/authentication-best-practices-for-android-devices.md) 。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步骤 2 - 创建新的用户帐户并分配许可证

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

如果要同时部署多个公用区域电话，请了解如何 [使用 PowerShell](#using-powershell) 创建帐户和分配许可证。

如果要部署一台设备：

1. 在 [Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，转到 **“用户** > **”“活动用户** > **”“添加用户**”。

2. 为名字输入用户名，`Reception`为第二个名称输入类似`Main`用户名。

3. 如果它不自动生成显示名称，则输入显示名称，例如 `Main Reception`。

4. 输入用户名，例如 `MainReception` 或 `Mainlobby`。

5. 手动设置公用区域电话的密码。 若要设置密码，请取消选中 **“自动创建密码** ”，并 **要求此用户在首次登录时更改其密码**。  

    > [!IMPORTANT]
    > 强烈建议手动为公用区域电话设置密码，以防止最终用户出现登录问题。

6. 选择设备的使用位置，并将 **Teams 共享设备** 许可证分配给帐户。 如果需要任何其他许可证（如通话套餐），请分配它们。

> [!NOTE]
> 无需添加具有电话系统功能的许可证。 它包含在 **Teams 共享设备** 许可证中。
>
> 如果不将 Microsoft 电话系统与直接路由或运营商连接配合使用，则可能需要添加 **通话套餐** 许可证。 有关许可证的详细信息，请参阅 [Microsoft Teams 加载项许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

如果要同时为多个用户帐户创建和分配许可证，请使用 PowerShell。 有关详细信息，请参阅[使用 PowerShell 创建Microsoft 365 个用户帐户](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)和使用 [PowerShell 将Microsoft 365 个许可证分配给用户帐户](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

## <a name="step-3---set-policies-for-common-area-phones"></a>步骤 3 - 设置公用区域电话的策略

使用策略控制公用区域电话上的用户可以使用哪些功能。

### <a name="ip-phone-policies"></a>IP 电话策略

仅当登录电话的帐户使用 **Teams 共享设备** 许可证以外的其他许可时，才能修改 Teams IP 电话策略。  如果已获得Microsoft 365 E3、E5 订阅或Office 365 企业版 E1、E3 或 E5 订阅的许可，则可以修改 IP 电话策略。  如果你在公用区域电话帐户上使用 **Teams 会议室** 许可证，它将只允许你使用`MeetingRoomSignIn`模式。 `MeetingRoomSignIn` 模式在大多数常见的区域电话上不可用。 有关手机界面支持的替代的详细信息，请参阅[设置Microsoft Teams Android 设备用户界面](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection)。

使用 Teams IP 电话策略，将 [SignInMode 参数](/powershell/module/skype/new-csteamsipphonepolicy#parameters) 设置为 以 `CommonAreaPhoneSignIn` 启用 Teams 电话设备上的公用区域电话体验。

若要配置其他参数，请考虑创建 [IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy)。 例如，如果在公共区域使用公用区域电话，请设置 IP 电话策略以限制搜索组织的全局通讯簿并阻止热桌面。 若要了解详细信息，请参阅 [设置 Teams Android 设备用户界面](/microsoftteams/devices/Teams-Android-devices-user-interface)。

### <a name="calling-policies"></a>通话策略

使用呼叫策略在公用区域电话上启用专用呼叫、呼叫转接或同时响铃。 若要了解详细信息，请参阅 [Teams 中的呼叫和呼叫转接](teams-calling-policy.md)。

默认情况下，不为公用区域电话启用呼叫寄存。 需要创建策略才能启用它。 若要了解详细信息，请参阅[呼叫寄存和检索Microsoft Teams](call-park-and-retrieve.md)。

> [!NOTE]
> 分配策略后，注销手机并重新登录。 策略分配可能需要长达一小时才能生效。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步骤 4 - 获取和分配电话号码

请参阅 [管理组织的电话号码](manage-phone-numbers-landing-page.md) ，了解如何根据 PSTN 连接选项获取和分配电话号码。

## <a name="step-5---sign-in"></a>步骤 5 - 登录

创建并配置用户帐户后，即可登录到手机。 根据要部署的手机数量，有三个登录选项：

- [本地登录](#local-sign-in)。
- [从其他设备登录](#sign-in-from-another-device)。
- [使用 Teams 管理中心登录](#sign-in-using-the-teams-admin-center)。

### <a name="local-sign-in"></a>本地登录

若要使用用户名和密码在本地登录，请执行以下操作：

1. 打开公用区域电话。
2. 选择“ **在此设备上登录**”。
3. 按照设备上的登录说明进行操作。 登录后，手机将显示公用区域电话用户体验。

> [!NOTE]
> 如果使用取消固定呼叫应用的自定义设置策略，则拨号盘不会显示在公用区域电话上。 有关 Teams 设置策略的详细信息，请参阅[在 Microsoft Teams 中管理应用设置策略](teams-app-setup-policies.md)。

### <a name="sign-in-from-another-device"></a>从其他设备登录

还可以使用代码从另一台设备登录到公用区域电话。 以这种方式登录时，你将在另一台设备（而不是手机本身）上输入用户名和密码。

1. 在公用区域电话上，找到登录屏幕上显示的代码。
2. 在另一台设备上，转到 [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin)。
3. 输入代码并按照说明完成登录。

### <a name="sign-in-using-the-teams-admin-center"></a>使用 Teams 管理中心登录

作为管理员，你可以从 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)远程预配和登录公用区域电话。 在同时部署大量电话时，此方法是最有效的登录方法。 有关详细信息 [，请参阅 Teams Android 设备的远程预配和登录](devices/remote-provision-remote-login.md) 。

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>步骤 6 - 在公用区域电话上设置高级呼叫 (可选) 

默认情况下，基本通话体验将位于公用区域电话的主屏幕上，但你可以打开高级通话体验。

以下高级呼叫功能适用于具有 Teams 共享设备许可证的受支持 **Teams** 电话设备型号和最新 Teams 更新 (最低版本：1449/1.0.94.2022061702) ：

- [调用寄存并检索](call-park-and-retrieve.md)。
- [通过计划 2 Exchange Online基于云的语音邮件](set-up-phone-system-voicemail.md)。
  - 若要禁用基于云的语音邮件，请参阅 [使用 PowerShell 的语音邮件用户设置](/powershell/module/skype/set-csonlinevoicemailusersettings)。
- [呼叫队列](create-a-phone-system-call-queue.md)。
- [自动助理](create-a-phone-system-auto-attendant.md)。
- [群组呼叫接听](call-sharing-and-group-call-pickup.md)。
- [转发规则](teams-calling-policy.md)。

若要在支持的 Teams 电话设备型号上使用这些高级呼叫功能，可以在 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)或登录到 Teams 共享设备帐户的 Teams 电话设备上打开 **“高级呼叫**”开关。

启用高级调用功能需要购买可以支持所有所需功能的硬件模型。

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>在 Teams 管理中心中打开“高级呼叫”

1. 使用 Microsoft 365 管理员帐户登录到 [Teams 管理中心](https://admin.teams.microsoft.com/dashboard)。
1. 在左侧菜单中，导航到 **Teams 设备** > **电话** >并选择“ **配置文件** ”选项卡。
1. 从列表中，选择分配给公用区域电话的配置文件。
1. 在 **“呼叫设置”** 部分下，找到 **“高级呼叫** ”切换。
1. 打开开关。
1. 在页面底部，选择“ **保存** ”按钮。

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>从 Teams 电话设备启用高级呼叫

1. 登录到 Teams 电话设备后，导航到 **“设置** > **”“设备设置** > **管理员仅** > **通话**”。
1. 找到 **“高级呼叫** ”开关并将其打开。

## <a name="next-steps"></a>后续步骤

现在，你已为组织设置并登录公用区域电话，可以在 Teams 管理中心对其进行管理。 有关详细信息，请参阅 [Microsoft Teams：管理设备](devices/device-management.md)。

## <a name="related-articles"></a>相关文章

- [远程更新Microsoft Teams 设备](devices/remote-update.md)。
- [管理Microsoft Teams 设备标记](devices/manage-device-tags.md)。
- [Microsoft Teams 设备运行状况监视](alerts/device-health-status.md)。
