---
title: 管理 Surface Hub 上的 Microsoft Teams 配置
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
description: 使用 Microsoft Intune 和 Windows 配置设计器管理 Surface Hub 上的 Microsoft Teams 设置
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117380"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理 Surface Hub 上的 Microsoft Teams 设置

可以使用 Windows 配置设计器或 Microsoft 终结点管理器中的 Microsoft Intune 在 Surface Hub 上管理 Microsoft Teams 设置。 若要更改 Teams 设置，需要了解 Windows 配置设计器或 Microsoft Intune。 有关这些选项的详细信息，请参阅以下文章：

- [为 Windows 10 创建预配包](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什么是 Microsoft Intune 设备管理？](/mem/intune/remote-actions/device-management)

如果你只有几个 Surface Hub 设备并且你可以轻松访问它们，则 Windows 配置设计器是一个不错的选择。 如果有许多 Surface Hub，或者它们位于远程位置，请使用 Microsoft Endpoint Manager 中的 Microsoft Intune（如果已部署在组织中）。 无论选择哪种方法，都需要创建 XML 配置文件，以对 Surface Hub 上的 Teams 设置进行更改。

## <a name="teams-configuration-file-syntax"></a>Teams 配置文件语法

Surface Hub 上的 Teams 配置是使用 XML 文件定义的。 XML 文件包含可用于控制 Teams 工作原理的所有设置。 Windows 配置设计器和 Microsoft Intune 使用相同的 XML 语法。 下面是 Teams 配置 XML 文件的示例：

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

下表描述了配置文件中提供的所有配置设置：

| 父级                  | 元素                                   | 属性 | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 无                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上 Teams 配置的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 确定 Surface Hub 是否播发它可用于Bluetooth连接。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 确定 Teams 是否自动接受基于邻近感应的会议。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含协调会议的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 确定是否将 Teams 配置为与其他设备一起参与协调会议。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 这是每个 Teams 会议室设备或 Surface Hub 的 UPN 的逗号分隔列表，设备应接受来自该设备的会议加入请求，或者应发送到哪些会议加入请求。<br>接受的值：字符串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含协调会议的配置音频和视频配置元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上 Teams 的音频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定在会议开始时麦克风将处于活动状态的设备。 只有一 (Teams 会议室设备) 可以将此字段设置为 ，而其余设备必须将此字段设置为 以避免音频回声和 `true` `false` 反馈。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 确定会议参与者是否可以打开或关闭麦克风。 将 **"音频默认值** "设置为 的设备应将此设置设置为 ，以便参与者不会意外打开麦克风并 `false` `false` 引发音频回声或反馈。<p>如果 **"音频** 默认值"设置为 `true` ，则忽略此设置，参与者可以将麦克风设为静音或取消静音。<br>接受的值 `true` ：、 `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制 Surface Hub 上 Teams 的视频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定在会议开始时相机将在哪个设备上处于活动状态。 为获得最佳体验，建议仅将 Teams 会议室设备设置为 ，而所有其他 `true` 设备都设置为 `false` 。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 确定会议参与者是否可以打开或关闭摄像机。 您可以在事件参与者想要共享不同视频透视图的其他任何设备上 (，例如，如果参与者正在使用 Surface Hub 白板 `true`) 。 如果不希望参与者在设备上打开或关闭摄像机，请将其设置为 `false` 。<p> 如果 **"视频** 默认值"设置为 `true` ，则忽略此设置，参与者可以打开或关闭摄像机。<br>接受的值 `true` ：、 `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>将 Teams 设置应用到 Surface Hub

在 Microsoft Endpoint Manager 中，使用 Windows 配置设计器或 Microsoft Intune 在 Surface Hub 上应用或更新 Teams 配置设置。

### <a name="use-windows-configuration-designer"></a>使用 Windows 配置设计器

可以使用 Windows 配置设计器创建可用于将 Teams 设置应用到 Surface Hub 的预配包。 将上面创建的 XML 文件粘贴到 Windows 配置设计器中，以创建预配包。

