---
title: 管理 Surface Hub 上的 Microsoft 团队配置
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
description: 使用 Microsoft Intune 和 Windows 配置设计器管理 Surface Hub 上的 Microsoft 团队设置
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761428"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理 Surface Hub 上的 Microsoft 团队设置

你可以在 Microsoft Endpoint Manager 中使用 Windows 配置设计器或 Microsoft Intune 管理 Surface Hub 上的 Microsoft 团队设置。 需要了解有关 Windows 配置设计器或 Microsoft Intune 的知识才能对团队设置进行更改。 有关这些选项的详细信息，请参阅以下文章：

- [创建适用于 Windows 10 的预配包](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [什么是 Microsoft Intune 设备管理？](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

如果你只有几个 Surface Hub 设备，并且可以轻松访问它们，Windows 配置设计器是一个不错的选择。 如果你有多个 Surface Hub，或者它们位于远程位置，请在 Microsoft 终结点管理器中使用 Microsoft Intune （如果它是在你的组织中部署的）。 无论选择哪种方法，都需要创建 XML 配置文件，以便对 Surface Hub 上的团队设置进行更改。

## <a name="teams-configuration-file-syntax"></a>团队配置文件语法

Surface Hub 上的团队配置是使用 XML 文件定义的。 XML 文件包含可用于控制团队工作方式的所有设置。 Windows 配置设计器和 Microsoft Intune 都使用相同的 XML 语法。 下面是团队配置 XML 文件的示例：

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

下表介绍了配置文件中可用的所有配置设置：

| 代                  | 元素                                   | 属性 | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 无                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上团队配置的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 确定 Surface Hub 是否公布它可用于蓝牙连接。<br>接受值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 确定团队是否将自动接受基于邻近感应的会议。<br>接受值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含协调会议的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 确定团队是否配置为参与与其他设备的协调会议。<br>接受值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 这是一个逗号分隔的 Upn 列表，用于表示设备应接受会议加入请求的每个团队房间设备或 Surface Hub，或应发送到哪些会议加入请求。<br>接受值：字符串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含用于协调会议的配置音频和视频配置元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上的团队音频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定当会议启动时，麦克风将处于活动状态的设备。 只有一台设备 (通常是团队会议室设备) 可以将此字段设置为 "， `true` 而其余设备必须将此字段设置为" `false` ，以避免音频回声和反馈。<br>接受值： `true` ， `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 确定会议中的参与者是否可以打开或关闭麦克风。 将 **音频默认** 设置为 `false` 应将此设置设置为的设备， `false` 以便参与者无法意外打开麦克风并导致音频回声或反馈。<p>如果 " **音频默认值** " 设置为 `true` ""，将忽略此设置，并且参与者可以将麦克风设为静音或取消静音。<br>接受值： `true` ， `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制 Surface Hub 上团队的视频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定会议启动时相机将处于活动状态的设备。 为了获得最佳体验，我们建议仅将团队聊天室设备设置为， `true` 同时将所有其他设备设置为 `false` 。<br>接受值： `true` ， `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 确定会议中的参与者是否可以打开或关闭摄像头。 你可以将此项设置为 `true` 在事件参与者中的任何其他设备上，希望共享不同的视频透视 (例如，如果参与者使用 Surface Hub 白板) 。 如果不希望参与者在设备上打开或关闭摄像头，请将此设置为 `false` 。<p> 如果 " **视频默认值** " 设置为 `true` ""，则会忽略此设置，并且参与者可以打开或关闭摄像头。<br>接受值： `true` ， `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>将团队设置应用于 Surface Hub

在 Surface Hub 上使用 Windows 配置设计器或 microsoft Intune 在 Microsoft 终结点管理器中应用或更新团队配置设置。

### <a name="use-windows-configuration-designer"></a>使用 Windows 配置设计器

可以使用 Windows 配置设计器创建可用于将团队设置应用于 Surface Hub 的预配包。 你将在上面创建的 XML 文件粘贴到 Windows 配置设计器以创建预配包。

> [!IMPORTANT]
> 如果你已使用预配包将团队配置应用到 Surface Hub，并且想要对其进行更改，则需要首先删除现有预配包。 有关详细信息，请参阅 [删除 Windows 配置设计器创建的预配包](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

执行以下操作以在 Windows 配置设计器中创建预配包：

1. 从本地计算机上的 Windows 应用商店安装 Windows 配置设计器并将其打开
2. 选择 "**预置 Surface Hub 设备**"，然后**切换到 "高级编辑器**"
3. 在下一个屏幕上，展开 " **WindowsTeamSettings**  >  **团队**"，然后选择 "**配置**"
4. 在中间窗格中 " **配置** " 旁边的字段中，粘贴您在上面创建的单行 XML
5. 选择**导出**  >  **预配包**
6. 在 "**名称**" 中提供预配包的名称，然后选择 "**下**  >  **一步**"
7. 指定用于保存预配包的位置，然后选择 "**下一步**"
8. 选择 "**生成**" 创建预配包，然后选择 "**完成**"

最后，在创建预配包后，请执行以下操作以将预配包应用于 Surface Hub：

1. 将上面创建的预配包保存到 USB 驱动器
2. 将 USB 驱动器插入 Surface Hub
3. 在 Surface Hub 上，打开 "开始" 菜单，选择 "**所有应用**"，然后选择 "**设置**"
4. 提供管理员用户名和密码，然后选择 **"是"**
5. 转到 **Surface Hub**、 **设备管理**、 **添加或删除预配包**，然后 **添加程序包**
6. 在 " **选择程序包**" 下，选择预配包旁边的 " **添加** "，然后重新启动 Surface Hub

### <a name="use-microsoft-intune"></a>使用 Microsoft Intune

如果 Surface Hub 是使用 microsoft Intune 在 Microsoft 终结点管理中管理的，则可以使用它将团队设置应用于 Surface Hub。 你将创建一个新的配置文件，然后将上面创建的 XML 文件粘贴到该配置文件中。

> [!IMPORTANT]
> 你的 Surface Hub 需要位于设备组中，以便 Microsoft Intune 能够识别要向其应用配置文件的设备。 有关如何创建设备组的信息，请参阅 [添加组以组织用户和设备](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

执行以下操作以创建将团队设置应用于 Surface Hub 的配置文件：

1. 通过访问登录到 Microsoft 终结点管理器 https://endpoint.microsoft.com/
2. 导航到 "**设备**  >  **配置文件**"，然后选择 "**创建配置文件**"
3. 在 "**平台**" 下，选择 " **Windows 10 和更高版本**"
4. 在 " **配置文件**" 下，选择 " **自定义**"，然后单击 " **创建**
5. 在 "**基本**" 选项卡上的 "**名称**" 中，为配置文件提供描述性名称，然后选择 "**下一步**"
6. 在 "**配置设置**" 选项卡上，选择 "**添加**"
7. 在 " **添加行** " 窗格中，执行下列操作：
    1. 提供一个描述性名称，并根据需要为你添加的团队设置说明
    2. 在 " **OMA URI**" 中，输入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 " **数据类型**" 中，选择 " **字符串 (XML 文件") **
    4. 打开文件浏览器，选择上面创建的 XML 文件，然后 **打开**
8. 依次选择 "**添加**" 和 "**下一步**"
9. 在 "**作业**" 选项卡上，确保将 "**分配**" 设置为 "**选定组**"
10. 在 "**所选组**" 下，选择 "**选择要包含的组**"，然后选择包含 Surface hub 的组，然后选择 "**选择**"
11. 选择 **下一**步， **下一步**
12. 在 "**审阅 + 创建**" 中，选择 "**创建**"

## <a name="remove-teams-settings-from-a-surface-hub"></a>从 Surface Hub 中删除团队设置

使用 Microsoft 终结点管理器中的 Windows 配置设计器或 Microsoft Intune 删除 Surface Hub 上的团队配置设置。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>删除 Windows 配置设计器创建的预配包

如果你使用 Windows 配置设计器创建的预配包将团队设置应用到 Surface Hub，请使用以下步骤删除程序包及其设置：

1. 在 Surface Hub 上，打开 "开始" 菜单，选择 "**所有应用**"，然后选择 "**设置**"
2. 提供管理员用户名和密码，然后选择 **"是"**
3. 转到 **Surface Hub**， **设备管理** ，然后 **添加或删除预配包**
4. 在要删除的预配包旁边，选择 "**删除**"
5. 转到 **Surface Hub** ，然后 **& 功能的应用**
6. 查找 "**适用于 Surface Hub 的 Microsoft 团队**"，然后选择 "**高级选项**"
7. 选择 "**重置**"，然后再次**重置**
8. 重启 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>删除 Microsoft Intune 应用的设置

如果你在 Microsoft 终结点管理中使用 Microsoft Intune 将团队设置应用到 Surface Hub，请使用以下步骤删除配置文件及其设置：

1. 通过访问登录到 Microsoft 终结点管理器 https://endpoint.microsoft.com/
2. 导航到**设备**  >  **配置文件**
3. 选择包含要删除的协调的会议设置的配置文件
4. 在 "配置文件详细信息" 页面上，选择 " **删除** "，然后选择 **"确定"**

删除包含 Surface Hub 的协调会议设置的配置文件后，请使用以下步骤重置 Surface Hub 上的团队应用：

1. 在 Surface Hub 上，打开 "开始" 菜单，选择 "**所有应用**"，然后选择 "**设置**"
2. 提供管理员用户名和密码，然后选择 **"是"**
3. 转到 **Surface Hub** ，然后 **& 功能的应用**
4. 查找 "**适用于 Surface Hub 的 Microsoft 团队**"，然后选择 "**高级选项**"
5. 选择 "**重置**"，然后再次**重置**
6. 重启 Surface Hub