---
title: 通过 Microsoft 团队聊天室和 Surface Hub 设置协调的会议
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 配置团队室设备和 Surface Hub，以便在一个设备或其他设备加入会议时加入会议。
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803934"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>通过 Microsoft 团队聊天室和 Surface Hub 设置协调的会议

如果您在会议室中有一个或多个 Microsoft 团队聊天室设备或 Surface Hub，则可以设置协调的会议。 使用协调的会议，你可以设置团队房间设备和 Surface Hub，以便在一个设备上加入会议时，会议室中的其他设备也会加入同一会议。 你可以配置你的相机、扬声器和麦克风，以便允许参与者获得最佳体验的人在其他人禁用时启用。 这样就避免了令人可怕的回音和反馈噪音参与者在向会议添加多个设备时可能会遇到的情况。

若要设置协调的会议，你需要确保你的团队聊天室设备和 Surface Hub 已正确配置为参与会议。 最重要的是，每个设备都需要有自己的 Exchange 会议室邮箱。 有关如何设置它们的信息，请参阅以下文章：

- [部署 Microsoft Teams 会议室](../rooms/rooms-deploy.md)
- [创建 Surface Hub 2 设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

在您确认团队聊天室设备和 Surface Hub 可以自动接受会议并成功加入会议后，您可以设置协调的会议。

应为每个会议室单独完成以下步骤。 一个会议室中的设备不应设置为与其他会议室中的设备进行协调的会议。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步骤1：规划您的协调会议体验

在进行任何配置更改之前，你需要确定哪些设备将在每个会议室中执行哪些操作。 也就是说，对于给定的会议室，你需要确定哪些设备将具有 "活动麦克风"、"照相机" 和 "白板"。 配置设备的方式取决于你的特定环境，但以下是一些一般建议：

- **麦克风** 团队聊天室设备
- **相机** 默认情况下，团队聊天室设备 (默认情况下) 和 Surface Hub (关闭，但允许参与者启用) 
- **白板** Surface Hub

> [!IMPORTANT]
> 请确保仅在一台设备上启用麦克风。 如果在多台设备上启用它，将体验音频回声和反馈。

## <a name="step-2-get-your-devices-upns"></a>步骤2：获取你的设备的 Upn

在会议室中设置协调的会议体验时，你需要将团队聊天室设备和 Surface Hub 告知在该房间内要与之协调的设备。 这是通过将用户主体名称添加到其与其配置配合的设备 (UPN) 来完成的。 如果你不知道要为协调会议设置的每个设备的 Upn，则可以使用 Microsoft 365 管理中心找到它们。 

您需要分配管理员角色才能访问 Microsoft 365 管理中心。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

若要获取团队聊天室设备和 Surface Hub 的 Upn，请执行下列操作：

1. 通过访问登录到 Microsoft 365 管理中心 https://admin.microsoft.com 。
2. 转到 "**用户**  >  **活动用户**"。
3. 在 " **显示名称** " 列中查找团队聊天室设备或 Surface Hub 的名称 (如果有多个用户) ，则可以使用 " **搜索** " 框。
4. 在 " **用户名** " 列中查找 UPN， (它将以 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 的形式显示。
5. 对将参与协调会议的每个设备重复此操作。

## <a name="step-3-create-a-deployment-worksheet"></a>步骤3：创建部署工作表

在规划了您的协调会议体验并收集了设备 Upn 的列表后，最好创建一个部署工作表。 部署工作表可帮助你可视化要在所有设备上设置的配置，使你可以验证你的选择并检查错误。

在电子表格应用中，在第一列中为以下内容添加行：

| 设置                | 说明      |
|------------------------|-----------------|
| **音频默认值**      | 确定当会议启动时，麦克风将处于活动状态的设备。 只有一台设备 (通常是团队会议室设备) 可以将此字段设置为 "， `true` 而其余设备必须将此字段设置为" `false` ，以避免音频回声和反馈。          |
| **启用音频**      | 确定会议中的参与者是否可以打开或关闭麦克风。 将 **音频默认** 设置为 `false` 应将此设置设置为的设备， `false` 以便参与者无法意外打开麦克风并导致音频回声或反馈。<p>如果 " **音频默认值** " 设置为 `true` ""，将忽略此设置，并且参与者可以将麦克风设为静音或取消静音。          |
| **视频默认值**      | 确定会议启动时相机将处于活动状态的设备。 为了获得最佳体验，我们建议仅将团队聊天室设备设置为， `true` 同时将所有其他设备设置为 `false` 。          |
| **视频已启用**      | 确定会议中的参与者是否可以打开或关闭摄像头。 你可以将此项设置为 `true` 在事件参与者中的任何其他设备上，希望共享不同的视频透视 (例如，如果参与者使用 Surface Hub 白板) 。 如果不希望参与者在设备上打开或关闭摄像头，请将此设置为 `false` 。<p> 如果 " **视频默认值** " 设置为 `true` ""，则会忽略此设置，并且参与者可以打开或关闭摄像头。         |
| **白板默认设置** | 确定团队间设备是否将显示由某个会议参与者共享的白板。 我们建议你将其设置为 `false` 如果你有 Surface Hub，并且你没有 Surface Hub `true` 。 此设置对 Surface Hub 没有影响。 Surface Hub 将始终显示由会议参与者共享的白板。         |
| **白板已启用** | 确定会议中的参与者是否可以打开或关闭白板。 如果不希望参与者在设备上打开或关闭白板，请将此设置为 `false` 。 <p>如果 " **白板默认值** " 设置为 `true` ""，则忽略此设置，参与者可以打开或关闭白板。
| **受信任帐户**   | 这是一个逗号分隔的 Upn 列表，用于表示设备应接受会议加入请求的每个团队房间设备或 Surface Hub，或应发送到哪些会议加入请求。 |

在后续列中，添加每个团队聊天室设备和 Surface Hub。 在每列中，填写与你希望的会议室的体验相对应的值。 下面是一个团队聊天室设备和一个 Surface Hub 的示例：

- 团队设备
  - 当会议启动时，音频和 **视频处于打开** 状态。 参与者 **可以** 打开或关闭音频和视频。
  - 显示共享白板功能已关闭。
- Surface Hub
  - 会议启动时，音频处于 **关闭** 状态。 参与者 **无法** 打开或关闭音频。
  - 会议启动时，视频处于 **关闭** 状态。 参与者 **可以** 打开或关闭视频。

| 设置                | 团队聊天室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音频默认值**      | `true`          | `false`          |
| **启用音频**      | `true`          | `false`          |
| **视频默认值**      | `true`          | `false`          |
| **视频已启用**      | `true`          | `true`           |
| **白板默认设置** | `false`         | `false`          |
| **受信任帐户**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步骤4：配置团队聊天室设备

你可以使用设备的触摸屏在团队聊天室设备上设置协调的会议，或者，如果需要设置多个设备并希望从中心位置执行此操作，则可以使用 XML 配置文件。

使用您在上一步中创建的工作表来帮助您设置设备。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用团队聊天室设备的触摸屏幕

若要在设备上设置协调的会议，请执行下列操作：

1. 选择 **.。。更多**  >  **设置**。
2. 输入管理员密码，然后选择 **"是"**。
3. 选择 " **协调的会议**"。
4. 在 " **选项**" 下，将 " **协调会议** " 设置为 _"开"_。
5. 如果工作表中的 **音频默认值** 为 `true` ，请将 **此设备的麦克风** 设置为 "打开"，否则将其 _关闭_。
6. 如果工作表中**已启用音频** `true` ，请选择 "**打开此设备的麦克风**" 下的 "在**加入会议时允许用户启用**"。 如果 **"打开此设备的麦克风** " 设置为 "打开"，则不能关闭此选项。
7. 如果工作表中的 **视频默认值** 为 `true` "启用"，则将 **此设备的摄像头** 设置为 "开"，否则将其 _关闭_。
8. 如果工作表中**启用**了视频 `true` ，请选择 "在**此设备的相机上**启用**加入会议时允许用户启用**"。 如果将 **此设备的相机** 设置为 _"_ 打开"，则无法关闭此选项。
9. 如果工作表中的 **白板默认值** 为 `true` "打开"，请将 **此设备** 上的 whiteboarding 设置为 _"_ 打开"，否则将其 _关闭_。
10. 在 " **受信任的设备帐户**" 下，在工作表中键入 " **受信任帐户** " 中列出的所有 UPN 用逗号分隔多个 Upn。
11. 选择 " **保存并退出**"。

选择 " **保存并退出**" 后，设备将重新启动，并准备好参与协调的会议。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用团队聊天室 XML 配置文件

可以使用团队聊天室设备的 `SkypeSettings.xml` XML 配置文件设置协调的会议。 `SkypeSettings.xml`文件不是静态文件。 当团队房间设备启动时，它将签入 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 一个名为的文件 `SkypeSettings.xml` 。 如果文件存在，设备将读取并应用文件中指定的配置。 完成应用配置后，文件将被删除。 有关文件的详细信息 `SkypeSettings.xml` ，请参阅 [使用 XML 配置文件管理控制台设置](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

以下是配置文件中协调的会议设置的语法：

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

若要在设备上设置协调的会议，请执行下列操作：

1. 在文本文件编辑器（如 Visual Studio 代码或记事本）中，将上面的 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为 `true` `false` 电子表格中的相应值或值。 例如，如果 **音频默认值** 为 `true` ，则设置 `<Audio default="true">` 。

3. 请确保更改 `TrustedAccounts` 为 upn 列表。

4. 将文件保存为名称 `SkypeSettings.xml` 。

5. 将文件放在团队聊天室设备的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 文件夹中。 你可以通过以下几种方式执行此操作：

    - **将文件复制到团队聊天室设备** 在将文件复制到你的设备之前，你需要启用文件共享并创建网络共享。 执行此操作后，您可以连接到网络共享并将文件复制到设备。 有关详细信息，请参阅 [Microsoft 团队会议室维护和操作](../rooms/rooms-operations.md)。
    - **使用组策略** 创建组策略以将文件复制到设备。 有关详细信息，请参阅 [组策略概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **在团队聊天室设备上下载文件** 你可以使用管理员模式登录到设备，然后从网络共享或 USB 驱动器将文件复制到设备。 有关详细信息，请参阅 [切换到 "管理员模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)"。
    
6. 重启设备。 你可以通过以下几种方式执行此操作：

    - **远程 PowerShell** 你可以使用远程 PowerShell 在设备上运行 Shutdown 命令。 有关详细信息，请参阅 [使用 PowerShell 进行远程管理](../rooms/rooms-operations.md)。
    - **运行重启-计算机** 你可以 `Restart-Computer` 在本地计算机上运行 cmdlet，并指定要重新启动的设备的计算机名。 有关详细信息，请参阅 [重新启动计算机](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步骤5：配置 Surface Hub

你可以使用 Windows 配置设计器创建预配包，你可以使用它将协调会议设置应用于 Surface Hub。 你将在上面创建的 XML 文件粘贴到 Windows 配置设计器以创建预配包。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>创建 Surface Hub 的协调会议 XML 配置文件

Windows 配置设计器和 Microsoft Intune 都用于将协调的会议配置应用于 Surface Hub。 配置是使用 XML 定义的。 在继续操作之前，你需要创建将应用的 XML。

下面是 "协调的会议" XML 配置文件的语法。

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

执行以下操作以准备适用于 Windows 配置设计器或 Microsoft Intune 的 XML：

1. 在文本文件编辑器（如 Visual Studio 代码或记事本）中，将上面的 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为 `true` `false` 电子表格中的相应值或值。 例如，如果 **音频默认值** 为 `true` ，则设置 `<Audio default="true">` 。

3. 请确保更改 `TrustedAccounts` 为 upn 列表。

4. Windows 配置设计器要求 XML 位于单个行上。 删除每行之间的所有换行符，以使 XML 如下所示：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 将文件保存在您的计算机上。

创建 XML 配置文件后，请使用 " [管理 Microsoft 团队中的 Microsoft 团队设置](surface-hub-manage-config.md) " 中的步骤将其应用于 surface hub。
