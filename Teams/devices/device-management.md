---
title: 在 Microsoft Teams 中管理设备
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 管理组织中与 Microsoft Teams 一起使用的设备。
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e545a6d4208e6f54abbf72327cf887d45b34e141
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2023
ms.locfileid: "69807444"
---
# <a name="manage-devices-in-teams"></a>在 Teams 中管理设备 

可以从 Microsoft Teams 管理中心管理组织中与 Microsoft Teams 一起使用的设备。 可以查看和管理组织的设备清单，并执行更新、重启和监视设备的诊断等任务。 还可以创建配置文件并将其分配给设备或设备组。

若要管理设备，例如更改设备配置、重启设备、管理更新或查看设备和外围设备运行状况，需要分配以下 Microsoft 365 管理员角色之一：

- Microsoft 365 全局管理员
- Teams 服务管理员
- Teams 设备管理员

有关 Teams 中的管理员角色的详细信息，请参阅 [使用 Teams 管理员角色管理 Teams](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？

可以管理已获得 Teams 认证和注册的任何设备。 用户首次登录设备上的 Teams 时，会自动注册设备。 有关可管理的认证设备的列表，请参阅：

- [Microsoft Teams 会议室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [会议电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [桌面电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 显示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 面板](teams-panels.md)

若要管理设备，请在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)的左侧导航栏中，转到 **“Teams 设备”**，然后选择设备类型。 每种类型的设备都有其各自的部分，这允许你单独管理它们。

## <a name="manage-teams-rooms-on-windows-devices"></a>在 Windows 设备上管理Teams 会议室

可以使用 Teams 管理中心在整个组织中的 Windows 设备上查看和远程管理Teams 会议室。 借助 Teams 管理中心，可以轻松一目了然地查看哪些设备正常运行，哪些设备需要注意，并让你专注于特定设备，以查看有关设备运行状况、会议性能、通话质量和外围设备的详细信息。 

下面是管理Teams 会议室设备的一些操作。 Teams 会议室设备可以在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)的 **Teams 设备** > **Teams 会议室 Windows 下** 找到。

有关如何管理Teams 会议室设备的详细信息，请参阅[管理Microsoft Teams 会议室](../rooms/rooms-manage.md)。

| 执行此操作...                          | 执行此操作                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改一个或多个设备上的设置 | > **编辑设置** 选择一个或多个设备。 如果选择多个设备，则更改的值将替换所有选定设备上的值。                                                                                                                                                                                                                       |
| 重启设备                        | 选择一个或多个设备> **重启**。 重启设备时，可以选择是立即重启设备，还是选择“ **计划重启** ”以在特定日期和时间重启设备。 所选的日期和时间是重启设备的本地日期和时间。                                                                                            |
| 查看会议活动                  | 选择设备名称以打开设备详细信息> **活动**。 打开“ **活动** ”选项卡时，可以看到设备已参与的所有会议。 此摘要视图显示会议开始时间、参与者数、持续时间和总体通话质量。                                                                                        |
| 查看会议详细信息                   | 选择设备名称以打开设备详细信息> **活动** >选择会议。 打开会议的详细信息时，可以看到会议中的所有参与者、他们参加通话的时间、Teams 会话类型及其个人通话质量。 如果要查看有关参与者呼叫的技术信息，请选择参与者的呼叫开始时间。 |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>管理 Android 上的电话、Teams 会议室、Teams 显示器和 Teams 面板 

在 Teams 管理中心中，可以查看和管理电话、Android 上的Teams 会议室、Teams 显示器以及组织中在 Teams 中注册的 Teams 面板。 你将为每个设备看到的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。 可以自定义视图以显示符合需求的信息。

如果你已注册电话、Android 上的Teams 会议室、Teams 显示器和 Teams 面板，则会自动在 Microsoft Intune 中注册。 注册设备后，将确认设备符合性，并将条件访问策略应用于设备。

下面是有关如何在 Android 上管理电话、Teams 会议室、Teams 显示器和组织中的 Teams 面板的一些示例。  

| 执行此操作...                           | 执行此操作                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改设备信息               | 选择“ **编辑**”>设备。 可以编辑设备名称、资产标记和添加备注等详细信息。                                                                                                                                                                                                              |
| 管理软件更新                 | 选择设备> **更新**。 可以查看设备可用的软件和固件更新列表，然后选择要安装的更新。 有关更新设备的详细信息，请参阅 [远程更新 Teams 设备](remote-update.md)                                                          |
| 将 Teams 电话升级到 Teams 显示器  | 在 **“IP 电话** ”页上，选择一个或多个 Teams 电话> **升级**。 此选项仅适用于支持升级到 Teams 显示器的手机。 若要了解详细信息，请参阅 [将 Teams 电话升级到 Teams 显示器](upgrade-phones-to-displays.md)。                                                      |
| 分配或更改配置策略 | 选择一个或多个设备> **分配配置**。                                                                                                                                                                                                                                                       |
| 添加或删除设备标记               | > **“管理标记**”选择一个或多个设备。 有关设备标记的详细信息，请参阅 [管理 Teams 设备标记](manage-device-tags.md)。                                                                                                                                                                 |
| 重启设备                         | 选择一个或多个设备> **重启**。                                                                                                                                                                                                                                                                    |
| 使用设备标记筛选设备        | 选择筛选器图标，选择 **“标记”** 字段，指定要筛选的设备标记，然后选择“ **应用**”。 有关使用设备标记筛选设备的详细信息，请参阅 [使用筛选器返回具有特定标记的设备](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 查看设备历史记录和诊断     | 在“ **历史记录** ”列下，单击设备的 **“查看** ”链接以查看其更新历史记录和诊断详细信息。                                                                                                                                                                                         |

### <a name="view-android-device-sign-in-failures"></a>查看 Android 设备登录失败

如果登录 Android 设备时遇到问题，可以查看设备的详细信息页面，了解可能已发生哪些登录失败。

1. 在左侧导航中，转到 **Teams 设备** >选择 Teams 设备类型。 例如，如果 Android 设备是手机，请选择“ **手机**”。
2. 单击要查看其登录失败的手机的显示名称。 这将打开设备的详细信息页。
3. 在设备详细信息页上，选择“**活动**”选项卡，然后在“**活动类型**”下拉列表 **中选择“登录失败**”。

> [!NOTE]
> 如果登录时遇到问题的设备未看到任何登录失败，请确保设备的固件位于其制造商提供的最新版本上。

返回的结果包含以下信息：

- 登录失败的时间。
- 尝试登录到设备的帐户。
- 失败的原因。

### <a name="use-configuration-profiles-in-teams"></a>在 Teams 中使用配置文件

使用配置文件管理组织中不同 Teams 设备的设置和功能，包括 Android 上的Teams 会议室、Teams 显示器、Teams 手机和 Teams 面板。 可以创建或上传配置文件以包括要启用或禁用的设置和功能，然后将配置文件分配给设备或设备集。 

#### <a name="create-a-configuration-profile"></a>创建配置文件

若要为 Teams 设备类型创建配置文件，请执行以下操作：

1. 在左侧导航中，转到 **Teams 设备** >选择 Teams 设备类型> **配置文件**。 例如，选择 **“Teams 设备** > **”“Teams 面板** > **”“配置文件”** ，为 Teams 面板创建新的配置文件。
2. 单击“**添加**”。
3. 输入配置文件的名称，并选择性地添加友好说明。
4. 指定配置文件所需的设置，然后单击“ **保存**”。
   新创建的配置文件将显示在配置文件列表中。

#### <a name="assign-a-configuration-profile"></a>分配配置文件

为 Teams 设备类型创建配置文件后，将其分配给一个或多个设备。

1. 在左侧导航中，转到 **“Teams 设备”** >选择 Teams 设备类型。 例如，若要将配置文件分配给 Teams 面板设备，请选择“ **Teams 设备** > **Teams 面板**”。
2. 选择一个或多个设备，然后单击“ **分配配置**”。  
3. 在 **“分配配置** ”窗格中，搜索要分配给所选设备的配置文件。
4. 单击“**应用**”。
   对于已应用配置策略的设备， **“操作”** 列显示 **“配置更新”** ，“ **配置文件”** 列显示配置文件名称。
