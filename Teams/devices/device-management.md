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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 了解如何管理组织中Teams使用的设备。
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 576c22d95dbbbb16105eb8e365c717ba7140cfb8
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65767238"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams：管理设备 

可以从Microsoft Teams管理中心管理与组织中Microsoft Teams一起使用的设备。 可以查看和管理组织的设备清单，并执行更新、重启和监视设备诊断等任务。 还可以创建配置文件并将配置文件分配给设备或设备组。

若要管理设备（例如更改设备配置、重启设备、管理更新或查看设备和外围运行状况），需要为你分配以下Microsoft 365管理员角色之一：

- Microsoft 365全局管理员
- Teams服务管理员
- Teams设备管理员

有关Teams中的管理员角色的详细信息，请参阅[使用Teams管理员角色来管理Teams](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？

可以管理经过认证并注册Teams的任何设备。 当用户首次登录到设备上Teams时，会自动注册设备。 有关可管理的认证设备的列表，请参阅：

- [Microsoft Teams 会议室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [会议电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [桌面电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams显示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams面板](teams-panels.md)

若要管理设备，[请在Microsoft Teams管理中心的](https://admin.teams.microsoft.com)左侧导航中转到 **Teams设备**，然后选择设备类型。 每种类型的设备都有各自的部分，这使你可以单独管理它们。

## <a name="manage-teams-rooms-on-windows-devices"></a>管理Windows设备上的Teams 会议室

可以使用Teams管理中心在组织内Windows设备上查看和管理Teams 会议室。 通过Teams管理中心，可以一目了然地查看哪些设备正常运行，哪些设备需要关注，并让你专注于特定设备，查看有关设备运行状况、会议性能、通话质量和外围设备的详细信息。 

下面是管理Teams 会议室设备可以执行的一些操作。 Teams 会议室设备可以在Windows上的Teams **设备** > Teams 会议室下 **的Microsoft Teams**[管理中心](https://admin.teams.microsoft.com)找到。

有关如何管理Teams 会议室设备的详细信息，请参阅[“管理Microsoft Teams 会议室](../rooms/rooms-manage.md)”。

| 要执行此操作...                          | 执行此操作                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改一个或多个设备上的设置 | 选择一个或多个设备> **编辑设置**。 如果选择多个设备，更改的值将替换所有选定设备上的值。                                                                                                                                                                                                                       |
| 重启设备                        | 在 **重启**>选择一个或多个设备。 重启设备时，可以选择是立即重启设备，还是选择 **“计划重启** ”以在特定日期和时间重启设备。 选择的日期和时间是正在重启的设备的本地日期和时间。                                                                                            |
| 查看会议活动                  | 选择设备名称以打开活动>设备详细 **信息。** 打开 **“活动”** 选项卡时，可以看到设备参与的所有会议。 此摘要视图显示会议开始时间、参与者数、持续时间和总体通话质量。                                                                                        |
| 查看会议详细信息                   | 选择设备名称以打开设备详细信息> **活动** >选择会议。 打开会议的详细信息时，可以看到会议中的所有参与者、他们在呼叫中的时间、Teams会话类型及其单个呼叫质量。 如果要查看有关参与者呼叫的技术信息，请选择参与者的呼叫开始时间。 |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>管理手机、Teams 会议室Android、Teams显示器和Teams面板 

在Teams管理中心，可以查看和管理电话、Teams 会议室Android、Teams显示器以及Teams组织中注册的Teams面板。 对于每个设备，你将看到的信息包括设备名称、制造商、模型、用户、状态、操作、上次查看时间和历史记录。 可以自定义视图以显示符合你需求的信息。

如果已注册手机、Teams 会议室Android、Teams显示器和Teams面板，则会自动在Microsoft Intune中注册。 注册设备后，将确认设备符合性，并将条件访问策略应用到设备。

下面是一些示例，说明如何在组织中管理手机、Teams 会议室Android、Teams显示和Teams面板。  

| 要执行此操作...                           | 执行此操作                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改设备信息               | 选择> **编辑** 的设备。 可以编辑设备名称、资产标记等详细信息，并添加备注。                                                                                                                                                                                                              |
| 管理软件更新                 | 选择> **更新** 的设备。 可以查看设备可用的软件和固件更新列表，并选择要安装的更新。 有关更新设备的详细信息，请参阅[远程更新Teams设备](remote-update.md)                                                          |
| 将Teams手机升级到Teams显示器  | 在 **“IP 电话**”页上，选择一部或多部Teams手机>**升级**。 此选项仅适用于支持升级到Teams显示器的手机。 若要了解详细信息，请参阅[升级Teams手机以Teams显示。](upgrade-phones-to-displays.md)                                                      |
| 分配或更改配置策略 | 选择一个或多个设备> **分配配置**。                                                                                                                                                                                                                                                       |
| 添加或删除设备标记               | 选择一个或多个设备> **管理标记**。 有关设备标记的详细信息，请参阅[管理Teams设备标记](manage-device-tags.md)。                                                                                                                                                                 |
| 重启设备                         | 在 **重启**>选择一个或多个设备。                                                                                                                                                                                                                                                                    |
| 使用设备标记筛选设备        | 选择筛选器图标，选择 **“标记”** 字段，指定要筛选的设备标记，然后选择 **“应用**”。 有关使用设备标记筛选设备的详细信息，请参阅 [使用筛选器返回具有特定标记的设备](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 查看设备历史记录和诊断     | 在 **“历史记录** ”列下，单击设备的 **“视图** ”链接以查看其更新历史记录和诊断详细信息。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>在Teams中使用配置文件

使用配置文件管理组织中不同Teams设备的设置和功能，包括Android上的Teams 会议室、Teams显示器、Teams手机和Teams面板。 可以创建或上传配置文件，包括要启用或禁用的设置和功能，然后将配置文件分配给设备或设备集。 

#### <a name="create-a-configuration-profile"></a>创建配置文件

若要为Teams设备类型创建配置文件，请执行以下操作：

1. 在左侧导航栏中，转到 **Teams设备**>选择Teams设备类型>**配置文件**。 例如，选择 **Teams设备** > **Teams面板** > **配置文件**，为Teams面板创建新的配置文件。
2. 单击“**添加**”。
3. 输入配置文件的名称，并可以选择添加友好说明。
4. 指定配置文件所需的设置，然后单击 **“保存**”。
   新创建的配置文件显示在配置文件列表中。

#### <a name="assign-a-configuration-profile"></a>分配配置文件
为Teams设备类型创建配置文件后，将其分配给一个或多个设备。

1. 在左侧导航栏中，转到 **Teams设备**>选择Teams设备类型。 例如，若要将配置文件分配到Teams面板设备，请选择 **Teams设备** > **Teams面板**。
2. 选择一个或多个设备，然后单击 **“分配配置**”。  
3. 在 **“分配配置** ”窗格中，搜索要分配给所选设备的配置文件。
4. 单击“**应用**”。
   对于向其应用配置策略的设备，“ **操作** ”列显示 **“配置更新** ”， **配置文件** 列显示配置文件名称。
