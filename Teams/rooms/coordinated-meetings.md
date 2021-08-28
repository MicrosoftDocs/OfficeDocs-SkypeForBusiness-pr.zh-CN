---
title: 使用会议设置协调Microsoft Teams 会议室Surface Hub
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
ms.localizationpriority: medium
description: 配置Teams 会议室设备，Surface Hub一台设备加入会议时加入会议。
ms.openlocfilehash: 21b8dc21b65748754f8a7903bc20cf55bd7c80c4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592206"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>使用会议设置协调Microsoft Teams 会议室Surface Hub

如果您在会议室中拥有一Microsoft Teams 会议室或 Surface Hub，您可以设置协调会议。 协调会议允许您设置 Teams 会议室 设备和 Surface Hub，以便当您在一台设备上加入会议时，会议室的其他设备也会加入同一会议。 您可以配置摄像机、扬声器和麦克风，以便启用为参与者提供最佳体验的摄像机，同时禁用其他设备。 这可以避免参与者在将多个设备添加到会议时可能体验到的干扰回声和反馈噪音。

若要设置协调会议，你需要确保Teams 会议室设备和 Surface Hub 已正确配置为参加会议。 最重要的是，每台设备需要有自己的会议室Exchange邮箱。 若要了解如何设置它们，请参阅以下文章：

- [部署 Microsoft Teams 会议室](../rooms/rooms-deploy.md)
- [创建 Surface Hub 2S 设备帐户](/surface-hub/surface-hub-2s-account)

确认你的设备和 Surface Hub Teams 会议室自动接受会议并成功加入会议后，可以设置协调会议。

应分别针对每个会议室完成以下步骤。 不应将一个会议室中的设备设置为与其他会议室中的设备协调会议。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步骤 1：规划协调会议体验

在做出任何配置更改之前，您需要确定哪些设备将在每个会议室中执行哪些操作。 也就是说，对于给定的会议室，你需要确定哪个设备将具有活动的麦克风、摄像头和白板。 配置设备的方式取决于特定的环境，但以下是一些一般建议：一开始建议：

- **麦克风** Teams 会议室设备
- **默认情况下** Teams 会议室打开 (相机设备) Surface Hub (关闭，但参与者或参与者) 
- **白板** Surface Hub

> [!IMPORTANT]
> 请确保仅在一台设备上启用麦克风。 如果你在多台设备上启用它，你将体验到音频回声和反馈。

## <a name="step-2-get-your-devices-upns"></a>步骤 2：获取设备的 UPN

当您在会议室中设置协调会议体验时，您需要告知Teams 会议室会议室中的设备和 Surface Hub 要协调哪些设备。 为此，将用户主体名称 (UPN) 应协调到其配置的设备中。 如果不知道要为协调会议设置的每个设备的 UPN，可以使用Microsoft 365 管理中心。 

需要分配管理员角色才能访问Microsoft 365 管理中心。 有关详细信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

若要获取 Teams 会议室 和 Surface Hub 的 UPN，请执行下列操作：

