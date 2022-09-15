---
title: 在 Surface Hub 上管理 Microsoft Teams 配置
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
description: 使用 Microsoft Intune 和 Windows 配置设计器管理 Surface Hub 上的 Microsoft Teams 设置
ms.openlocfilehash: 7296ed84cf34b47c562cb3ab5f5582fe1eec58ac
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705971"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>在 Surface Hub 上管理 Microsoft Teams 设置

可以使用 Windows 配置设计器或 Microsoft Endpoint Manager 中的 Microsoft Intune 管理 Surface Hub 上的 Microsoft Teams 设置。 需要了解 Windows 配置设计器或Microsoft Intune才能对 Teams 设置进行更改。 有关这些选项的详细信息，请参阅以下文章：

- [为Windows 10创建预配包](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什么是Microsoft Intune设备管理？](/mem/intune/remote-actions/device-management)

如果只有几个 Surface Hub 设备并且可以轻松访问这些设备，则 Windows 配置设计器是一个不错的选择。 如果有许多 Surface Hub，或者它们位于远程位置，请在 Microsoft Endpoint Manager中使用Microsoft Intune（如果已在组织中部署）。 无论选择哪种方法，都需要创建一个 XML 配置文件，以便对 Surface Hub 上的 Teams 设置进行更改。

## <a name="teams-configuration-file-syntax"></a>Teams 配置文件语法

Surface Hub 上的 Teams 配置是使用 XML 文件定义的。 XML 文件包含可用于控制 Teams 工作原理的所有设置。 Windows 配置设计器和Microsoft Intune使用相同的 XML 语法。 下面是 Teams 配置 XML 文件的示例：

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

