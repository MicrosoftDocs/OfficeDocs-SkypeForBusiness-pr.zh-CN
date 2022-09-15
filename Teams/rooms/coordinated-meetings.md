---
title: 与 Microsoft Teams 会议室 和 Surface Hub 建立协调会议
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 配置Teams 会议室设备和 Surface Hub 以在一台设备或其他设备加入会议时加入会议。
ms.openlocfilehash: 759574015f2138476e0b03ef6fa85b8b105d81ef
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706979"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>使用 Microsoft Teams 会议室 和 Surface Hub 设置协调会议

如果会议室中有一个或多个Microsoft Teams 会议室设备或 Surface Hub，则可以设置协调会议。 协调会议允许你设置Teams 会议室设备和 Surface Hub，以便在一台设备上加入会议时，会议室中的其他设备也会加入同一个会议。 可以配置相机、扬声器和麦克风，以便在禁用其他设备时启用为参与者提供最佳体验的摄像机、扬声器和麦克风。 这样可以避免在将多个设备添加到会议时，参与者可能会遇到可怕的回声和反馈噪音。

若要设置协调会议，需要确保Teams 会议室设备和 Surface Hub 已正确配置为参与会议。 最重要的是，每个设备都需要有自己的 Exchange 会议室邮箱。 有关如何设置它们的信息，请参阅以下文章：

- [部署 Microsoft Teams 会议室](../rooms/rooms-deploy.md)
- [创建 Surface Hub 2S 设备帐户](/surface-hub/surface-hub-2s-account)

确认Teams 会议室设备和 Surface Hub 可以自动接受会议并成功加入会议后，可以设置协调会议。

应单独为每个会议室完成以下步骤。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步骤 1：规划协调会议体验

在进行任何配置更改之前，需要确定哪些设备将在每个会议室中执行哪些操作。 也就是说，对于给定的会议室，你需要决定哪个设备将具有活动麦克风、照相机和白板。 如何配置设备取决于特定环境，但下面是一些一般性建议，可从以下内容开始：

- **麦克风** Teams 会议室设备
- **默** 认情况下，相机Teams 会议室设备 () 和 Surface Hub 默认 (关闭，但参与者允许其打开) 
- **白板** Surface Hub

> [!IMPORTANT]
> 确保仅在一台设备上启用麦克风。 如果在多个设备上启用它，你将体验音频回显和反馈。

## <a name="step-2-get-your-devices-upns"></a>步骤 2：获取设备的 UPN

在会议室中设置协调会议体验时，需要告知会议室中的Teams 会议室设备和 Surface Hub 哪些设备要与之协调。 为此，请将用户主体名称添加 (UPN) 其应与其配置协调的设备。 如果不知道要为协调会议设置的每个设备的 UPN，可以使用Microsoft 365 管理中心找到它们。 

需要为你分配一个管理员角色才能访问Microsoft 365 管理中心。 有关详细信息，请参阅 [“关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)”。

若要获取Teams 会议室设备和 Surface Hub 的 UPN，请执行以下操作：