1. 访问 登录到 https://admin.microsoft.com Microsoft 365 管理中心。
2. 转到"**用户**  >  **""活动用户"。**
3. 在"显示名称"Teams 会议室或Surface Hub"名称"列中 (如果有许多用户，可以使用"搜索"框) 。 
4. 在"用户名" **列中找到** UPN (其外观类似 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。
5. 对将参与协调会议的每个设备重复此操作。

## <a name="step-3-create-a-deployment-worksheet"></a>步骤 3：创建部署工作表

规划协调会议体验并收集设备的 UPN 列表后，建议创建部署工作表。 部署工作表有助于可视化要设置的所有设备的配置，从而验证选择并检查错误。

在电子表格应用中，添加第一列中以下内容的行：

| 设置                | 说明      |
|------------------------|-----------------|
| **音频默认值**      | 确定在会议开始时麦克风将处于活动状态的设备。 只有一 (设备Teams 会议室设备) 可以将此字段设置为 ，而其余设备必须将此字段设置为 以避免音频回声和 `true` `false` 反馈。          |
| **已启用音频**      | 确定会议参与者是否可以打开或关闭麦克风。 将 **"音频默认值** "设置为 的设备应将此设置设置为 ，以便参与者不会意外打开麦克风并 `false` 引发音频 `false` 回声或反馈。<p>如果 **"音频** 默认值"设置为 `true` ，则忽略此设置，参与者可以将麦克风设为静音或取消静音。          |
| **视频默认值**      | 确定在会议开始时相机将在哪个设备上处于活动状态。 为获得最佳体验，建议仅将Teams 会议室设置为 ，而所有其他 `true` 设备都设置为 `false` 。          |
| **视频已启用**      | 确定会议参与者是否可以打开或关闭摄像机。 您可以在事件参与者想要共享不同视频透视图的其他任何设备上 (，例如，如果参与者正在使用 Surface Hub `true` 白板) 。 如果不希望参与者在设备上打开或关闭摄像机，请将其设置为 `false` 。<p> 如果 **"视频** 默认值"设置为 `true` ，则忽略此设置，参与者可以打开或关闭摄像机。         |
| **白板默认值** | 确定Teams 会议室设备是否显示由其中一个会议参与者共享的白板。 如果你拥有一个Surface Hub并且没有，建议将此选项 `false` `true` 设置为 。 此设置对 Surface Hub 没有影响。 Surface Hub 将始终显示会议参与者共享的白板。         |
| **已启用 Whiteboard** | 确定会议参与者是否可以打开或关闭白板。 如果不希望参与者在设备上打开或关闭白板，请将其设置为 `false` 。 <p>如果 **Whiteboard 默认值** 设置为 `true` ，则忽略此设置，参与者可以打开或关闭白板。
| **受信任的帐户**   | 这是每个 Teams 会议室设备或设备的 UPN 的逗号分隔列表Surface Hub设备应接受会议加入请求，或者应发送到哪些会议加入请求。 |

在后续列中，添加每个Teams 会议室设备和 Surface Hub。 在每个列中，填写与想要用于会议室的体验对应的值。 下面是一个示例，其中一个设备Teams 会议室一个Surface Hub：

- Teams设备
  - 音频和视频在会议 **开始时** 打开。 参与者 **可以** 打开或关闭音频和视频。
  - 显示共享白板已关闭。
- Surface Hub
  - 会议 **开始时，音频** 已关闭。 参与者 **无法打开** 或关闭音频。
  - 会议开始时 **，** 视频已关闭。 参与者 **可以** 打开或关闭视频。

| 设置                | Teams会议室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音频默认值**      | `true`          | `false`          |
| **已启用音频**      | `true`          | `false`          |
| **视频默认值**      | `true`          | `false`          |
| **视频已启用**      | `true`          | `true`           |
| **白板默认值** | `false`         | `false`          |
| **受信任的帐户**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步骤 4：配置Teams 会议室设备

可以使用设备的触摸屏在 Teams 会议室 设备上设置协调会议，或者如果需要设置许多设备，并且想要从一个中心位置设置协调会议，可以使用 XML 配置文件。

使用在上一步骤中创建的工作表来帮助设置设备。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用Teams 会议室设备的触摸屏

若要在设备上设置协调会议，请执行下列操作：

1. 选择 **...。更多**  >  **设置。**
2. 输入管理员密码，然后选择"**是"。**
3. 选择 **"协调会议"。**
4. 在 **"选项"** 下，将 **"协调会议"** 设置为 _on。_
5. 如果 **工作表中的**"音频"默认为 ，将"打开此设备的麦克风"设置为"打开"， `true` 否则将其 _关闭_。 
6. 如果 **工作表中已启用**"音频"，请在"打开此设备的麦克风"下选择"允许用户在加入会议时 `true` **启用"。**  如果"打开此设备的麦克风"设置为"打开 **"，则不能** 关闭此选项。
7. 如果 **工作表中的"** 视频"默认为 `true` ，将 **"打开此设备的** 相机"设置为"打开"，否则请将其 _关闭_。
8. 如果 **工作表中** 已启用"视频"，请在"打开此设备的相机"下选择"允许用户在加入会议 `true` **时启用"。**  如果"打开此设备的相机"设置为"开"，则不能 _关闭此选项_。
9. 如果 **工作表中的 Whiteboard** 默认值为 `true` ，将 **"在此设备上打开白板** "设置为 _"打开_"，否则将其 _关闭_。
10. 在 **"受信任的设备帐户"下**，键入工作表中" **受信任的帐户"中列出的** 每个 UPN。 使用逗号分隔多个 UPN。
11. 选择 **"保存并退出"。**

选择" **保存并退出"** 后，设备将重新启动，并准备好参与协调会议。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用 Teams 会议室 XML 配置文件

可以使用设备的 XML 配置文件Teams 会议室协调 `SkypeSettings.xml` 会议。 `SkypeSettings.xml`该文件不是静态文件。 当Teams 会议室启动时，它将检查 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名为 的文件 `SkypeSettings.xml` 。 如果文件存在，设备将读取并应用文件中指定的配置。 应用完配置后，将删除该文件。 有关文件详细信息 `SkypeSettings.xml` ，请参阅 [使用 XML 配置文件管理控制台设置](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

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

若要在设备上设置协调会议，请执行下列操作：

1. 在文本文件编辑器中（例如Visual Studio Code或记事本，将上述 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为电子表格 `true` 中的对应 `false` 或值。 例如，如果 **"音频默认值"为** `true` ，则设置 `<Audio default="true">` 。

3. 请务必更改为 `TrustedAccounts` UPN 列表。

4. 保存名称为 的文件 `SkypeSettings.xml` 。

5. 将文件Teams 会议室设备的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 文件夹中。 可通过多种方式实现此要求：

    - **将文件复制到 Teams 会议室 设备** 需要先启用文件共享并创建网络共享，然后才能将文件复制到设备。 完成操作后，可以连接到网络共享，将文件复制到设备。 有关详细信息，请参阅Microsoft Teams 会议室[和操作](../rooms/rooms-operations.md)。
    - **使用组策略** 创建组策略，将文件复制到设备。 有关详细信息，请参阅组 [策略概述](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **在设备上下载Teams 会议室文件** 可以使用管理模式登录到设备，然后将文件从网络共享或 U 盘复制到设备。 有关详细信息，请参阅 [切换到管理模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. 重启设备。 可通过多种方式实现此要求：

    - **远程 PowerShell** 可以使用远程 PowerShell 在设备上运行"关闭"命令。 有关详细信息，请参阅使用 [PowerShell 进行远程管理](../rooms/rooms-operations.md)。
    - **运行 Restart-Computer** 可以在本地 `Restart-Computer` 计算机上运行 cmdlet，并指定要重启的设备的计算机名称。 有关详细信息，请参阅 [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步骤 5：配置Surface Hub

可以使用Windows设计器创建可用于将协调会议设置应用到 Surface Hub 的预配包。 将上面创建的 XML 文件粘贴到Windows设计器中以创建预配包。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>为会议创建协调会议 XML 配置文件Surface Hub

配置Windows设计器Microsoft Intune用于将协调会议配置应用到 Surface Hub。 配置是使用 XML 定义的。 在进一步操作之前，需要创建要应用的 XML。

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

执行以下操作，为配置设计器或Windows准备 XML Microsoft Intune：

1. 在文本文件编辑器中（例如Visual Studio Code或记事本，将上述 XML 粘贴到新文件中。

2. 将每个 XML 元素设置为电子表格 `true` 中的对应 `false` 或值。 例如，如果 **"音频默认值"为** `true` ，则设置 `<Audio default="true">` 。

3. 请务必更改为 `TrustedAccounts` UPN 列表。

4. Windows配置设计器要求 XML 位于单行中。 删除每行之间的所有换行符，使 XML 如下所示：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 在计算机上保存文件。

创建 XML 配置文件后，请使用在 Microsoft Teams 上管理[](surface-hub-manage-config.md)Surface Hub 设置中的步骤，以将该文件应用到 Surface Hub。