> [!IMPORTANT]
> 如果已使用预配包将 Teams 配置应用到 Surface Hub，并想要更改它，则需要先删除现有的预配包。 有关详细信息，请参阅删除由 Windows 配置设计器 [创建的预配包](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

执行以下操作，在 Windows 配置设计器中创建预配包：

1. 从 Windows 应用商店在本地计算机上安装 Windows 配置设计器并打开它
2. 选择 **"预配 Surface Hub 设备** "，然后选择 **"切换到高级编辑器"**
3. 下一个屏幕上，展开 **"WindowsTeamSettings**  >  **Teams"，** 然后选择"**配置"**
4. 在中间窗格的 **"** 配置"旁边的字段中，粘贴上面创建的单个 XML 行
5. 选择 **"导出**  >  **预配包"**
6. 在"名称"中提供预配包 **的名称，然后选择**"下 **一步**  >  **"**
7. 指定保存预配包的位置，然后选择"下一步 **"**
8. 选择 **"生成** "以创建预配包，然后选择" **完成"**

最后，创建预配包后，执行以下操作以将预配包应用到 Surface Hub：

1. 将上面创建的预配包保存到 U 盘
2. 将 U 盘插入 Surface Hub
3. 在 Surface Hub 上，打开"开始"菜单，选择" **所有应用**"，然后选择"设置 **"**
4. 提供管理员用户名和密码，然后选择" **是"**
5. 转到 **"Surface** Hub"，"**设备管理****"，"添加或删除预配包**"，然后"**添加包"**
6. 在 **"选择包"下**，选择预配包旁边的"添加"，然后重启 Surface Hub 

### <a name="use-microsoft-intune"></a>使用 Microsoft Intune

如果在 Microsoft 终结点管理中使用 Microsoft Intune 管理 Surface Hub，可以使用它将 Teams 设置应用到 Surface Hub。 将创建新的配置文件，然后将上面创建的 XML 文件粘贴到该文件中。

> [!IMPORTANT]
> Surface Hub 需在设备组中，以便 Microsoft Intune 能够识别要应用配置文件的设备。 若要了解如何创建设备组，请参阅添加 [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

执行以下操作以创建配置文件，以将 Teams 设置应用到 Surface Hub：

1. 通过访问 登录到 Microsoft 终结点管理器 https://endpoint.microsoft.com/
2. 导航到 **"设备**  >  **配置文件"并选择**"**创建配置文件"**
3. 在 **"平台"** 下， **选择"Windows 10 及更高版本"**
4. 在" **配置文件"** 下 **，选择"自定义**"，然后单击" **创建"**
5. 在" **基本信息"** 选项卡上的 **"名称**"中，提供配置文件的描述性名称，然后选择"下一步 **"**
6. 在"配置 **设置"选项卡** 上，选择" **添加"**
7. 在" **添加行** "窗格中，执行以下操作：
    1. 提供描述性名称，并选择性地提供要添加的 Teams 设置的说明
    2. 在 **OMA-URI** 中，输入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **"数据类型"** 中，选择 **"字符串 (XML 文件)**
    4. 打开文件浏览器，选择上面创建的 XML 文件，然后选择" **打开"**
8. 选择 **"添加"，** 然后选择"下 **一步"**
9. 在" **作业"** 选项卡上，确保" **分配到** "设置为" **所选组"**
10. 在 **"所选组**"下，选择 **"** 选择要包括的组"，然后选择包含 Surface Hub 的组，然后选择"选择 **"**
11. 选择"**下一步****"，"下一步"**
12. 在" **审阅 + 创建"中**，选择" **创建"**

## <a name="remove-teams-settings-from-a-surface-hub"></a>从 Surface Hub 中删除 Teams 设置

在 Microsoft Endpoint Manager 中，使用 Windows 配置设计器或 Microsoft Intune 删除 Surface Hub 上的 Teams 配置设置。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>删除 Windows 配置设计器创建的预配包

如果使用 Windows 配置设计器创建的预配包将 Teams 设置应用到 Surface Hub，请使用以下步骤删除该包及其设置：

1. 在 Surface Hub 上，打开"开始"菜单，选择" **所有应用**"，然后选择"设置 **"**
2. 提供管理员用户名和密码，然后选择" **是"**
3. 转到 **"Surface** Hub"，"**设备管理****"，然后添加或删除预配包**
4. 在要删除的预配包旁边，选择"删除 **"**
5. 转到 **Surface Hub，** 然后转到 **"应用"&功能**
6. 查找 **Microsoft Teams for Surface Hub，** 然后选择" **高级选项"**
7. 选择 **"重置**"，然后再次 **选择"重置** "
8. 重启 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>删除 Microsoft Intune 应用的设置

如果在 Microsoft 终结点管理中使用 Microsoft Intune 将 Teams 设置应用到 Surface Hub，请使用以下步骤删除配置文件及其设置：

1. 通过访问 登录到 Microsoft 终结点管理器 https://endpoint.microsoft.com/
2. 导航到 **"设备**  >  **配置文件"**
3. 选择包含要删除的协调会议设置的配置文件
4. 在配置文件详细信息页上，选择"删除 **"，** 然后选择" **确定"**

删除包含 Surface Hub 协调会议设置的配置文件后，使用以下步骤重置 Surface Hub 上的 Teams 应用：

1. 在 Surface Hub 上，打开"开始"菜单，选择" **所有应用**"，然后选择"设置 **"**
2. 提供管理员用户名和密码，然后选择" **是"**
3. 转到 **Surface Hub，** 然后转到 **"应用"&功能**
4. 查找 **Microsoft Teams for Surface Hub，** 然后选择" **高级选项"**
5. 选择 **"重置**"，然后再次 **选择"重置** "
6. 重启 Surface Hub