| 父母                  | 元素                                   | 属性 | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 无                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上 Teams 配置的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 确定 Surface Hub 是否播发它可用于蓝牙连接。<br>接受的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 确定 Teams 是否会自动接受基于邻近的会议。<br>接受的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含协调会议的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 确定 Teams 是否配置为与其他设备一起参加协调会议。<br>接受的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 这是设备应接受会议加入请求的每个Teams 会议室设备或 Surface Hub 的逗号分隔的 UPN 列表，或者应向其发送会议加入请求。<br>接受的值：字符串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含协调会议的配置音频和视频配置元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上 Teams 的音频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定会议开始时麦克风将处于活动状态的设备。 只有一个设备 (通常Teams 会议室设备) 可以设置`true`此字段，而其余设备必须设置此字段以避免`false`音频回显和反馈。<br>接受的值： `true``false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 确定会议中的参与者是否可以打开或关闭麦克风。 **将音频默认** 设置为`false`的设备应设置`false`此设置，以便参与者不能意外打开麦克风并引起音频回显或反馈。<p>如果 **音频默认** 设置为 `true`“音频”，则忽略此设置，参与者可以静音或取消静音麦克风。<br>接受的值： `true``false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制 Surface Hub 上 Teams 的视频配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定在会议开始时相机将处于活动状态的设备。 为了获得最佳体验，我们建议仅将Teams 会议室设备设置为`true``false`所有其他设备。<br>接受的值： `true``false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 确定会议中的参与者是否可以打开或关闭相机。 可以在事件参与者希望共享不同视频透视的任何其他设备上将其设置 `true` 为 (例如参与者使用 Surface Hub 白板) 。 如果不希望参与者在设备上打开或关闭相机，请将其设置为 `false`。<p> 如果 **视频默认** 设置为 `true`“视频”，则忽略此设置，参与者可以打开或关闭相机。<br>接受的值： `true``false` |

## <a name="apply-teams-settings-to-surface-hub"></a>将 Teams 设置应用到 Surface Hub

在 Microsoft Endpoint Manager 中使用 Windows 配置设计器或Microsoft Intune在 Surface Hub 上应用或更新 Teams 配置设置。

### <a name="use-windows-configuration-designer"></a>使用 Windows 配置设计器

可以使用 Windows 配置设计器创建可用于将 Teams 设置应用到 Surface Hub 的预配包。 将上面创建的 XML 文件粘贴到 Windows 配置设计器中，以创建预配包。

> [!IMPORTANT]
> 如果已使用预配包将 Teams 配置应用到 Surface Hub，并且想要更改它，则需要先删除现有的预配包。 有关详细信息，请参阅 [删除由 Windows 配置设计器创建的预配包](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

执行以下操作，在 Windows 配置设计器中创建预配包：

1. 在本地计算机上从 Windows 应用商店安装 Windows 配置设计器并将其打开
2. 选择 **“预配 Surface Hub”设备** ，然后 **切换到高级编辑器**
3. 在下一个屏幕上，展开 **WindowsTeamSettings** > **Teams** 并选择 **“配置”**
4. 在中间窗格的 **“配置”** 旁边的字段中，粘贴上面创建的单行 XML
5. 选择 **“导出** > **预配”包**
6. 在 **“名称**”中为预配包提供名称，然后选择 **“下** 一 **步** > ”
7. 指定保存预配包的位置，然后选择 **“下一步**”
8. 选择 **“生成** ”以创建预配包，然后 **完成**

最后，创建预配包后，请执行以下操作，将预配包应用到 Surface Hub：

1. 将上面创建的预配包保存到 USB 驱动器
2. 将 USB 驱动器插入 Surface Hub
3. 在 Surface Hub 上，打开“开始”菜单，选择 **“所有应用**”，然后选择 **“设置”**
4. 提供管理员用户名和密码，然后选择 **“是”**
5. 转到 **Surface Hub**、 **设备管理**、 **添加或删除预配包**，然后 **添加包**
6. 在 **“选择包**”下，选择预配包旁边的 **“添加** ”，然后重启 Surface Hub

### <a name="use-microsoft-intune"></a>使用Microsoft Intune

如果 Surface Hub 在 Microsoft Endpoint Management 中使用Microsoft Intune进行管理，则可以使用它将 Teams 设置应用到 Surface Hub。 你将创建一个新的配置文件，然后将上面创建的 XML 文件粘贴到其中。

> [!IMPORTANT]
> Surface Hub 需要位于设备组中，以便Microsoft Intune能够识别要将配置文件应用于哪些设备。 有关如何创建设备组的信息，请参阅 [“添加组”来组织用户和设备](/mem/intune/fundamentals/groups-add)。

执行以下操作，创建配置文件以将 Teams 设置应用到 Surface Hub：

1. 通过访问登录到 Microsoft Endpoint Managerhttps://endpoint.microsoft.com/
2. 导航到 **设备** > **配置文件** 并选择 **“创建配置文件”**
3. 在 **“平台**”下，选择 **Windows 10及更高版本**
4. 在 **“配置文件**”下，选择 **“自定义**”，然后单击 **“创建”**
5. 在 **“基本信息”** 选项卡上的 **“名称”** 中，为配置文件提供描述性名称，然后选择 **“下一步**”
6. 在“**配置设置”** 选项卡上，选择 **“添加**”
7. 在 **“添加行** ”窗格中，执行以下操作：
    1. 提供描述性名称以及所添加的 Teams 设置的说明（可选）
    2. 在 **OMA-URI 中**，输入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **数据类型** 中，选择 **字符串 (XML 文件)**
    4. 打开文件浏览器，选择上面创建的 XML 文件，然后 **打开**
8. 选择 **“添加**”，然后选择 **“下一步**”
9. 在“**分配”** 选项卡上，确保 **“分配**”设置为 **“所选组**”
10. 在 **“选定组**”下，**选择要包含的组**，然后选择包含 Surface Hub 的组，然后选择“**选择**”
11. 选择 **“下一步**”、“ **下一步”**
12. 在 **“审阅 + 创建**”中，选择 **“创建”**

## <a name="remove-teams-settings-from-a-surface-hub"></a>从 Surface Hub 中删除 Teams 设置

在 Microsoft Endpoint Manager 中使用 Windows 配置设计器或Microsoft Intune删除 Surface Hub 上的 Teams 配置设置。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>删除由 Windows 配置设计器创建的预配包

如果使用 Windows 配置设计器创建的预配包将 Teams 设置应用到 Surface Hub，请使用以下步骤删除包及其设置：

1. 在 Surface Hub 上，打开“开始”菜单，选择 **“所有应用**”，然后选择 **“设置”**
2. 提供管理员用户名和密码，然后选择 **“是”**
3. 转到 **Surface Hub**、 **设备管理** ，然后 **添加或删除预配包**
4. 在要删除的预配包旁边，选择 **“删除”**
5. 转到 **Surface Hub** ，然后 **转到应用&功能**
6. 查找 **适用于 Surface Hub 的 Microsoft Teams** ，然后选择 **“高级选项”**
7. 选择 **“重置**”，然后再次 **重置**
8. 重启 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>删除Microsoft Intune应用的设置

如果在 Microsoft Endpoint Management 中使用Microsoft Intune将 Teams 设置应用到 Surface Hub，请使用以下步骤删除配置文件及其设置：

1. 通过访问登录到 Microsoft Endpoint Managerhttps://endpoint.microsoft.com/
2. 导航到 **设备** > **配置文件**
3. 选择包含要删除的协调会议设置的配置文件
4. 在配置文件详细信息页上，选择 **“删除** ”，然后 **选择“确定”**

删除包含 Surface Hub 协调会议设置的配置文件后，请使用以下步骤在 Surface Hub 上重置 Teams 应用：

1. 在 Surface Hub 上，打开“开始”菜单，选择 **“所有应用**”，然后选择 **“设置”**
2. 提供管理员用户名和密码，然后选择 **“是”**
3. 转到 **Surface Hub** ，然后 **转到应用&功能**
4. 查找 **适用于 Surface Hub 的 Microsoft Teams** ，然后选择 **“高级选项”**
5. 选择 **“重置**”，然后再次 **重置**
6. 重启 Surface Hub
