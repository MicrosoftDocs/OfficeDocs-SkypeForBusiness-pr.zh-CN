---
title: 在Microsoft Teams上管理Surface Hub
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
description: 使用Microsoft Teams配置设计器Surface Hub管理Microsoft Intune Windows设置
ms.openlocfilehash: 39d62296a87fa50722bce98a4fcd5e0372b362cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602157"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理Microsoft Teams上的Surface Hub

可以使用 Microsoft Teams 配置设计器Surface Hub或 Windows Microsoft Intune 管理Microsoft Endpoint Manager。 若要Windows设置，Microsoft Intune配置设计器或Teams知识。 有关这些选项的详细信息，请参阅以下文章：

- [为应用程序创建预配Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什么是Microsoft Intune管理？](/mem/intune/remote-actions/device-management)

Windows如果只有几个设备，并且可以轻松访问Surface Hub设计器是一个不错的选择。 如果有许多 Surface Hub，或者它们位于远程位置，请使用 Microsoft Intune Microsoft Endpoint Manager（如果已部署在你的组织中）。 无论选择哪种方法，都需要创建 XML 配置文件，以更改Teams上的Surface Hub。

## <a name="teams-configuration-file-syntax"></a>Teams配置文件语法

Teams上的配置Surface Hub XML 文件定义。 XML 文件包含可用于控制工作原理Teams设置。 两Windows配置设计器Microsoft Intune使用相同的 XML 语法。 下面是 XML 配置文件Teams示例：

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
| 无                    | `<SurfaceHubSettings>`                    |           | 包含所有配置元素，Teams上配置Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 确定是否Surface Hub播发它可用于蓝牙连接。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 确定是否Teams自动接受基于邻近感应的会议。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含协调会议的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 确定是否Teams配置为与其他设备一起参与协调会议。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 这是每个 Teams 会议室设备或 Surface Hub 设备应接受会议加入请求或者应发送到哪些会议加入请求的 UPN 的逗号分隔列表。<br>接受的值：字符串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含协调会议的配置音频和视频配置元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制音频Teams上Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定在会议开始时麦克风将处于活动状态的设备。 只有一 (设备Teams 会议室设备) 可以将此字段设置为 ，而其余设备必须将此字段设置为 以避免音频回声和 `true` `false` 反馈。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 确定会议参与者是否可以打开或关闭麦克风。 将 **"音频默认值** "设置为 的设备应将此设置设置为 ，以便参与者不会意外打开麦克风并 `false` 引发音频 `false` 回声或反馈。<p>如果 **"音频** 默认值"设置为 `true` ，则忽略此设置，参与者可以将麦克风设为静音或取消静音。<br>接受的值 `true` ：、 `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制视频上Teams视频Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 确定在会议开始时相机将在哪个设备上处于活动状态。 为获得最佳体验，建议仅将Teams 会议室设置为 ，而所有其他 `true` 设备都设置为 `false` 。<br>接受的值 `true` ：、 `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 确定会议参与者是否可以打开或关闭摄像机。 您可以在事件参与者想要共享不同视频透视图的其他任何设备上 (例如，如果参与者正在使用 Surface Hub `true` 白板) 。 如果不希望参与者在设备上打开或关闭摄像机，请将其设置为 `false` 。<p> 如果 **"视频** 默认值"设置为 `true` ，则忽略此设置，参与者可以打开或关闭摄像机。<br>接受的值 `true` ：、 `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>将Teams设置应用于Surface Hub

使用Teams设计器Surface Hub或Windows配置设计器Microsoft Intune更新Microsoft Endpoint Manager。

### <a name="use-windows-configuration-designer"></a>使用 Windows 配置设计器

可以使用 Windows 配置设计器创建一个预配包，该包可用于Teams Surface Hub 设置。 将上面创建的 XML 文件粘贴到Windows设计器中以创建预配包。

> [!IMPORTANT]
> 如果已使用预配包Teams配置Surface Hub并想要更改它，则需要先删除现有的预配包。 有关详细信息，请参阅[删除配置设计器](#remove-a-provisioning-package-created-by-windows-configuration-designer)创建的Windows包。

执行以下操作，在配置设计器Windows包：

1. 在本地Windows安装 Windows Store 中的配置设计器并打开它
2. 选择 **"Surface Hub设备"，** 然后选择 **"切换到高级编辑器"**
3. 下一个屏幕上，展开 **"WindowsTeamSettings"Teams**  >  并选择"配置 **"**
4. 在中间窗格的 **"** 配置"旁边的字段中，粘贴上面创建的单个 XML 行
5. 选择 **"导出**  >  **预配包"**
6. 在"名称"中提供预配包 **的名称，然后选择**"下 **一步**  >  **"**
7. 指定保存预配包的位置，然后选择"下一步 **"**
8. 选择 **"生成** "以创建预配包，然后选择" **完成"**

最后，创建预配包后，执行以下操作，将预配包应用到Surface Hub：

1. 将上面创建的预配包保存到 U 盘
2. 将 U 盘插入Surface Hub
3. 在Surface Hub上，打开"开始"菜单，选择"所有 **应用**"，**然后选择"设置**
4. 提供管理员用户名和密码，然后选择" **是"**
5. 转到 **Surface Hub、****设备** 管理 **、添加或删除预配包**，然后 **添加包**
6. 在 **"选择包"下**，选择预配包旁边的"添加"，然后重启Surface Hub 

### <a name="use-microsoft-intune"></a>使用Microsoft Intune

如果你的 Surface Hub 使用 Microsoft 终结点Microsoft Intune管理中的设置进行管理，则你可以使用它Teams Surface Hub 应用这些设置。 将创建新的配置文件，然后将上面创建的 XML 文件粘贴到该文件中。

> [!IMPORTANT]
> Surface Hub 需在设备组中，以便Microsoft Intune标识要应用配置文件的设备。 若要了解如何创建设备组，请参阅添加 [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

执行以下操作以创建配置文件，以将Teams应用到 Surface Hub：

1. 通过访问 Microsoft Endpoint Manager登录到https://endpoint.microsoft.com/
2. 导航到 **"设备**  >  **配置文件"并选择**"**创建配置文件"**
3. 在 **"平台**"**下，Windows 10和更高版本**
4. 在" **配置文件"** 下 **，选择"自定义**"，然后单击" **创建"**
5. 在" **基本信息"** 选项卡上的 **"名称**"中，提供配置文件的描述性名称，然后选择"下一步 **"**
6. 在"配置 **设置"选项卡** 上，选择" **添加"**
7. 在" **添加行** "窗格中，执行以下操作：
    1. 提供描述性名称，并选择性地提供Teams添加的设置的说明
    2. 在 **OMA-URI** 中，输入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **"数据类型"** 中，选择 **"字符串 (XML 文件)**
    4. 打开文件浏览器，选择上面创建的 XML 文件，然后选择" **打开"**
8. 选择 **"添加"，** 然后选择"下 **一步"**
9. 在" **作业"** 选项卡上，确保" **分配到** "设置为" **所选组"**
10. 在 **"所选组**"下，选择 **"** 选择要包括的组"，然后选择包含 Surface Hub 的组，然后选择"选择 **"**
11. 选择"**下一步****"，"下一步"**
12. 在" **审阅 + 创建"中**，选择" **创建"**

## <a name="remove-teams-settings-from-a-surface-hub"></a>从Teams中删除Surface Hub

使用Teams设计器Surface Hub配置设计器Windows删除Microsoft Intune配置Microsoft Endpoint Manager。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>删除配置设计器创建的Windows包

如果使用 Windows 配置Teams创建的预配包将 Teams 设置应用到 Surface Hub，请使用以下步骤删除该包及其设置：

1. 在Surface Hub上，打开"开始"菜单，选择"所有 **应用**"，**然后选择"设置**
2. 提供管理员用户名和密码，然后选择" **是"**
3. 转到 **"Surface Hub** 设备 **管理****"，然后添加或删除预配包**
4. 在要删除的预配包旁边，选择"删除 **"**
5. 转到 **"Surface Hub"，** 然后 **转到"应用&功能**
6. 查找 **Microsoft Teams选项Surface Hub** 然后选择"**高级选项"**
7. 选择 **"重置**"，然后再次 **选择"重置** "
8. 重启Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>删除由用户应用的Microsoft Intune

如果在 Microsoft Teams管理Surface Hub应用Microsoft Intune设置，请使用以下步骤删除配置文件及其设置：

1. 通过访问 Microsoft Endpoint Manager登录到https://endpoint.microsoft.com/
2. 导航到 **"设备**  >  **配置文件"**
3. 选择包含要删除的协调会议设置的配置文件
4. 在配置文件详细信息页上，选择"删除 **"，** 然后选择" **确定"**

删除包含协调会议设置的配置文件后Surface Hub，使用以下步骤重置 Teams 应用Surface Hub：

1. 在Surface Hub上，打开"开始"菜单，选择"所有 **应用**"，**然后选择"设置**
2. 提供管理员用户名和密码，然后选择" **是"**
3. 转到 **"Surface Hub"，** 然后 **转到"应用&功能**
4. 查找 **Microsoft Teams选项Surface Hub** 然后选择"**高级选项"**
5. 选择 **"重置**"，然后再次 **选择"重置** "
6. 重启Surface Hub