1. 通过访问https://admin.microsoft.com登录到Microsoft 365 管理中心。
2. 转到 **用户** > **活动用户**。
3. 在“**显示名称**”列中查找Teams 会议室设备或 Surface Hub 的名称 (如果) 用户很多，则可以使用 **搜索** 框。
4. 在 **“用户名** ”列中查找 UPN (它的外观类似于 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。
5. 对于将参与协调会议的每个设备重复此操作。

## <a name="step-3-create-a-deployment-worksheet"></a>步骤 3：创建部署工作表

规划协调会议体验并收集设备的 UPN 列表后，最好创建部署工作表。 部署工作表将帮助你可视化要在所有设备上设置的配置，从而验证你的选择并检查错误。

在电子表格应用中，在第一列中为以下内容添加行：

| 设置                | 说明      |
|------------------------|-----------------|
| **音频默认值**      | 确定会议开始时麦克风将处于活动状态的设备。 只有一个设备 (通常Teams 会议室设备) 可以设置`true`此字段，而其余设备必须设置此字段以避免`false`音频回显和反馈。          |
| **已启用音频**      | 确定会议中的参与者是否可以打开或关闭麦克风。 **将音频默认** 设置为`false`的设备应设置`false`此设置，以便参与者不能意外打开麦克风并引起音频回显或反馈。<p>如果 **音频默认** 设置为 `true`“音频”，则忽略此设置，参与者可以静音或取消静音麦克风。          |
| **视频默认值**      | 确定在会议开始时相机将处于活动状态的设备。 为了获得最佳体验，我们建议仅将Teams 会议室设备设置为`true``false`所有其他设备。          |
| **已启用视频**      | 确定会议中的参与者是否可以打开或关闭相机。 可以在事件参与者希望共享不同视频透视的任何其他设备上将其设置 `true` 为 (例如参与者使用 Surface Hub 白板) 。 如果不希望参与者在设备上打开或关闭相机，请将其设置为 `false`。<p> 如果 **视频默认** 设置为 `true`“视频”，则忽略此设置，参与者可以打开或关闭相机。         |
| **白板默认值** | 确定Teams 会议室设备是否会显示会议参与者之一共享的白板。 如果有 Surface Hub，`true`并且没有 Surface Hub，建议将其设置`false`为。 此设置对 Surface Hub 没有影响。 Surface Hub 将始终显示会议参与者共享的白板。         |
| **已启用白板** | 确定会议中的参与者是否可以打开或关闭白板。 如果不希望参与者在设备上打开或关闭白板，请将其设置为 `false`。 <p>如果 **将 Whiteboard 默认** 设置为 `true`，则忽略此设置，参与者可以打开或关闭白板。
| **受信任的帐户**   | 这是设备应接受会议加入请求的每个Teams 会议室设备或 Surface Hub 的逗号分隔的 UPN 列表，或者应向其发送会议加入请求。 |

在后续列中，添加每个Teams 会议室设备和 Surface Hub。 在每个列中，填写与会议室所需的体验相对应的值。 下面是一个包含一个Teams 会议室设备和一个 Surface Hub 的示例：

- Teams 设备
  - 会议开始时 **打开** 音频和视频。 参与者 **可以** 打开或关闭音频和视频。
  - 显示共享白板已关闭。
- Surface Hub
  - 会议开始时 **，** 音频会关闭。 参与者 **无法** 打开或关闭音频。
  - 当会议开始时，视频会 **关闭** 。 参与者 **可以** 打开或关闭视频。

| 设置                | Teams 会议室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音频默认值**      | `true`          | `false`          |
| **已启用音频**      | `true`          | `false`          |
| **视频默认值**      | `true`          | `false`          |
| **已启用视频**      | `true`          | `true`           |
| **白板默认值** | `false`         | `false`          |
| **受信任的帐户**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步骤 4：配置Teams 会议室设备

可以使用设备的触摸屏在Teams 会议室设备上设置协调会议，或者，如果需要设置许多设备，并希望从中心位置执行此操作，则可以使用 XML 配置文件。

使用在上一步中创建的工作表来帮助你设置设备。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用Teams 会议室设备的触摸屏

若要在设备上设置协调会议，请执行以下操作：

1. 选择 **...更多** > **设置**。
2. 输入管理员密码，然后选择 **“是**”。
3. 选择 **协调会议**。
4. 在 **“选项**”下，将 **协调会议** 设置为 _“打开_”。
5. 如果工作表`true`中的 **音频默认** 值为“**打开此设备的麦克风**”，请将其 _关闭_。
6. 如果工作表`true`中 **启用了音频**，请选择“允许用户 **在打开此设备的麦克风”** 下 **加入会议时启用**。 如果打开 **此设备的麦克风** ，则无法关闭此选项。
7. 如果工作表中的视频 **默认** 值为 `true`“ **打开此设备的相机** ”，请 _将其关闭_。
8. 如果工作表`true`中 **启用了视频**，请选择“在 **打开此设备的相机下****加入会议时允许用户启用**”。 如果打开 **此设备的相机**，则无法关闭此 _选项。_
9. 如果工作表中的 **Whiteboard 默认值** ， `true`请将 **此设备上的“打开白板** ”设置为 _打开_，否则 _将其关闭_。
10. 在 **“受信任的设备帐户**”下，键入工作表中 **受信任帐户** 中列出的每个 UPN。 使用逗号分隔多个 UPN。
11. 在受信任的设备上，关闭邻近和远程房间。 
12. 选择 **“保存”并退出**。

选择 **“保存”并退出** 后，设备将重新启动，并准备参加协调会议。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用Teams 会议室 XML 配置文件

可以使用Teams 会议室设备的 `SkypeSettings.xml` XML 配置文件设置协调会议。 该 `SkypeSettings.xml` 文件不是静态文件。 当Teams 会议室设备启动时，它会签入`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`名为文件`SkypeSettings.xml`的文件。 如果文件存在，设备将读取并应用文件中指定的配置。 应用完配置后，该文件将被删除。 有关该文件的 `SkypeSettings.xml` 详细信息，请参阅 [使用 XML 配置文件管理控制台设置](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

下面是配置文件中协调会议设置的语法：

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

若要在设备上设置协调会议，请执行以下操作：

1. 在文本文件编辑器（如Visual Studio Code或记事本）中，将上述 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为电子表格中的对应 `true` 或 `false` 值。 例如，如果 **音频默认** 值为 `true`“设置 `<Audio default="true">`”。

3. 请务必更改 `TrustedAccounts` 为 UPN 列表。

4. 使用名称 `SkypeSettings.xml`保存文件。

5. 将文件放在Teams 会议室设备`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`的文件夹中。 可以通过以下几种方式执行此操作：

    - 将 **文件复制到Teams 会议室设备** 需要启用文件共享并创建网络共享，然后才能将文件复制到设备。 执行此操作后，可以连接到网络共享并将文件复制到设备。 有关详细信息，请参阅[Microsoft Teams 会议室维护和操作](../rooms/rooms-operations.md)。
    - **使用نهج المجموعة** 创建组策略将文件复制到设备。 有关详细信息，请[参阅نهج المجموعة概述](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **在Teams 会议室设备上下载文件**，可以使用管理员模式登录到设备，然后从网络共享或 USB 驱动器将文件复制到设备。 有关详细信息，请参阅[切换到管理员模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. 重启设备。 可以通过以下几种方式执行此操作：

    - **远程 PowerShell** 可以使用远程 PowerShell 在设备上运行 Shutdown 命令。 有关详细信息，请参阅 [使用 PowerShell 的远程管理](../rooms/rooms-operations.md)。
    - **运行 Restart-Computer** 可以在本地计算机上运行 `Restart-Computer` 该 cmdlet，并指定要重启的设备的计算机名称。 有关详细信息，请参阅 [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步骤 5：配置 Surface Hub

可以使用 Windows 配置设计器创建可用于将协调会议设置应用到 Surface Hub 的预配包。 将上面创建的 XML 文件粘贴到 Windows 配置设计器中，以创建预配包。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>为 Surface Hub 创建协调会议 XML 配置文件

Windows 配置设计器和Microsoft Intune都用于将协调会议配置应用到 Surface Hub。 配置是使用 XML 定义的。 在进一步操作之前，需要创建将要应用的 XML。

下面是协调会议 XML 配置文件的语法。

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

请执行以下操作，为 Windows 配置设计器或Microsoft Intune准备 XML：

1. 在文本文件编辑器（如Visual Studio Code或记事本）中，将上述 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为电子表格中的对应 `true` 或 `false` 值。 例如，如果 **音频默认** 值为 `true`“设置 `<Audio default="true">`”。

3. 请务必更改 `TrustedAccounts` 为 UPN 列表。

4. Windows 配置设计器要求 XML 位于单行上。 删除每行之间的所有换行符，使 XML 如下所示：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 将文件保存在计算机上。

创建 XML 配置文件后，请使用 [Surface Hub 上“管理 Microsoft Teams”设置中的](surface-hub-manage-config.md) 步骤将其应用到 Surface Hub。
